# Tandem Bank (tandem-bank)

Tandem Bank (Tandem Bank Limited) is a UK app-only challenger and self-styled "greener" digital bank founded in 2014 and headquartered in Blackpool, England. It obtained its UK banking licence through the 2018 acquisition of Harrods Bank and has grown by acquiring Allium Lending Group, Oplo, and Loop Money. Tandem offers savings and cash ISAs, green home-improvement and home loans, mortgages, motor finance, and a credit card. Tandem Bank Limited is authorised by the Prudential Regulation Authority and regulated by the Financial Conduct Authority.

Tandem is not one of the CMA9 and does not publish a public Open Data reference API. As an FCA-authorised ASPSP it meets UK Open Banking / PSD2 obligations through a dedicated interface provided by **Token**, conformant to the Open Banking Implementation Entity (OBIE) Read/Write Standard, secured with FAPI-grade OAuth2/OIDC, mutual-TLS, and PSD2 strong customer authentication. Tandem also consumes Open Banking as a third-party provider via TrueLayer for savings onboarding and transfers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/tandem-bank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/tandem-bank/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Open Banking
- PSD2
- OBIE
- FAPI
- United Kingdom
- Payments
- Account Information
- Challenger Bank
- Fintech

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Tandem Bank Account and Transaction Information API (AIS)

Open Banking Account Information Service exposing account, balance, transaction, and product data for Tandem's credit card and savings products, via the Token-provided PSD2 dedicated interface, conformant to the OBIE Read/Write Account and Transaction API Standard.

- **Human URL:** [https://developer.token.io/](https://developer.token.io/)

#### Tags

- Account Information
- AISP
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-standard-account-info-openapi.yaml) — shared OBIE standard specification (not a Tandem-proprietary contract)
- [Documentation](https://developer.token.io/)
- [API Reference](https://github.com/OpenBankingUK/read-write-api-specs)

### Tandem Bank Payment Initiation API (PIS)

Open Banking Payment Initiation Service for initiating payments against Tandem accounts, via the Token-provided PSD2 dedicated interface, conformant to the OBIE Read/Write Payment Initiation API Standard.

- **Human URL:** [https://developer.token.io/](https://developer.token.io/)

#### Tags

- Payment Initiation
- PISP
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-standard-payment-initiation-openapi.yaml) — shared OBIE standard specification (not a Tandem-proprietary contract)
- [Documentation](https://developer.token.io/)
- [API Reference](https://github.com/OpenBankingUK/read-write-api-specs)

### Tandem Bank Confirmation of Funds API (CBPII)

Open Banking Confirmation of Funds Service allowing card-based payment instrument issuers to confirm availability of funds, via the Token-provided PSD2 dedicated interface, conformant to the OBIE Read/Write Confirmation of Funds API Standard.

- **Human URL:** [https://developer.token.io/](https://developer.token.io/)

#### Tags

- Confirmation of Funds
- CBPII
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-standard-confirmation-funds-openapi.yaml) — shared OBIE standard specification (not a Tandem-proprietary contract)
- [Documentation](https://developer.token.io/)
- [API Reference](https://github.com/OpenBankingUK/read-write-api-specs)

## Common Properties

- [Website](https://www.tandem.co.uk/)
- [Open Banking](https://www.tandem.co.uk/save/open-banking-page)
- [Developer Portal](https://developer.token.io/)
- [API Standard](https://github.com/OpenBankingUK/read-write-api-specs)
- [LinkedIn](https://www.linkedin.com/company/tandem-bank/)
- [Blog](https://www.tandem.co.uk/blog)
- [Newsroom](https://www.tandem.co.uk/newsroom)
- [Support](https://www.tandem.co.uk/support)
- [Privacy Notice](https://www.tandem.co.uk/privacy-notice)
- [About](https://www.tandem.co.uk/about)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
