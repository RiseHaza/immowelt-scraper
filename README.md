[Immowelt Scraper](https://apify.com/ninhothedev/immowelt-scraper?fpr=data)

# Immowelt Scraper

Extract structured real estate data from **Immowelt.de** – one of Germany's largest property portals with millions of monthly visitors. Get apartments, houses, and plots for sale or rent across all German cities, filtered precisely to your criteria.

> **Reliable & stealthy.** Uses headless browser automation with full consent handling and anti-detection measures. Streams results page by page directly into your Apify dataset.

---

## What you get

Each listing is returned as a clean JSON record with up to 33 fields:

| Field | Type | Description |
| --- | --- | --- |
| `title` | String | Listing headline |
| `price` | Number | Base price in € (Kaltmiete or Kaufpreis) |
| `price_type` | String | `kauf` (buy) or `miete` (rent) |
| `property_type` | String | `wohnung`, `haus`, or `grundstueck` |
| `rooms` | Number | Number of rooms |
| `area_sqm` | Number | Living area in m² |
| `plot_sqm` | Number | Plot area in m² (houses/plots) |
| `additional_costs` | Number | Nebenkosten / Betriebskosten in € |
| `heating_costs` | Number | Heizkosten in € |
| `deposit` | Number | Kaution in € |
| `total_rent` | Number | Warmmiete / Gesamtmiete in € |
| `city` | String | City name |
| `zip_code` | String | German postal code |
| `district` | String | City district / Stadtteil |
| `state` | String | German Bundesland |
| `address` | String | Full address (when available) |
| `floor` | Number | Floor level (apartments) |
| `total_floors` | Number | Total floors in the building |
| `year_built` | Number | Year of construction |
| `energy_rating` | String | Energy class: A+, A, B, C, D … H |
| `energy_kwh` | Number | Energy consumption in kWh/m²/year |
| `heating_type` | String | Heating system type |
| `condition` | String | Property condition |
| `has_balcony` | Boolean | Has balcony or terrace |
| `has_garden` | Boolean | Has garden |
| `has_garage` | Boolean | Has garage or parking space |
| `has_elevator` | Boolean | Has elevator |
| `has_cellar` | Boolean | Has cellar |
| `is_commission_free` | Boolean | No broker commission |
| `thumbnail_url` | String | Main listing photo URL |
| `images` | Array | All photo URLs *(detail mode only)* |
| `description` | String | Full expose text *(detail mode only)* |
| `url` | String | Direct link to the listing |
| `external_id` | String | Immowelt expose ID |

---

## Input options

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `city` | String | `Berlin` | City to search (e.g. München, Hamburg, Frankfurt) — leave empty for nationwide |
| `propertyType` | Select | `wohnung` | `wohnung`, `haus`, or `grundstueck` |
| `priceType` | Select | `kauf` | `kauf` (buy) or `miete` (rent) |
| `priceMin` | Number | — | Minimum price in € |
| `priceMax` | Number | — | Maximum price in € |
| `roomsMin` | Number | — | Minimum number of rooms |
| `roomsMax` | Number | — | Maximum number of rooms |
| `areaMin` | Number | — | Minimum living area in m² |
| `areaMax` | Number | — | Maximum living area in m² |
| `yearBuiltMin` | Number | — | Minimum year of construction |
| `zipCode` | String | — | Search by postal code instead of city name |
| `radiusKm` | Number | — | Search radius in km around city/zip |
| `yearBuiltMax` | Number | — | Maximum year of construction |
| `hasBalcony` | Boolean | — | Filter for listings with balcony |
| `hasElevator` | Boolean | — | Filter for listings with elevator |
| `hasCellar` | Boolean | — | Filter for listings with cellar |
| `hasGarage` | Boolean | — | Filter for listings with garage/parking |
| `commissionFree` | Boolean | — | Filter for commission-free listings only |
| `maxPages` | Number | `5` | Pages to scrape (~20 listings per page) |
| `enrichDetails` | Boolean | `false` | Visit each expose page for full description & all photos |
| `proxyConfiguration` | Proxy | — | Apify Proxy settings (Residential recommended) |

---

## Example — Rental apartments in Hamburg

```
{
  "city": "Hamburg",
  "propertyType": "wohnung",
  "priceType": "miete",
  "priceMax": 1800,
  "roomsMin": 2,
  "areaMin": 50,
  "maxPages": 5,
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": ["RESIDENTIAL"]
  }
}
```

**Expected output:** ~100 rental listings with price, rooms, area, floor, district, and energy rating.

---

## Example — Houses for sale in Frankfurt

```
{
  "city": "Frankfurt",
  "propertyType": "haus",
  "priceType": "kauf",
  "priceMin": 500000,
  "priceMax": 1500000,
  "roomsMin": 4,
  "maxPages": 10
}
```

---

## Tips for best results

- **Residential proxies** significantly improve success rates on larger runs — select `RESIDENTIAL` in the proxy configuration
- Each page returns approximately 20 listings; `maxPages: 10` = ~200 results
- Enable `enrichDetails` only when you need full descriptions or all photos — it multiplies runtime and proxy usage considerably
- For nationwide searches, leave `city` empty
- Immowelt has strong bot detection — always use proxies for runs above 5 pages

---

## Use cases

**Real estate professionals**
Monitor new listings as they appear, track price reductions, and generate qualified buyer or tenant leads automatically.

**Investors & analysts**
Build price comparison tables, analyze average rents by city and district, track supply/demand across German markets.

**PropTech & developers**
Integrate Immowelt data into your own property app, CRM, or valuation model — without maintaining your own scraper infrastructure.

**Researchers & journalists**
Study housing affordability trends, regional price disparities, or the impact of policy changes on the rental market.

**Relocation services**
Automatically monitor listings for clients moving to a new city — filter by commute zone, budget, and property type.

---

## Output example

```
{
  "title": "Sonnige 2-Zimmer-Wohnung mit Balkon in Altona",
  "price": 1350,
  "price_type": "miete",
  "property_type": "wohnung",
  "rooms": 2,
  "area_sqm": 58.0,
  "city": "Hamburg",
  "zip_code": "22765",
  "district": "Altona-Altstadt",
  "state": "Hamburg",
  "address": "22765 Hamburg",
  "floor": 3,
  "total_floors": 5,
  "additional_costs": 180,
  "heating_costs": null,
  "deposit": 4050,
  "total_rent": 1530,
  "year_built": 2002,
  "energy_rating": "B",
  "energy_kwh": 78,
  "heating_type": "Zentralheizung",
  "condition": "Gepflegt",
  "has_balcony": true,
  "has_garden": false,
  "has_garage": false,
  "has_elevator": true,
  "is_commission_free": true,
  "thumbnail_url": "https://pictures.immowelt.com/...",
  "url": "https://www.immowelt.de/expose/abc12345",
  "external_id": "abc12345"
}
```

---

## FAQ

**Does this work without proxies?**
For small searches (1–3 pages), it usually works without proxies. For larger runs, Residential proxies are strongly recommended — Immowelt actively detects automated traffic.

**How many listings can I scrape per search?**
Immowelt typically shows up to 50 pages per search (~1,000 listings). For broader coverage, split searches by city, price range, or property type.

**Will it break when Immowelt updates their site?**
The scraper targets stable data attributes in Immowelt's page structure. The actor is maintained and updated when significant layout changes occur.

**What's the difference between standard and detail mode?**
Standard mode scrapes search result pages only (~1–2s per listing). Detail mode (`enrichDetails: true`) additionally opens each individual expose page to extract the full text description, all listing photos, and extended feature data (~5–8s per listing).

**Does it handle cookie consent popups?**
Yes — the scraper includes an automatic consent handler that dismisses GDPR cookie banners before scraping begins.

---

## Legal

This actor is intended for legitimate research, analysis, and data aggregation. Users are responsible for complying with Immowelt's Terms of Service and applicable data protection laws (GDPR). Do not use scraped data for spam, unauthorized commercial solicitation, or any illegal purpose.