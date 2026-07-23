---
name: Confirm availability of funds (CBPII)
description: Set up an OBIE funds-confirmation-consent, have the customer authorise it, then check whether funds are available on a Tandem account via the Confirmation of Funds API.
api: openapi/obie-standard-confirmation-funds-openapi.yaml
operations: [CreateFundsConfirmationConsents, GetFundsConfirmationConsentsConsentId, CreateFundsConfirmations, DeleteFundsConfirmationConsentsConsentId]
---

# Confirm availability of funds (CBPII)

Tandem Bank exposes UK Open Banking CBPII through Token's dedicated interface
(OBIE Read/Write v4.0.1). You must be a registered CBPII (card-based payment
instrument issuer) with the `fundsconfirmations` scope.

## Preconditions
- Registered TPP with mTLS transport cert and `fundsconfirmations` scope.
- FAPI headers (`x-fapi-interaction-id`, `x-fapi-auth-date`) on every call.

## Steps
1. **Create the consent** — `CreateFundsConfirmationConsents` with the `DebtorAccount`
   and consent `ExpirationDateTime`. Store the `ConsentId`.
2. **Redirect for SCA** — run the `authorizationCode` flow so the PSU authorises the consent.
3. **Confirm consent status** — `GetFundsConfirmationConsentsConsentId` (`Status` = `Authorised`).
4. **Check funds** — `CreateFundsConfirmations` with the `ConsentId` and the `InstructedAmount`;
   read the boolean `FundsAvailable` result.
5. **Revoke when done** — `DeleteFundsConfirmationConsentsConsentId` to end the standing consent.

## Rules
- A funds confirmation returns only a yes/no availability result — never a balance.
- Errors use the OBIE `OBErrorResponse1` envelope — see `errors/tandem-bank-problem-types.yml`.
