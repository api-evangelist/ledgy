# Ledgy (ledgy)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Ledgy is a European equity-management platform for cap tables, ESOP/equity plans, stakeholder and investor relations, and financing rounds. The Ledgy GraphQL API exposes a company's cap table, transactions (convertibles, grants, transfers), share classes, financing rounds, ESOP grants, and portfolio data through a single Bearer-authenticated endpoint at https://app.ledgy.com/graphql.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ledgy/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ledgy/refs/heads/main/apis.yml)

## Tags

- Equity Management
- Cap Table
- ESOP
- Stakeholders
- GraphQL

## Timestamps

- **Created:** 2026-06-21
- **Modified:** 2026-06-21

## APIs

### Ledgy Companies API

Resolve the authenticated company context (company ID and name) for the supplied API token via the auth query, the entry point for all company-scoped Ledgy GraphQL operations.

- **Human URL:** [https://docs.ledgy.com/](https://docs.ledgy.com/)
- **Base URL:** `https://app.ledgy.com/graphql`

#### Tags

- Companies
- Authentication
- GraphQL

#### Properties

- [Documentation](https://docs.ledgy.com/)
- [API Reference](https://docs.ledgy.com/)
- [OpenAPI](openapi/ledgy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/ledgy-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Postman Collection](collections/ledgy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/ledgy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ledgy Stakeholders API

Read stakeholder-level cap table rows via companyCaptable grouped by stakeholderName - ownership percentages, issued, diluted, vested and exercised share counts, and stakeholder metadata.

- **Human URL:** [https://docs.ledgy.com/](https://docs.ledgy.com/)
- **Base URL:** `https://app.ledgy.com/graphql`

#### Tags

- Stakeholders
- Cap Table
- GraphQL

#### Properties

- [Documentation](https://docs.ledgy.com/)
- [OpenAPI](openapi/ledgy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/ledgy-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Postman Collection](collections/ledgy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/ledgy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ledgy Transactions API

List company transactions via companyTransactions, returning a typed union of Convertible, Grant, and Transfer records filterable by transaction type and an as-of date.

- **Human URL:** [https://docs.ledgy.com/](https://docs.ledgy.com/)
- **Base URL:** `https://app.ledgy.com/graphql`

#### Tags

- Transactions
- Convertibles
- Transfers
- GraphQL

#### Properties

- [Documentation](https://docs.ledgy.com/)
- [OpenAPI](openapi/ledgy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/ledgy-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Postman Collection](collections/ledgy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/ledgy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ledgy Share Classes API

Aggregate the cap table by share class via companyCaptable grouped by shareClassName, exposing per-class share counts, ownership, and value.

- **Human URL:** [https://docs.ledgy.com/](https://docs.ledgy.com/)
- **Base URL:** `https://app.ledgy.com/graphql`

#### Tags

- Share Classes
- Cap Table
- GraphQL

#### Properties

- [Documentation](https://docs.ledgy.com/)
- [OpenAPI](openapi/ledgy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/ledgy-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Postman Collection](collections/ledgy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/ledgy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ledgy Financing Rounds API

Surface financing-round and convertible-instrument detail through companyTransactions filtered to the convertible type - investment, interest, valuation cap, discount, and maturity.

- **Human URL:** [https://docs.ledgy.com/](https://docs.ledgy.com/)
- **Base URL:** `https://app.ledgy.com/graphql`

#### Tags

- Financing Rounds
- Convertibles
- GraphQL

#### Properties

- [Documentation](https://docs.ledgy.com/)
- [OpenAPI](openapi/ledgy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/ledgy-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Postman Collection](collections/ledgy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/ledgy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ledgy ESOP and Grants API

Read ESOP / equity-plan grant detail via companyTransactions filtered to the grant type - grant type, granted and vested shares, strike price, vesting schedule, and equity plan name.

- **Human URL:** [https://docs.ledgy.com/](https://docs.ledgy.com/)
- **Base URL:** `https://app.ledgy.com/graphql`

#### Tags

- ESOP
- Grants
- Vesting
- GraphQL

#### Properties

- [Documentation](https://docs.ledgy.com/)
- [OpenAPI](openapi/ledgy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/ledgy-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Postman Collection](collections/ledgy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/ledgy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/ledgy)
- [LinkedIn](https://www.linkedin.com/company/ledgy)
- [Website](https://www.ledgy.com/)
- [Documentation](https://docs.ledgy.com/)
- [Plans](plans/ledgy-plans-pricing.yml)
- [Rate Limits](rate-limits/ledgy-rate-limits.yml)
- [Fin Ops](finops/ledgy-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
