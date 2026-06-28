[Immowelt Scraper](https://apify.com/igolaizola/immowelt-scraper?fpr=data)

Scrape public property listings from **Immowelt** in Germany and export them as clean data for **market research, lead generation, price tracking, and investment analysis**.

This actor is designed for both:

- **Non-technical users** who want ready-to-download data in Apify.
- **Data teams** that need structured JSON/CSV via API.

## ✅ What does this actor do?

The actor searches Immowelt listing result pages and returns structured records for properties such as:

- Apartments (`Wohnung`)
- Houses (`Haus`)
- Plots (`Grundstueck`)
- Parking / garage
- Commercial categories (selected combinations)

It supports:

- Location search (city / district / postcode style queries)
- Direct property fetch by explicit property IDs
- Buy or rent mode
- Rich filters (price, rooms, space, energy class, etc.)
- Optional listing details under `_details`
- Pagination up to your `maxItems`

## 🏠 Use cases

- **Real estate market monitoring** in Germany
- **Immowelt price tracking** by city and property type
- **Lead generation** for agencies and investors
- **Property dataset creation** for BI dashboards and alerts
- **Competitor and supply analysis** for PropTech teams

## 🚀 How to use

1. Open the actor in Apify and click **Try for free**.
2. Set these 3 fields first:

- `maxItems` (how many listings you want)
- `location` (for example: `Berlin`, `Hamburg`, `Muenchen`) or `locationID`
- `operation` (`buy` or `rent`)

1. Optionally add filters (price, rooms, space, estate type).
2. Run the actor.
3. Download results from **Dataset** as JSON/CSV/Excel.

## 🧾 Input parameters

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `maxItems` | integer | Yes | Maximum number of listings to return. Above 570 items, the actor automatically uses a price sort. |
| `properties` | array | No | List of explicit Immowelt property IDs. When set, location and filters are ignored and each item includes `_details`. |
| `location` | string | No* | Search location text (city, district, postcode, etc.). |
| `locationID` | string | No* | Optional single location ID. Can be used by itself. |
| `operation` | string | No | `buy` or `rent`. |
| `estateType` | string | No | Main property family (e.g., `APARTMENT`, `HOUSE`, `PLOT`). |
| `order` | string | No | Sorting (`Default` or `DateDesc`). Above 570 items, non-price sorts are automatically overridden. |
| `fetchDetails` | boolean | No | If `true`, adds `_details` with full detail payload per listing. |

### Common Filters

- `minPrice`, `maxPrice`
- `minRooms`, `maxRooms`
- `minSpace`, `maxSpace`
- `energyScores`
- `features`
- `subEstateTypes`
- `classifiedBusiness`

### Property IDs mode

If you already know listing IDs, use `properties` and skip search filters.

```
{
  "maxItems": 2,
  "properties": [
    "251KK5W8ERLI",
    "26PD7QUELGE1"
  ]
}
```

In this mode:

- `location`, `locationID`, and all filters are ignored.
- Results are fetched directly by ID.
- Each output item includes `_details`.

### Example Input

```
{
  "maxItems": 100,
  "location": "Berlin",
  "operation": "buy",
  "estateType": "APARTMENT",
  "minPrice": 250000,
  "maxPrice": 900000,
  "minRooms": 2,
  "maxRooms": 5,
  "minSpace": 55,
  "order": "DateDesc",
  "fetchDetails": false,
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": ["RESIDENTIAL"]
  }
}
```

## 📊 Output Data

Each dataset item is a listing object (Immowelt payload) with a convenience image field:

- `id`
- `type`
- `mainDescription.headline`
- `mainDescription.description`
- `hardFacts.price.formatted`
- `rawData.price`, `rawData.nbroom`, `rawData.surface.main`
- `location.address.city`, `location.address.zipCode`, `location.address.street`
- `rawData.propertyType`, `rawData.distributionType`
- `provider.publisherType`, `cardProvider.title`
- `url`
- `_image` (first gallery image URL, added by this actor)
- `_details` (only when `fetchDetails=true`)

## ⚠️ Notes and tips

- `fetchDetails=false` is faster and cheaper.
- `fetchDetails=true` enriches each record with `_details`, useful for deeper analysis.
- Above 570 items, the actor automatically switches to a price sort.
- Use specific `location` terms for better relevance (district > city center > broad region).
- For trend monitoring, keep filters stable and run periodically.
- For broad discovery, start with fewer filters and higher `maxItems`.
- Provide either `properties` or (`location`/`locationID`) depending on your workflow.

## ⚖️ Legal

Use responsibly and comply with applicable laws, website terms, and data regulations (including GDPR where relevant).

This actor is an independent tool and is **not affiliated with or endorsed by Immowelt**.