# Bank of Tanzania Exchange Rates API — bank-of-tanzania-exchange-rate

[![npm version](https://img.shields.io/npm/v/bank-of-tanzania-exchange-rate.svg)](https://www.npmjs.com/package/bank-of-tanzania-exchange-rate)
[![license](https://img.shields.io/npm/l/bank-of-tanzania-exchange-rate.svg)](https://github.com/AllRates-Today/bank-of-tanzania-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/bank-of-tanzania-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/TZS today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbotz%3Fsource%3DUSD%26target%3DTZS&query=%24.rate&label=USD%2FTZS%20published%20by%20Bank%20of%20Tanzania&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/botz/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbotz%3Fsource%3DUSD%26target%3DTZS&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/botz/)

**Official Bank of Tanzania (Tanzania) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Bank of Tanzania itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Bank of Tanzania's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2010** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Bank of Tanzania itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Bank of Tanzania table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/botz?source=USD&target=TZS"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/botz').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full Bank of Tanzania table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-09** by Bank of Tanzania — 113 rates, first 60 shown. Updated 2026-10-09.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | TZS | buy | 712.8028 |
| AED | TZS | reference | 716.3668 |
| AED | TZS | sell | 719.9309 |
| AUD | TZS | buy | 1819.6958 |
| AUD | TZS | reference | 1828.7943 |
| AUD | TZS | sell | 1837.8928 |
| BIF | TZS | buy | 0.8688 |
| BIF | TZS | reference | 0.8732 |
| BIF | TZS | sell | 0.8775 |
| BWP | TZS | buy | 200.5593 |
| BWP | TZS | reference | 201.5621 |
| BWP | TZS | sell | 202.5649 |
| CAD | TZS | buy | 1835.1912 |
| CAD | TZS | reference | 1844.3672 |
| CAD | TZS | sell | 1853.5431 |
| CHF | TZS | buy | 3139.4093 |
| CHF | TZS | reference | 3155.1063 |
| CHF | TZS | sell | 3170.8034 |
| CNY | TZS | buy | 390.6404 |
| CNY | TZS | reference | 392.5936 |
| CNY | TZS | sell | 394.5468 |
| DKK | TZS | buy | 391.9269 |
| DKK | TZS | reference | 393.8865 |
| DKK | TZS | sell | 395.8461 |
| DZD | TZS | buy | 19.3666 |
| DZD | TZS | reference | 19.4634 |
| DZD | TZS | sell | 19.5603 |
| EUR | TZS | buy | 2929.8411 |
| EUR | TZS | reference | 2944.4903 |
| EUR | TZS | sell | 2959.1396 |
| GBP | TZS | buy | 3458.993 |
| GBP | TZS | reference | 3476.2879 |
| GBP | TZS | sell | 3493.5829 |
| HKD | TZS | buy | 333.635 |
| HKD | TZS | reference | 335.3032 |
| HKD | TZS | sell | 336.9713 |
| IDR | TZS | buy | 0.1463 |
| IDR | TZS | reference | 0.147 |
| IDR | TZS | sell | 0.1477 |
| INR | TZS | buy | 27.051 |
| INR | TZS | reference | 27.1863 |
| INR | TZS | sell | 27.3215 |
| IQD | TZS | buy | 1.7225 |
| IQD | TZS | sell | 1.7398 |
| IRR | TZS | buy | 0.0015 |
| IRR | TZS | reference | 0.0015 |
| IRR | TZS | sell | 0.0015 |
| JPY | TZS | buy | 16.5504 |
| JPY | TZS | reference | 16.6331 |
| JPY | TZS | sell | 16.7159 |
| KES | TZS | buy | 20.1483 |
| KES | TZS | reference | 20.249 |
| KES | TZS | sell | 20.3497 |
| KRW | TZS | buy | 1.9502 |
| KRW | TZS | reference | 1.96 |
| KRW | TZS | sell | 1.9698 |
| KWD | TZS | buy | 8495.3515 |
| KWD | TZS | reference | 8537.8282 |
| KWD | TZS | sell | 8580.305 |
| MWK | TZS | buy | 1.4953 |

[Full table on the Bank of Tanzania rates page](https://allratestoday.com/central-bank-rates-api/botz/) · Source: [Official rates published by BOTZ, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/botz/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install bank-of-tanzania-exchange-rate
```

```bash
yarn add bank-of-tanzania-exchange-rate
```

```bash
pnpm add bank-of-tanzania-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/bank-of-tanzania-exchange-rate`](https://www.npmjs.com/package/@allratestoday/bank-of-tanzania-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'bank-of-tanzania-exchange-rate';

const pair = await getRate('USD', 'TZS', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Bank of Tanzania rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'TZS', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'botz',
  name: 'Bank of Tanzania',
  rate_date: '2026-10-08',   // Bank of Tanzania's own publication date
  source: 'USD',
  target: 'TZS',
  rate: 2633.6771,
  rate_type: 'reference',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'bank-of-tanzania-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'botz',
  name: 'Bank of Tanzania',
  rate_date: '2026-10-08',
  rates: [
    { "base": "USD", "quote": "TZS", "type": "reference", "value": 2633.6771 },
    { "base": "USD", "quote": "TZS", "type": "sell", "value": 2646.78 },
    { "base": "USD", "quote": "TZS", "type": "buy", "value": 2620.5743 },
    // … the rest of the published table (38 currencies vs TZS)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2010 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'bank-of-tanzania-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'TZS' });
```

**Response:**

```javascript
{
  bank: 'botz',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'bank-of-tanzania-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'TZS', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'botz',
  source: 'USD',
  target: 'TZS',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 2633.6771, rate_type: 'reference', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Bank of Tanzania currently publishes rates covering **38 currencies** against the TZS (as of the latest table):

🇦🇪 `AED` · 🇦🇺 `AUD` · 🇧🇮 `BIF` · 🇧🇼 `BWP` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNY` · 🇩🇰 `DKK` · 🇩🇿 `DZD` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇭🇰 `HKD` · 🇮🇩 `IDR` · 🇮🇳 `INR` · 🇮🇶 `IQD` · 🇮🇷 `IRR` · 🇯🇵 `JPY` · 🇰🇪 `KES` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇲🇼 `MWK` · 🇲🇾 `MYR` · 🇳🇦 `NAD` · 🇳🇬 `NGN` · 🇳🇴 `NOK` · 🇳🇿 `NZD` · 🇵🇰 `PKR` · 🇶🇦 `QAR` · 🇷🇼 `RWF` · 🇸🇦 `SAR` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇹🇷 `TRY` · 🇺🇬 `UGX` · 🇺🇸 `USD` · `XDR` · 🇿🇦 `ZAR` · 🇿🇲 `ZMW`

## 🏛️ Source

The Bank of Tanzania publishes daily indicative shilling rates — mean, buying and selling — for about 40 currencies, including the East African Community pairs. It is the official reference for Tanzanian banks, customs valuation and business accounting.

- Publisher's own page: [Indicative exchange rates](https://www.bot.go.tz/ExchangeRate/excRates) · [www.bot.go.tz](https://www.bot.go.tz)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Bank of Tanzania rates page](https://allratestoday.com/central-bank-rates-api/botz/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Bank of Tanzania quotes **TZS per 1 unit of foreign currency** (e.g. `base: "USD", quote: "TZS"` means TZS per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`reference` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Bank of Tanzania rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/botz/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('botz')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate botz ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Bank of Tanzania does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via TZS from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Bank of Tanzania |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'bank-of-tanzania-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('bank-of-tanzania-exchange-rate');

getRate('USD', 'TZS', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2010 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/botz.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/botz/latest.json`

## 🔗 Links

- [Bank of Tanzania rates page](https://allratestoday.com/central-bank-rates-api/botz/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/bank-of-tanzania-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/bank-of-tanzania-exchange-rate)

## 📜 License

MIT
