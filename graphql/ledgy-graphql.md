# Ledgy GraphQL API

[Ledgy](https://www.ledgy.com/) is a European equity-management platform for cap tables,
ESOP/equity plans, stakeholder and investor relations, and financing rounds. Unlike many
catalog entries where the GraphQL schema is conceptual, **Ledgy ships a real, native
GraphQL API** — it is the only programmatic interface Ledgy publishes.

**Endpoint:** `https://app.ledgy.com/graphql` (POST, `application/json`)
**Authentication:** `Authorization: Bearer <apiKey>` — the API key is revealed from your
company's general settings page in the Ledgy app ("Reveal API key" in the danger-zone card).
**Documentation:** <https://docs.ledgy.com/>

- Reference: <https://docs.ledgy.com/>
- Schema: [`ledgy-schema.graphql`](./ledgy-schema.graphql) — representative SDL (noted)
- Rate limit: 20 requests per 5 seconds, per company

> The schema in [`ledgy-schema.graphql`](./ledgy-schema.graphql) is a **representative**
> reconstruction from Ledgy's public API reference. It mirrors the documented query surface
> and the Convertible / Grant / Transfer transaction union but is not an authoritative
> introspection dump; field nullability and the full field inventory may differ from the
> live schema. The API is **read-only** — no mutations are documented.

---

## Overview

The Ledgy GraphQL API is split into two scopes:

- **Company scope** — operates on the company that owns the API token: `auth`,
  `companyCaptable`, `companyTransactions`.
- **Portfolio scope** — operates on a portfolio company by `companyId` (for investors /
  fund admins): `portfolioCaptable`, `portfolioPerformance`, `portfolioTransactions`.

A typical first call is `auth`, which echoes back the `companyId` and `companyName` the
token is bound to. Cap-table queries can be aggregated with `groupBy` (stakeholder, share
class, captable group, or grant) and snapshotted with an as-of `date`. Transaction queries
return a union of `Convertible`, `Grant`, and `Transfer` records, filterable by
`TransactionType` and `date`.

---

## Type inventory

### Scalars
| Scalar | Purpose |
|--------|---------|
| `Date` | Calendar date (`YYYY-MM-DD`), used for as-of snapshots and schedule dates |
| `DateTime` | ISO-8601 timestamp, used for `lastUpdatedAt` |

### Enums
| Enum | Values |
|------|--------|
| `CaptableGroupBy` | stakeholderName, shareClassName, captableGroup, grantName |
| `TransactionType` | convertible, grant, transfer |
| `VestingOnType` | grantDate, startDate, firstOfMonth, lastOfMonth |

### Object types
| Type | Purpose |
|------|---------|
| `Auth` | Authenticated company context (companyId, companyName) |
| `CaptableRow` | One aggregated cap-table row; dimension depends on `groupBy` |
| `CompanyCaptableResult` / `PortfolioCaptableResult` | `rows: [CaptableRow!]!` wrapper |
| `Vesting` | Vesting schedule (type, start, duration, interval, cliff, vestingOn) |
| `Convertible` | Convertible loan / financing instrument (investment, interest, cap, discount, maturity) |
| `Grant` | ESOP / equity-plan grant (grantType, granted, vested, strikePrice, vesting, equityPlanName) |
| `Transfer` | Share transfer between stakeholders (from/to, proceeds, sharePrice) |
| `Transaction` | Union of `Convertible \| Grant \| Transfer` |
| `CompanyTransactionsResult` / `PortfolioTransactionsResult` | `rows: [Transaction!]!` wrapper |
| `PortfolioPerformanceRow` | Per-company investment performance (irr, multiple, investment, value) |
| `PortfolioPerformanceResult` | `rows: [PortfolioPerformanceRow!]!` wrapper |

---

## Query examples

### Resolve the authenticated company

```graphql
query {
  auth {
    companyId
    companyName
  }
}
```

### Cap table grouped by stakeholder

```graphql
query {
  companyCaptable(groupBy: [stakeholderName]) {
    rows {
      stakeholderName
      stakeholderEmail
      shareClassName
      issued
      diluted
      vested
      fullyDilutedOwnership
      value
    }
  }
}
```

### Cap table grouped by share class, as of a date

```graphql
query {
  companyCaptable(groupBy: [shareClassName], date: "2026-01-01") {
    rows {
      shareClassName
      issued
      diluted
      votingOwnership
      value
    }
  }
}
```

### List ESOP grants

```graphql
query {
  companyTransactions(types: [grant]) {
    rows {
      ... on Grant {
        transactionId
        grantType
        stakeholderName
        granted
        grantVested
        strikePrice
        equityPlanName
        vesting {
          type
          startDate
          duration
          cliff
          vestingOn
        }
      }
    }
  }
}
```

### List financing-round convertibles

```graphql
query {
  companyTransactions(types: [convertible]) {
    rows {
      ... on Convertible {
        transactionId
        stakeholderName
        investment
        interestRate
        cap
        discount
        maturityDate
      }
    }
  }
}
```

### Portfolio performance (investor view)

```graphql
query {
  portfolioPerformance {
    rows {
      companyName
      industry
      irr
      multiple
      investment
      value
    }
  }
}
```

### Raw HTTP request

```bash
curl --request POST \
  --header 'content-type: application/json' \
  --header 'Authorization: Bearer <apiKey>' \
  --url 'https://app.ledgy.com/graphql' \
  --data '{"query":"{ auth { companyId companyName } }"}'
```
