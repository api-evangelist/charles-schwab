# Charles Schwab (charles-schwab)

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

Charles Schwab is a financial services company providing brokerage, banking, asset management, and financial advisory services to individual investors and independent investment advisors. The Schwab Developer Portal exposes Trader APIs that let registered applications access account balances, positions, and orders, place equity and option trades, and consume real-time and historical market data through OAuth 2.0-secured REST endpoints.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/charles-schwab/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/charles-schwab/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Accounts
- Banking
- Brokerage
- Financial Services
- Investing
- Market Data
- OAuth 2.0
- Orders
- Trading

## Timestamps

- **Created:** 2026-03-21
- **Modified:** 2026-05-19

## APIs

### Charles Schwab Trader API

The Schwab Trader API provides authenticated access to retail brokerage accounts. Applications can list linked accounts, retrieve balances and positions, fetch and cancel orders, place new orders for equities and options, retrieve transactions, and stream account activity.

- **Human URL:** [https://developer.schwab.com/products/trader-api--individual](https://developer.schwab.com/products/trader-api--individual)
- **Base URL:** `https://api.schwabapi.com/trader/v1`

#### Tags

- Accounts
- Brokerage
- Orders
- Trading
- Transactions

#### Properties

- [Documentation](https://developer.schwab.com/products/trader-api--individual)
- [Getting Started](https://developer.schwab.com/user-guides/get-started)
- [Authentication](https://developer.schwab.com/user-guides/get-started/authenticate-with-oauth)
- [OpenAPI](openapi/charles-schwab-trader-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/charles-schwab-trader-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/charles-schwab-trader-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Spectral Rules](spectral/charles-schwab-spectral.yml) — [Spectral](https://docs.stoplight.io/docs/spectral)

### Charles Schwab Market Data API

The Schwab Market Data API exposes real-time and historical quotes, option chains, price history, market hours, instrument metadata, and daily movers for the major US indices, supporting market analytics and trading decision tools.

- **Human URL:** [https://developer.schwab.com/products/trader-api--individual](https://developer.schwab.com/products/trader-api--individual)
- **Base URL:** `https://api.schwabapi.com/marketdata/v1`

#### Tags

- Equities
- Market Data
- Options
- Quotes

#### Properties

- [Documentation](https://developer.schwab.com/products/trader-api--individual)
- [Authentication](https://developer.schwab.com/user-guides/get-started/authenticate-with-oauth)
- [OpenAPI](openapi/charles-schwab-market-data-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/charles-schwab-market-data-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/charles-schwab-market-data-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/charles-schwab)
- [Website](https://www.schwab.com)
- [Developer Portal](https://developer.schwab.com/)
- [Documentation](https://developer.schwab.com/user-guides)
- [Authentication](https://developer.schwab.com/user-guides/get-started/authenticate-with-oauth)
- [Sign Up](https://developer.schwab.com/register)
- [Dashboard](https://developer.schwab.com/dashboard)
- [Support](https://developer.schwab.com/contact-us)
- [Terms of Service](https://developer.schwab.com/terms)
- [Privacy Policy](https://www.schwab.com/legal/online-privacy)
- [JSON-LD](json-ld/charles-schwab-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [JSON Schema](json-schema/charles-schwab-account-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/charles-schwab-order-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/charles-schwab-quote-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [L L Ms Txt](https://developer.schwab.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
