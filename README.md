# Ledgy (ledgy)

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
