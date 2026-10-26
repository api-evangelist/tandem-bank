# Tandem Bank (tandem-bank)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
