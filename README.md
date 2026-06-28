[Immowelt Scraper](https://apify.com/parseforge/immowelt-scraper?fpr=data)

![ParseForge Banner](https://images.apifyusercontent.com/RHzPvdHJ2joNXJHSWjeziGDTOTaycOsfmbNq9q8ZVRM/w:1800/cb:1/aHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL1BhcnNlRm9yZ2UvYXBpZnktYXNzZXRzL21haW4vYmFubmVyLmpwZw.webp)

# 🏠 Immowelt Property Listings Scraper

> 🕒 **Last updated:** 2026-05-05

Pull live real estate listings from Immowelt.de, Germany's largest property platform. Prices, room counts, floor, area, energy class, agency details, and more across apartments, houses, land, and commercial properties, delivered without writing a line of code.

> **The Immowelt Scraper collects property listings from Germany's leading real estate marketplace, including sale and rental prices, room count, area, address, energy class, and agency contact details.**

## ✨ What Does It Do

- 💶 **Sale and Rental Price** - collect the listed price for each property to track market rates or compare values across cities and neighborhoods
- 📐 **Price per Square Meter** - get the calculated price per m² for each listing to compare value across different property sizes and districts
- 🛏️ **Room Count and Living Area** - extract the number of rooms and total area in m² to filter properties by size without opening each listing manually
- 🏢 **Floor and Availability Date** - see which floor a unit is on and when it becomes available, useful for narrowing down move-in timelines
- 📍 **Full Address with District and ZIP** - get the complete address broken into street, district, city, and ZIP code for geographic analysis
- ⚡ **Energy Efficiency Class** - collect the energy certificate class (A to H) for each listing to assess running costs before committing to a visit
- 🏢 **Agency and Agent Details** - know which agency and agent manages each listing so you can reach out directly or track which agencies dominate a market
- 📝 **Description Snippet** - read a preview of the listing description to get context on property condition, features, and unique selling points

## 🔧 Input

- **Start URL** - paste any Immowelt search URL directly from your browser. Overrides location, property type, and transaction type
- **Max Items** - number of listings to collect. Free users: up to 100. Paid users: up to 1,000,000. Default: 10
- **Location** - city or region slug from Immowelt (e.g. `muenchen`, `berlin`, `hamburg`, `frankfurt-am-main`, `koeln`)
- **Property Type** - apartments, houses, land, commercial, or garages
- **Transaction Type** - buy or rent

Example input:

```
{
  "location": "berlin",
  "propertyType": "wohnungen",
  "transactionType": "mieten",
  "maxItems": 50
}
```

Or paste a direct search URL:

```
{
  "startUrl": "https://www.immowelt.de/suche/hamburg/haeuser/kaufen",
  "maxItems": 30
}
```

## 📊 Output

Each listing contains up to 21 fields. Download as JSON, CSV, or Excel.

| 🖼️ Property image | 🆔 Listing ID | 🏡 Property type |
| --- | --- | --- |
| 🔄 Transaction type | 🏷️ Listing tag | 💶 Sale or rental price |
| 📐 Price per m² | 🛏️ Number of rooms | 📏 Living area (m²) |
| 🏢 Floor | 📅 Available from | 📍 Full address |
| 🏘️ Street | 🗺️ District | 🌆 City |
| 📮 ZIP code | ⚡ Energy class | 🏢 Agency name |
| 👤 Agent name | 📝 Description snippet | 🔗 Listing URL |

```
{
  "imageUrl": "https://mms.immowelt.de/508de5d0-6b45-4452-a777-b073.jpg",
  "listingId": "2AABC12345678",
  "propertyType": "Wohnung",
  "transactionType": "kaufen",
  "tag": "Neubau",
  "price": 599500,
  "priceLabel": null,
  "pricePerSqm": 8213,
  "currency": "EUR",
  "rooms": 2.5,
  "area": 73,
  "floor": "3. Geschoss",
  "availableFrom": "frei ab sofort",
  "address": "Altperlacher Str. 12, Perlach, München (81737)",
  "street": "Altperlacher Str. 12",
  "district": "Perlach",
  "city": "München",
  "zip": "81737",
  "energyClass": "B",
  "agencyName": "BLAU-WEISS Hausverwaltungen - Immobilien GmbH",
  "agentName": "Thomas Berger",
  "descriptionSnippet": "Mitten in Altperlach befindet sich diese wunderschöne Dachgeschosswohnung mit uneinsehbarer Dachterrasse in hervorragender Lage...",
  "url": "https://www.immowelt.de/expose/2aabc12345678",
  "scrapedAt": "2026-03-18T16:30:00.000Z"
}
```

## 💎 Why Choose the Immowelt Scraper?

| Feature | Our Actor |
| --- | --- |
| Live sale and rental prices | ✔️ |
| Apartments, houses, land, and commercial | ✔️ |
| Full address with district and ZIP code | ✔️ |
| Energy efficiency class per listing | ✔️ |
| Agency name and agent contact | ✔️ |
| Description snippet per listing | ✔️ |
| Floor and availability date when listed | ✔️ |
| Price per m² calculated automatically | ✔️ |
| Direct search URL support | ✔️ |
| Free tier: 100 results per run | ✔️ |
| Export as CSV, Excel, or JSON | ✔️ |

## 📋 How to Use

No technical skills required. Follow these simple steps:

1. **Sign Up**: [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=vmoqkp)
2. **Find the Tool**: Search for "Immowelt Scraper" in the Apify Store and open it
3. **Set Your Input**: Pick a city, property type, and transaction type, or paste a search URL directly from Immowelt
4. **Run It**: Click "Start" and view your results in seconds

That's it. No coding, no setup, no complicated configuration. Export your data in CSV, Excel, or JSON format.

## 🎯 Business Use Cases

- 🏢 **Real Estate Agent** - monitor new listings in target cities, track price trends by district, and spot opportunities before competitors do
- 📊 **Market Researcher** - build structured datasets of German property listings with price, area, and energy class for regional analysis or investment research
- 💼 **Property Investor** - filter by city and transaction type to compare price per m² across neighborhoods and track availability dates for motivated sellers
- 🔬 **Data Analyst** - aggregate property data across multiple German cities to analyze rental vs. sale price ratios, energy class distribution, and market supply

---

## ✨ Why choose this Actor

|  | Capability |
| --- | --- |
| 🎯 | **Built for the job.** Scoped specifically to this data source so you skip the parser engineering entirely. |
| 🔖 | **Structured output.** Clean, typed fields ready for analysis, dashboards, or downstream pipelines. |
| ⚡ | **Fast.** Optimized request patterns return results in seconds, not minutes. |
| 🔁 | **Always fresh.** Every run pulls live data, so the dataset reflects the source as of run time. |
| 🌐 | **No infra to manage.** Apify handles proxies, retries, scaling, scheduling, and storage. |
| 🛡️ | **Reliable.** Battle-tested across many runs and edge cases, with graceful error handling. |
| 🚫 | **No code required.** Configure in the UI, run from CLI, schedule via cron, or call from any language with the Apify SDK. |

> 📊 Production-grade structured data without the engineering overhead of building and maintaining your own scraper.

---

## 📈 How it compares to alternatives

| Approach | Cost | Coverage | Refresh | Filters | Setup |
| --- | --- | --- | --- | --- | --- |
| **⭐ Immowelt Property Listings Scraper** *(this Actor)* | $5 free credit, then pay-per-use | Full source coverage | **Live per run** | Source-native filters supported | ⚡ 2 min |
| Build your own scraper | Engineering hours | Full once built | Whenever you maintain it | Custom code | 🐢 Days to weeks |
| Paid managed APIs | $$$ monthly | Vendor-defined | Live | Vendor-defined | ⏳ Hours |
| Third-party data dumps | Varies | Subset, often stale | Periodic | None | 🕒 Variable |

Pick this Actor when you want broad coverage, server-side filtering, and no pipeline maintenance.

---

## 🚀 How to use

1. 📝 **Sign up.** [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=vmoqkp) (takes 2 minutes).
2. 🌐 **Open the Actor.** Go to the Immowelt Property Listings Scraper page on the Apify Store.
3. 🎯 **Set input.** Configure the input fields in the form (or paste a JSON), then set `maxItems`.
4. 🚀 **Run it.** Click **Start** and let the Actor collect your data.
5. 📥 **Download.** Grab your results in the **Dataset** tab as CSV, Excel, JSON, or XML.

> ⏱️ Total time from signup to downloaded dataset: **3-5 minutes.** No coding required.

---

## 💼 Business use cases

| ### 📊 Data & Analytics     - Build trend reports and dashboards from live source data - Feed BI tools, warehouses, and ML pipelines with structured records - Run periodic snapshots to track changes over time - Compare segments, regions, or categories with consistent fields | ### 🏢 Operations & Strategy     - Monitor competitor moves, pricing, and inventory shifts - Build internal directories and lookup tools backed by current data - Power workflows that depend on fresh source records - Cut manual data-gathering time from hours to minutes |
| --- | --- |
| ### 🎯 Marketing & Growth     - Identify market opportunities and trending topics - Research target audiences and customer personas at scale - Power lead-generation pipelines with verified records - Track sentiment, reviews, or social signals over time | ### 🛠️ Engineering & Product     - Prototype features that need real-world data without owning a crawler - Replace fragile in-house scrapers with a managed Actor - Wire datasets into your apps via the Apify API or webhooks - Skip the proxy, retry, and parsing maintenance entirely |

---

## 🌟 Beyond business use cases

Data like this powers more than commercial workflows. The same structured records support research, education, civic projects, and personal initiatives.

| ### 🎓 Research and academia     - Empirical datasets for papers, thesis work, and coursework - Longitudinal studies tracking changes across snapshots - Reproducible research with cited, versioned data pulls - Classroom exercises on data analysis and ethical scraping | ### 🎨 Personal and creative     - Side projects, portfolio demos, and indie app launches - Data visualizations, dashboards, and infographics - Content research for bloggers, YouTubers, and podcasters - Hobbyist collections and personal trackers |
| --- | --- |
| ### 🤝 Non-profit and civic     - Transparency reporting and accountability projects - Advocacy campaigns backed by public-interest data - Community-run databases for local issues - Investigative journalism on public records | ### 🧪 Experimentation     - Prototype AI and machine-learning pipelines with real data - Validate product-market hypotheses before engineering spend - Train small domain-specific models on niche corpora - Test dashboard concepts with live input |

## 🤖 Ask an AI assistant about this scraper

Open a ready-to-send prompt about this ParseForge actor in the AI of your choice:

- 💬 [**ChatGPT**](https://chat.openai.com/?q=How%20do%20I%20use%20the%20IMMOWELT%20PROPERTY%20LISTINGS%20SCRAPER%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)
- 🧠 [**Claude**](https://claude.ai/new?q=How%20do%20I%20use%20the%20IMMOWELT%20PROPERTY%20LISTINGS%20SCRAPER%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)
- 🔍 [**Perplexity**](https://perplexity.ai/search?q=How%20do%20I%20use%20the%20IMMOWELT%20PROPERTY%20LISTINGS%20SCRAPER%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)
- 🅒 [**Copilot**](https://copilot.microsoft.com/?q=How%20do%20I%20use%20the%20IMMOWELT%20PROPERTY%20LISTINGS%20SCRAPER%20Scraper%20by%20ParseForge%20on%20Apify%3F%20Show%20me%20input%20examples%2C%20output%20fields%2C%20common%20use%20cases%2C%20and%20how%20to%20integrate%20it%20into%20a%20workflow.)

---

## ❓ Frequently Asked Questions

**🔍 How does it work?**
It collects publicly available listing data from Immowelt.de and delivers it in structured format. No coding or technical setup required.

**📊 How accurate is the data?**
Data reflects live listings visible on Immowelt at the time of the run, including real prices, room counts, and availability.

**🌍 Which locations are supported?**
Any German city or region available on Immowelt.de. Use the location slug from the URL (e.g. `muenchen`, `berlin`, `frankfurt-am-main`). You can also paste any Immowelt search URL directly.

**📅 Can I schedule this to run automatically?**
Yes, use Apify's scheduling feature or integrate with platforms like Make or Zapier for daily or weekly runs.

**⚖️ Is it legal to collect Immowelt data?**
This tool collects publicly available listing data. Users must comply with Immowelt's terms of service and applicable local laws.

**⚡ How long does a run take?**
A typical run of 10 to 30 listings completes in under 10 seconds.

**⚠️ Are there any limits?**
Free users can collect up to 100 listings per run. Paid users can collect up to 1,000,000 per run.

## 🔗 Integrate Immowelt Scraper with any app

- [Make](https://docs.apify.com/platform/integrations/make) - Automate workflows
- [Zapier](https://docs.apify.com/platform/integrations/zapier) - Connect 5000+ apps
- [GitHub](https://docs.apify.com/platform/integrations/github) - Version control integration
- [Slack](https://docs.apify.com/platform/integrations/slack) - Get notifications
- [Airbyte](https://docs.apify.com/platform/integrations/airbyte) - Data pipelines
- [Google Drive](https://docs.apify.com/platform/integrations/drive) - Export to spreadsheets

## 🔌 Integrate with any app

Immowelt Property Listings Scraper connects to any cloud service via [Apify integrations](https://apify.com/integrations):

- [**Make**](https://docs.apify.com/platform/integrations/make) - Automate multi-step workflows
- [**Zapier**](https://docs.apify.com/platform/integrations/zapier) - Connect with 5,000+ apps
- [**Slack**](https://docs.apify.com/platform/integrations/slack) - Get run notifications in your channels
- [**Airbyte**](https://docs.apify.com/platform/integrations/airbyte) - Pipe results into your warehouse
- [**GitHub**](https://docs.apify.com/platform/integrations/github) - Trigger runs from commits and releases
- [**Google Drive**](https://docs.apify.com/platform/integrations/drive) - Export datasets straight to Sheets

You can also use webhooks to trigger downstream actions when a run finishes. Push fresh data into your product backend, or alert your team in Slack.

---

## 💡 More ParseForge Actors

- [Idealista Scraper](https://apify.com/parseforge/idealista-scraper) - gather real estate listings and property details from Idealista
- [Propertypal Scraper](https://apify.com/parseforge/propertypal-scraper) - collect property listings and market data from Propertypal
- [Realestateview Scraper](https://apify.com/parseforge/realestateview-scraper) - extract real estate data from Realestateview
- [Trade Me Property Scraper](https://apify.com/parseforge/trade-me-property-scraper) - collect real estate listings from Trade Me

Browse our complete collection of [data extraction tools](https://apify.com/parseforge) for more.

## 🚀 Ready to Start?

[Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=vmoqkp) and collect your first 100 results for free. No coding, no setup.

## 🆘 Need Help?

- Check the FAQ section above for common questions
- Visit the [Apify support page](https://docs.apify.com) for documentation and tutorials
- Contact us to request a new scraper, propose a custom project, or report an issue at [Tally contact form](https://tally.so/r/BzdKgA)

## ⚠️ Disclaimer

> This Actor is an independent tool and is not affiliated with, endorsed by, or sponsored by Immowelt or any of its subsidiaries. All trademarks mentioned are the property of their respective owners.

---

## 🔗 Recommended Actors

- [**🔍 Google Search Scraper**](https://apify.com/parseforge/google-search-scraper) - Multi-engine SERP results with country and language targeting
- [**🗺️ Nominatim OSM Scraper**](https://apify.com/parseforge/nominatim-osm-scraper) - Geocode addresses via OpenStreetMap
- [**📊 Indexmundi Scraper**](https://apify.com/parseforge/indexmundi-scraper) - Global demographic and economic indicators
- [**📰 RAG Web Browser**](https://apify.com/parseforge/rag-web-browser) - Crawl and extract clean text from any URL for AI retrieval
- [**🌐 Website Content Crawler**](https://apify.com/parseforge/website-content-crawler) - Crawl entire sites and export structured content

> 💡 **Pro Tip:** browse the complete [ParseForge collection](https://apify.com/parseforge) for more reference-data scrapers.