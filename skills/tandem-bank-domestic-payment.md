---
name: Initiate a domestic payment (PIS)
description: Create and authorise an OBIE domestic-payment-consent, then submit the payment against Tandem Bank's Open Banking dedicated interface with an idempotency key.
api: openapi/obie-standard-payment-initiation-openapi.yaml
operations: [CreateDomesticPaymentConsents, GetDomesticPaymentConsentsConsentId, GetDomesticPaymentConsentsConsentIdFundsConfirmation, CreateDomesticPayments, GetDomesticPaymentsDomesticPaymentId]
---

# Initiate a domestic payment (PIS)

Tandem Bank exposes UK Open Banking PIS through Token's dedicated interface
(OBIE Read/Write v4.0.1). You must be an FCA/eIDAS-registered PISP with the
`payments` scope.

## Preconditions
- Registered TPP with mTLS transport cert and `payments` scope.
- Detached JWS request signing: send `x-jws-signature` on write bodies.
- An `x-idempotency-key` on every payment/consent create (valid 24h; see `conventions/`).

## Steps
1. **Create the payment consent** — `CreateDomesticPaymentConsents` with the
   `Initiation` (creditor account, `InstructedAmount`, reference). Include `x-idempotency-key`
   and `x-jws-signature`. Store the `ConsentId`.
2. **Redirect for SCA** — run the `authorizationCode` flow so the PSU authorises the consent;
   exchange the code for a consent-bound access token.
3. **Confirm consent is authorised** — `GetDomesticPaymentConsentsConsentId` (`Status` = `Authorised`);
   optionally check `GetDomesticPaymentConsentsConsentIdFundsConfirmation`.
4. **Submit the payment** — `CreateDomesticPayments` referencing the `ConsentId`, re-sending the
   same `Initiation`, a fresh `x-idempotency-key`, and `x-jws-signature`. Store `DomesticPaymentId`.
5. **Track status** — `GetDomesticPaymentsDomesticPaymentId` until a terminal `Status`
   (`AcceptedSettlementCompleted` / `Rejected`).

## Rules
- Reuse of an `x-idempotency-key` with a changed payload returns a 4xx — generate a new key per distinct request.
- The `Initiation` in the payment MUST match the authorised consent, or the payment is rejected.
- Errors use the OBIE `OBErrorResponse1` envelope — see `errors/tandem-bank-problem-types.yml`.
