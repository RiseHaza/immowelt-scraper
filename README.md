[Immowelt Scraper](https://apify.com/blackfalcondata/immowelt-scraper?fpr=data)

## What does Immowelt Scraper do?

Immowelt Scraper extracts structured property data from [immowelt.de](https://immowelt.de) — including pricing data, contact details (email, apply URL), company metadata, full descriptions, and location data. It supports keyword search, location filters, and controllable result limits, so you can run the same query consistently over time. The actor also offers detail enrichment (full descriptions, company profiles, and contact information) where the source provides them.

**New to Apify?** [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) and use the included $5 monthly platform credit to test this actor.

## Key features

- **Incremental mode** — recurring runs emit and charge only for listings that are new or whose tracked content changed. First run builds the baseline state; subsequent runs emit only new or changed records.
- **Detail enrichment** — full descriptions, company profiles, and contact information where the source provides them.
- **Compact mode** — AI-agent and MCP-friendly payloads with core fields only.
- **🔔 Notifications** — Telegram, Slack, Discord, WhatsApp Cloud API, generic webhook. Pair with incremental for daily "new Immowelt listings" alerts.

## What data can you extract from immowelt.de?

Each result includes Core listing fields (`jobId`, `jobKey`, `title`, `location`, `street`, `district`, `postalCode`, and `salaryText`, and more), detail fields when enrichment is enabled (`description`, `descriptionHtml`, `descriptionLength`, and `detailFetched`), contact and apply information (`contactPhone`, `applyUrl`, and `extractedEmails`), and company metadata (`company` and `companyUrl`). In standard mode, all fields are always present — unavailable data points are returned as `null`, never omitted. In compact mode, only core fields are returned.

Enable detail enrichment in the input to get richer fields such as full descriptions, company profiles, and contact information where the source provides them.

## Input

The main inputs are a search keyword, an optional location filter, and a result limit. Additional filters and options are available in the input schema.

Key parameters:

- **`query`** — Property search keywords. Use JSON array for multi-query. Leave empty when using startUrls only.
- **`country`** — Which immowelt.de market to search. (default: `"DE"`)
- **`city`** — City or region to search in (e.g. "Berlin", "München"). Use JSON array for multiple cities. Recommended over 'query' for location-based searches.
- **`distributionType`** — Filter by buy, rent, or both. (default: `"buy"`)
- **`estateType`** — Filter by property type. (default: `"apartment_and_house"`)
- **`radiusKm`** — Extend search beyond the city boundary by this many kilometres. Requires 'city' input. 0 = city boundary only. (default: `0`)
- **`location`** — Legacy field. Use 'city' instead.
- **`startUrls`** — Direct Immowelt search URLs or expose URLs.
- **`maxResults`** — Maximum total property listings to return (0 = unlimited). Dynamic memory profile: up to 25 results uses 1024 MB, 26+ results uses 2048 MB. (default: `25`)
- **`maxPages`** — Maximum search-result pages to scrape per search source. (default: `5`)
- **`includeDetails`** — Fetch each expose page for full description, price data, and provider info. (default: `true`)
- **`transport`** — Choose the standard fetch mode or browser mode for tougher pages. (default: `"browser"`)
- ...and 21 more parameters

## Input examples

**Basic search** — Keyword-driven search with a result cap.

→ Full payload per result — all standard fields populated where the source provides them.

```
{
  "query": "altbau balkon",
  "maxResults": 50
}
```

**Incremental tracking** — Only emit jobs that changed since the previous run with this `stateKey`.

→ First run builds the baseline state. Subsequent runs emit only records that are new or whose tracked content changed. Set `emitUnchanged: true` to include unchanged records as well.

```
{
  "query": "altbau balkon",
  "maxResults": 200,
  "incrementalMode": true,
  "stateKey": "altbau-balkon-tracker"
}
```

**Compact output for AI agents** — Return only core fields for AI-agent and MCP workflows.

→ Small payload with the most important fields — ideal for piping into LLMs without token overhead.

```
{
  "query": "altbau balkon",
  "maxResults": 50,
  "compact": true
}
```

## Output

Each run produces a dataset of structured property records. Results can be downloaded as JSON, CSV, or Excel from the Dataset tab in Apify Console.

## Example property record

```
{
  "jobId": "676e69dc0aef38d4f6646e63fc843a97640f326a4f8678dd9c346029fb143271",
  "jobKey": "22fd0ea2-0cbe-42a2-86e3-3a2082b4aa93",
  "title": "Diese gepflegte 3-Zimmer-Etagenwohnung befindet sich im 1. Obergeschoss eines im Jahr 1926 in solider Massivbauweise err",
  "company": "Herr Tobias Gruschla",
  "companyUrl": "https://www.immowelt.de/profil/39c37594d05c416095d0485812f037c6",
  "location": "Berlin",
  "street": "Pichelsdorfer Straße 30",
  "district": "Spandau",
  "postalCode": "13595",
  "description": "Diese gepflegte 3-Zimmer-Etagenwohnung befindet sich im 1. Obergeschoss eines im Jahr 1926 in solider Massivbauweise errichteten Mehrfamilienhauses, welches zur historischen Siedlung Birkenwäldchen ge...",
  "descriptionHtml": "Diese gepflegte 3-Zimmer-Etagenwohnung befindet sich im 1. Obergeschoss eines im Jahr 1926 in solider Massivbauweise errichteten Mehrfamilienhauses, welches zur historischen Siedlung Birkenwäldchen ge...",
  "descriptionLength": 4467,
  "salaryText": "255000 EUR",
  "salaryMin": 255000,
  "salaryMax": 255000,
  "salaryCurrency": "EUR",
  "salaryType": null,
  "rooms": 3,
  "areaSqm": 62.63,
  "pricePerSqm": 4071.53,
  "propertyType": "APARTMENT",
  "marketingType": "BUY",
  "contactPhone": null,
  "latitude": 52.516151428222656,
  "longitude": 13.197739601135254
}
```

## Incremental fields

When `incremental: true`, each record also carries:

- `changeType` — one of `NEW`, `UPDATED`, `UNCHANGED`, `REAPPEARED`, `EXPIRED`. Default output covers `NEW` / `UPDATED` / `REAPPEARED`; set `emitUnchanged: true` or `emitExpired: true` to opt into the others.
- `firstSeenAt`, `lastSeenAt` — ISO-8601 timestamps tracking the listing across runs.
- `isRepost`, `repostOfId`, `repostDetectedAt` — populated when a new listing matches the tracked content of a previously expired one. Set `skipReposts: true` to drop detected reposts from the output.

## How to scrape immowelt.de

1. Go to [Immowelt Scraper](https://apify.com/blackfalcondata/immowelt-scraper?fpr=1h3gvi) in Apify Console.
2. Enter a search keyword and optional location filter.
3. Set `maxResults` to control how many results you need.
4. Enable `includeDetails` if you need full descriptions, contact info, or company data.
5. Click **Start** and wait for the run to finish.
6. Export the dataset as JSON, CSV, or Excel.

## Use cases

- Extract property data from immowelt.de for market research and competitive analysis.
- Track pricing trends across regions and categories over time.
- Monitor new and changed listings on scheduled runs without processing the full dataset every time.
- Build outreach lists using contact details and apply URLs from listings.
- Research broker and agency profiles, provider coverage, and market distribution.
- Use structured location data for regional analysis, mapping, and geo-targeting.
- Feed structured data into AI agents, MCP tools, and automated pipelines using compact mode.
- Export clean, structured data to dashboards, spreadsheets, or data warehouses.

## How much does it cost to scrape immowelt.de?

Immowelt Scraper uses [pay-per-event](https://docs.apify.com/platform/actors/paid-actors/pay-per-event) pricing. You pay a small fee when the run starts and then for each result that is actually produced.

- **Run start:** $0.005 per run
- **Per result:** $0.0009 per property record

Example costs:

- 10 results: **$0.01**
- 100 results: **$0.1**
- 500 results: **$0.46**

### Example: recurring monitoring savings

These examples compare full re-scrapes with incremental runs at different churn rates. Churn is the share of listings that are new or whose tracked content changed since the previous run. Actual churn depends on your query breadth, source activity, and polling frequency — the scenarios below are examples, not predictions.

Example setup: 100 results per run, daily polling (30 runs/month). Event-pricing examples scale linearly with result count.

| Churn rate | Full re-scrape run cost | Incremental run cost | Savings vs full re-scrape | Monthly cost after baseline |
| --- | --- | --- | --- | --- |
| 5% — stable niche query | $0.10 | $0.0095 | $0.09 (90%) | $0.28 |
| 15% — moderate broad query | $0.10 | $0.02 | $0.08 (81%) | $0.55 |
| 30% — high-volume aggregator | $0.10 | $0.03 | $0.06 (66%) | $0.96 |

Full re-scrape monthly cost at daily polling: $2.85. First month with incremental costs $0.37 / $0.63 / $1.02 for the 5% / 15% / 30% scenarios because the first run builds baseline state at full cost before incremental savings apply.

Platform usage (compute and proxies) is billed separately by Apify based on actual consumption. Incremental runs consume less on result processing, though fixed per-run overhead stays the same.

 

## FAQ

### How many results can I get from immowelt.de?

The number of results depends on the search query and available listings on immowelt.de. Use the `maxResults` parameter to control how many results are returned per run.

### Does Immowelt Scraper support recurring monitoring?

Yes. Enable incremental mode to only receive new or changed listings on subsequent runs. This is ideal for scheduled monitoring where you want to track changes over time without re-processing the full dataset.

### Can I integrate Immowelt Scraper with other apps?

Yes. Immowelt Scraper works with Apify's [integrations](https://apify.com/integrations?fpr=1h3gvi) to connect with tools like Zapier, Make, Google Sheets, Slack, and more. You can also use webhooks to trigger actions when a run completes.

### Can I use Immowelt Scraper with the Apify API?

Yes. You can start runs, manage inputs, and retrieve results programmatically through the [Apify API](https://docs.apify.com/api/v2). Client libraries are available for JavaScript, Python, and other languages.

### Can I use Immowelt Scraper through an MCP Server?

Yes. Apify provides an [MCP Server](https://apify.com/apify/actors-mcp-server?fpr=1h3gvi) that lets AI assistants and agents call this actor directly. Use compact mode and `descriptionMaxLength` to keep payloads manageable for LLM context windows.

### Is it legal to scrape immowelt.de?

This actor extracts publicly available data from immowelt.de. Web scraping of public information is generally considered legal, but you should always review the target site's terms of service and ensure your use case complies with applicable laws and regulations, including GDPR where relevant.

### Your feedback

If you have questions, need a feature, or found a bug, please [open an issue](https://apify.com/blackfalcondata/immowelt-scraper/issues?fpr=1h3gvi) on the actor's page in Apify Console. Your feedback helps us improve.

## You might also like

- [Actiris Brussels Job Scraper](https://apify.com/blackfalcondata/actiris-scraper?fpr=1h3gvi) — Scrape all active job listings from actiris.brussels — official Brussels public employment service..
- [Adzuna Job Scraper — Global Jobs with Salary & Coordinates](https://apify.com/blackfalcondata/adzuna-scraper?fpr=1h3gvi) — Scrape adzuna.com job listings across 19 country markets with structured salary data.
- [APEC.fr Scraper - French Executive Jobs](https://apify.com/blackfalcondata/apec-scraper?fpr=1h3gvi) — Scrape apec.fr - French executive job listings with salary ranges, company, location, skills,.
- [Arbeitsagentur Jobs Feed — German Federal Employment Agency](https://apify.com/blackfalcondata/arbeitsagentur-jobs-feed?fpr=1h3gvi) — Extract job listings from arbeitsagentur.de — Germany's official public employment portal with 1M+.
- [Arbeitsagentur Scraper - German Jobs](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Scrape arbeitsagentur.de - Germany’s official employment portal with 1M+ listings. Contact data,.
- [Arbetsformedlingen Job Scraper](https://apify.com/blackfalcondata/arbetsformedlingen-scraper?fpr=1h3gvi) — Scrape arbetsformedlingen.se (Platsbanken) — Sweden's official employment portal. Returns 84.
- [AutoScout24 Scraper](https://apify.com/blackfalcondata/autoscout24-scraper?fpr=1h3gvi) — Scrape autoscout24.com - Europe's largest used car marketplace with 770K+ listings. Structured.
- [Bayt.com Scraper - Jobs from the Middle East](https://apify.com/blackfalcondata/bayt-scraper?fpr=1h3gvi) — Scrape bayt.com - the leading Middle East job board. Salary data, experience requirements.

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. Sign up — $5 platform credit included
2. Open this actor and configure your input
3. Click **Start** — export results as JSON, CSV, or Excel

Need more later? [See Apify pricing](https://apify.com/pricing?fpr=1h3gvi).