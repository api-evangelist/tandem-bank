---
name: Access account and transaction information (AIS)
description: Set up an OBIE account-access-consent, have the customer authorise it under SCA, then read accounts, balances and transactions from Tandem Bank's Open Banking dedicated interface.
api: openapi/obie-standard-account-info-openapi.yaml
operations: [CreateAccountAccessConsents, GetAccountAccessConsentsConsentId, GetAccounts, GetAccountsAccountId, GetAccountsAccountIdBalances, GetAccountsAccountIdTransactions]
---

# Access account and transaction information (AIS)

Tandem Bank exposes UK Open Banking AIS through a dedicated interface provided by
Token, conforming to the OBIE Read/Write API Standard v4.0.1. You must be an
FCA/eIDAS-registered AISP with the `accounts` scope; production base URLs are
issued per authorised TPP during Token onboarding.

## Preconditions
- Registered TPP with an mTLS transport certificate and `accounts` scope.
- FAPI-grade OAuth2/OIDC client (see `authentication/tandem-bank-authentication.yml`).
- Send FAPI headers on every call: `x-fapi-interaction-id`, `x-fapi-auth-date`, `x-fapi-customer-ip-address`.

## Steps
1. **Create the consent** — `CreateAccountAccessConsents` with the requested `Permissions[]`
   (e.g. `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`). Store the returned `ConsentId`.
2. **Redirect the customer for SCA** — start the `authorizationCode` flow (PSUOAuth2Security)
   so the PSU authorises the consent under PSD2 Strong Customer Authentication; exchange the
   code for an access token bound to the `ConsentId`.
3. **Verify consent status** — `GetAccountAccessConsentsConsentId` and confirm `Status` is `Authorised`.
4. **List accounts** — `GetAccounts` (or `GetAccountsAccountId` for one) to obtain `AccountId`s.
5. **Read balances** — `GetAccountsAccountIdBalances`.
6. **Read transactions** — `GetAccountsAccountIdTransactions`, paging via the OBIE `Links.Next`
   until absent (see `conventions/tandem-bank-conventions.yml`).

## Rules
- Reads are idempotent and safe to retry on `429`/`5xx` (honour `Retry-After`).
- Errors use the OBIE `OBErrorResponse1` envelope — see `errors/tandem-bank-problem-types.yml`.
- Never request permissions beyond what the use case needs; consents expire and can be revoked.
