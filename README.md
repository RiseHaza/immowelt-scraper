[Immowelt Scraper](https://apify.com/memo23/immowelt-scraper?fpr=data)

## Overview

Extract comprehensive real estate listings from Immowelt.de, Germany's leading property marketplace. Get detailed property information including prices, locations, specifications, contact details, publisher information, amenities, energy certificates, and high-quality images for informed real estate investment and market analysis.

The **Immowelt.de Scraper** is a specialized tool designed to extract comprehensive real estate listings from [Immowelt.de](https://www.immowelt.de/), one of Germany's most popular platforms for property search. This scraper delivers rich, structured data encompassing every critical aspect of property listings to support informed real estate investment and market analysis.

With this scraper, users gain access to **detailed property information** including complete addresses, property types, prices, room counts, living spaces, plot areas, and comprehensive location data with GPS coordinates. The tool captures **extensive property specifications** with full details about listings across German cities and regions.

**Property specifications** are thoroughly extracted, including property types (apartments, houses, commercial), distribution types (buy, rent, auction), detailed room layouts, living and plot areas, floor information, and availability dates. Detailed geographic information including coordinates enables precise location mapping.

The scraper excels at capturing **publisher and contact details**, including real estate agency information, contact emails, phone numbers, and professional profiles for direct outreach and lead generation.

**Financial details** receive special attention with dedicated fields for total prices, price per square meter, financing calculations, and commission information, enabling precise investment analysis.

Additional **property features** include comprehensive amenity lists, energy certificates with efficiency ratings, detailed descriptions, professional images, floor plans, and construction/condition details for comprehensive property evaluation.

Whether you're a real estate investor searching for German properties, an agent analyzing the market, a data analyst tracking real estate trends, or a property seeker looking for detailed listings, this scraper provides the complete, structured dataset needed for professional-grade real estate exploration and decision-making.

---

## Features

- **Smart Search Detection**:

- Automatically detects search results pages and extracts all property IDs
- Handles complex filters including location, property types, and distribution types
- Supports pagination for comprehensive data extraction
- **Comprehensive Property Data**:

- Extracts complete property addresses with GPS coordinates
- Captures prices, price per square meter, and financing information
- Includes detailed room counts, living space, and plot area data
- **Efficient Data Extraction**:

- Utilizes both browser API for search and mobile API for detailed property information
- Implements smart retry logic with DataDome bot protection bypass
- Handles cookie management for seamless pagination
- **Publisher & Contact Intelligence**:

- Extracts real estate agency/publisher information with logos
- Captures contact emails and phone numbers for direct outreach
- Includes publisher profiles and professional details
- **Rich Media & Documentation**:

- Downloads high-quality property images with descriptions
- Extracts floor plans and property layouts
- Captures energy certificates with detailed efficiency ratings
- **Advanced Filtering Support**:

- Supports scraping by location (city, region, postal code)
- Filters by property type (house, apartment, commercial)
- Distribution type filtering (buy, rent, auction)
- **SEO search URLs (`/suche/...`)**:

- Immowelt’s human-readable search URLs are supported alongside legacy query URLs
- The actor reads the canonical search payload from the first page HTML, then paginates through the **serp-bff** search API (repeating `?page=` on the SEO URL alone is not reliable for full result counts)
- **Legacy search URLs (`/classified-search?...`)**:

- Filter URLs from the classified search UI use an internal, Impit-based pipeline (search → batch classified data → per-listing detail) for efficient extraction
- **Realtor agency profiles (`/profil/{id}`)**:

- Accepts profile URLs with a **32-character hexadecimal** agency id (e.g. `https://www.immowelt.de/profil/52dc6238ddc2436cadac1556383f6d47`)
- Loads the **mobile webview** version (`?app=1`, iPhone-style `User-Agent`, `Cookie: aviv_client=ios`) so the server embeds `__UFRN_FETCHER__` listing cards in the HTML
- Parses embedded **UFRN** data and **`__UFRN_LIFECYCLE_SERVERREQUEST__`** for agency name and listing metadata
- **Sale-only by default** on profiles: keeps listings whose distribution type is buy or auction (`BUY`, `Buy_Auction`, `Compulsory_Auction`, `Buy`); rental listings on the same profile are skipped
- Each qualifying listing is then opened as **`/expose/{uuid}`** and merged with the same rich detail extraction used elsewhere
- **Profile `/classifiedList` backfill (optional automatic)**:

- If the profile’s **`counts.forSale`** is higher than the number of **sale** cards embedded in the first HTML response, but `__UFRN_FETCHER__` still lists **short classified ids** in its `properties` array, the actor issues **`GET https://www.immowelt.de/classifiedList/{id1,id2,...}`** using the same mobile headers and profile **Referer** (`.../profil/...?app=1`), in chunks
- Sale rows from that response are merged in **UUID order** aligned with the fetcher’s property list; this can **expand** how many exposes are queued when lazy-loaded cards were not in SSR
- If the backfill returns no extra sale rows, scraping continues from SSR cards only. If `properties` does not list ids beyond SSR, behavior is unchanged (true browser-only lazy load cannot be fixed without a different approach)

---

## How to Use

1. **Set Up**: Ensure you have an Apify account and access to the Apify platform.
2. **Provide Input Data**: Input specific scraping parameters, such as search URLs from Immowelt.de.
3. **Adjust Scraper Settings**: Configure settings like `maxItems`, `maxConcurrency`, and `maxRequestRetries` to optimize performance.
4. **Run the Scraper**: Execute the scraper on the Apify platform.
5. **Download Results**: Export the scraped property data in your preferred format (JSON, CSV, Excel).

### Usage Limitations

**Free Users**: Non-paying users are limited to scraping **50 properties** per run and can only use **1 start URL**. To access unlimited scraping and all features, please upgrade to a paid Apify account.

**Paid Users**: Enjoy unlimited property scraping, multiple start URLs, and full access to all scraper features.

---

## Input Configuration

To use the scraper, configure the input parameters as follows:

```
{
    "startUrls": [
        {
            "url": "https://www.immowelt.de/classified-search?distributionTypes=Buy,Buy_Auction,Compulsory_Auction&estateSubTypes=Multi_Family_House,Terrace_House,Corner_Terrace_House,Mid_Terrace_House,End_Terrace_House&estateTypes=House&keywords=Wohn-%2Bund%2BGesch%C3%A4ftshaus&locations=AD08DE2342,AD06DE297,AD08DE2572,AD08DE2404,AD08DE2355,AD08DE1114,AD06DE35,AD08DE2392,AD08DE2426,AD08DE10449,AD08DE2509,AD06DE138,AD06DE132,AD06DE21,AD06DE100,AD08DE2427,AD08DE1370,AD08DE2428,AD08DE2598,AD06DE28,AD06DE101,AD06DE31,AD08DE2456,AD08DE10451,AD06DE140,AD06DE117,AD08DE2490,AD08DE2458,AD08DE2767,AD08DE2409,AD08DE2279,AD06DE129,AD06DE59,AD06DE105,AD06DE26,AD08DE1115,AD08DE2482,AD08DE10453,AD08DE2734,AD06DE27,AD08DE1116&projectTypes=Resale,Investment&spaceMin=350&yearOfConstructionMin=1950"
        },
        {
            "url": "https://www.immowelt.de/expose/568ec3e0-d22e-4f8a-9e50-8bea70e24e81?serp_view=list&search=distributionTypes%3DBuy%2CBuy_Auction%2CCompulsory_Auction%26estateSubTypes%3DMulti_Family_House%2CTerrace_House%2CCorner_Terrace_House%2CMid_Terrace_House%2CEnd_Terrace_House%26estateTypes%3DHouse%26keywords%3DWohn-%252Bund%252BGesch%25C3%25A4ftshaus%26locations%3DAD08DE2342%2CAD06DE297%2CAD08DE2572%2CAD08DE2404%2CAD08DE2355%2CAD08DE1114%2CAD06DE35%2CAD08DE2392%2CAD08DE2426%2CAD08DE10449%2CAD08DE2509%2CAD06DE138%2CAD06DE132%2CAD06DE21%2CAD06DE100%2CAD08DE2427%2CAD08DE1370%2CAD08DE2428%2CAD08DE2598%2CAD06DE28%2CAD06DE101%2CAD06DE31%2CAD08DE2456%2CAD08DE10451%2CAD06DE140%2CAD06DE117%2CAD08DE2490%2CAD08DE2458%2CAD08DE2767%2CAD08DE2409%2CAD08DE2279%2CAD06DE129%2CAD06DE59%2CAD06DE105%2CAD06DE26%2CAD08DE1115%2CAD08DE2482%2CAD08DE10453%2CAD08DE2734%2CAD06DE27%2CAD08DE1116%26projectTypes%3DResale%2CInvestment%26spaceMin%3D300%26yearOfConstructionMin%3D1950#ln=classified_search_results&m=classified_search_results_classified_classified_detail_L"
        }
    ],
    "maxItems": 200,
    "maxConcurrency": 100,
    "minConcurrency": 1,
    "maxRequestRetries": 100,
    "proxy": {
        "useApifyProxy": true,
        "apifyProxyGroups": [
            "RESIDENTIAL"
        ]
    }
}
```

### Input Fields Explanation

- **Dual mode:** Add at least one **Start URL**, **or** leave the start URL list empty and use **Search by filters**. If any start URL is non-empty, **filter fields are ignored**. Filter-only runs build `https://www.immowelt.de/classified-search?...` from:

- **Buy / rent** (`searchDistributionMode`): `buy` (default, includes auctions), `rent`, or `buy_and_rent`
- **Property type** (`searchEstateType`): `house`, `apartment`, or `house_and_apartment` (default)
- **City / keyword** (`searchKeyword`, optional): Immowelt `keywords` — e.g. “Augsburg”. Omit for a very broad search; cap with **`maxItems`**. For the exact same filters as on the website, paste a **Start URL**.
Implementation: `src/lib/immoweltSearchUrlFromFilters.ts`, `src/main.ts`. See `GUIDE_DUAL_MODE_INPUT_FOR_SCRAPER_ACTORS.md`.
- **Start URLs** (`startUrls`): The URLs from which the scraper will begin extracting data. The scraper accepts:

- **Legacy search**: `https://www.immowelt.de/classified-search?...` (internal Impit search → batch → detail flow)
- **SEO search**: `https://www.immowelt.de/suche/...` (browser/crawler flow: HTML embeds canonical query; paginates via serp-bff)
- **Listing detail**: `https://www.immowelt.de/expose/{uuid}`
- **Project detail**: `https://www.immowelt.de/projekte/expose/{projectId}`
- **Realtor profile**: `https://www.immowelt.de/profil/{32-hex}` — mobile SSR + optional `/classifiedList` backfill; **sale listings only** by default; respects `maxItems` for how many exposes are scraped
- Example (search): `https://www.immowelt.de/classified-search?distributionTypes=Buy&estateTypes=House&locations=AD08DE6748`
- **Max Items** (`maxItems`): Maximum number of properties to scrape per run. Default is `200`.
- **Max Concurrency** (`maxConcurrency`): Maximum number of pages processed simultaneously. Default is `100`.
- **Min Concurrency** (`minConcurrency`): Minimum number of pages processed simultaneously. Default is `1`.
- **Max Request Retries** (`maxRequestRetries`): Number of retries for failed requests. Default is `100`.
- **Proxy Configuration** (`proxy`): Settings for reliable and anonymous scraping. Supports custom proxy URLs.
- **More Results** (`moreResults`): Enable to fetch additional pages beyond the initial results.
- **Include Listing Details** (`includeListingDetails`): When true, fetches complete property details for each listing.

### URL Parameters Guide

Immowelt.de search URLs support various filters:

- **distributionTypes**: `Buy`, `Buy_Auction`, `Rent`
- **estateTypes**: `House`, `Apartment`, `Commercial`, `Plot`, `Garage`
- **locations**: Location ID (e.g., `AD08DE6748` for Kolbermoor)
- **page**: Page number for pagination

Example URL with filters:

```
https://www.immowelt.de/classified-search?distributionTypes=Buy,Buy_Auction&estateTypes=House,Apartment&locations=AD08DE6748&page=1
```

---

## Output Structure

The scraper produces a JSON output with detailed information for each property listing. The output includes comprehensive data with **120+ fields** covering all aspects of the property.

```
{
    "id": "25Y6EXGVK817",
    "legacyId": "f3c84937-a9ab-4b32-9859-cb48d6ee0e5e",
    "brand": "immowelt",
    "status": "Published",
    "type": "PROFESSIONAL",
    "portal": "immowelt",
    "display": "classified",
    "metadataStatus": true,
    "metadataEnrichments": {
        "contactSettings": false,
        "geo": false,
        "intermediary": false,
        "media": false,
        "onlineId": false
    },
    "title": "Mehrfamilienhaus zum Kauf",
    "headline": "Attraktives Wohn- und Geschäftshaus in zentraler Lage Bielefeld",
    "description": "...",
    "propertyType": "Mehrfamilienhaus",
    "distributionType": "BUY",
    "titleAdditions": ["als Kapitalanlage geeignet"],
    "keyFacts": ["752 m²", "754 m² Grundstück"],
    "price": 1190000,
    "priceFormatted": "1.190.000 €",
    "priceValue": "1.190.000 €",
    "pricePerSqm": "1.582 €/m²",
    "priceAddition": {
        "value": "1.582 €/m²",
        "ariaLabel": "1582,45 Euro pro Quadratmeter"
    },
    "priceAriaLabel": "1190000 €",
    "priceFinancialLink": {
        "href": "https://www.immowelt.de/immobilienfinanzierung-anfragen/?price=1190000...",
        "label": "Finanzierung anfragen",
        "partnerName": "KFW"
    },
    "priceRaw": "1.190.000 €",
    "currency": "EUR",
    "address": "33613 Bielefeld",
    "city": "Bielefeld",
    "zipCode": "33613",
    "country": "DE",
    "isAddressPublished": false,
    "geoIdHierarchy": [
        {"id": "NBH2DE91294727", "typeKey": "NBH2"},
        {"id": "AD08DE2355", "typeKey": "AD08"},
        {"id": "AD06DE99", "typeKey": "AD06"}
    ],
    "coordinates": {
        "lng": [[[8.57255, 52.04771], [8.56912, 52.04985], ...]]
    },
    "rooms": 13,
    "livingSpace": 752,
    "livingSpaceFormatted": "752 m²",
    "plotSize": 754,
    "plotSizeFormatted": "754 m² Grundstück",
    "factsRaw": [...],
    "energyClass": "F",
    "energyRating": "F",
    "energyCertificate": "F",
    "energyConsumption": "230 kWh/(m²·a)",
    "yearOfConstruction": "1957",
    "condition": "Saniert",
    "buildingState": "Saniert",
    "heatingType": "Zentralheizung",
    "energySource": "Gas",
    "energyFeaturesRaw": [...],
    "locationDescription": "...",
    "images": [
        {
            "key": "abc123...",
            "url": "https://mms.immowelt.de/...",
            "description": "Titelbild",
            "alt": "Property image",
            "title": "Titelbild",
            "ariaLabel": "Titelbild",
            "classification": "BUILDING_FACADE",
            "classificationVersion": "1.0"
        }
    ],
    "imageCount": 15,
    "floorplans": [...],
    "floorplanCount": 2,
    "galleryAvailableFeatures": {
        "floorplans": true,
        "virtualTours": false
    },
    "hasFloorplans": true,
    "hasVirtualTours": false,
    "providerType": "AGENCY",
    "isPrivateOwner": false,
    "displayLinks": true,
    "contactName": "John Doe",
    "contactSubtitle": "Dein Kontakt",
    "contactDisplay": true,
    "contactLogoUrl": "https://...",
    "companyName": "Real Estate AG",
    "companySubtitle": "Gewerblicher Anbieter",
    "companyDisplay": true,
    "companyLogo": "https://...",
    "companyLogoHref": "https://...",
    "companyAddress": "Hauptstraße 1, 33613 Bielefeld",
    "phoneNumbers": ["+49 123 456789"],
    "website": "https://example.com",
    "profileUrl": "https://www.immowelt.de/profil/...",
    "imprintUrl": "https://www.immowelt.de/profil/...#impressum",
    "agencyLegalInformations": [],
    "badge": "immowelt Partner",
    "badgeImage": "https://...",
    "agencyColor": "#2a835e",
    "agencyFontColor": "#FFFFFF",
    "providerRating": {
        "rating": 4.5,
        "reviews": 120,
        "link": "https://..."
    },
    "cardProvider": {
        "title": "John Doe",
        "subtitle": "Dein Kontakt",
        "logoUrl": "https://...",
        "agencyStrip": {...}
    },
    "isExclusive": false,
    "has3DVisit": false,
    "hasBrokerageFee": false,
    "isNew": true,
    "isHdExclusive": false,
    "tracking": {...},
    "estateType": "av_5",
    "trackingDistributionType": "2",
    "productType": "standard",
    "clientId": "1234567",
    "rawData": {...},
    "surface": {"main": 752, "plot": 754},
    "nbroom": 13,
    "contactLocationEnabled": true,
    "createdAt": "2025-12-01T10:00:00.000Z",
    "updatedAt": "2026-01-10T15:30:00.000Z",
    "isNewBuild": false,
    "url": "https://www.immowelt.de/expose/25Y6EXGVK817",
    "searchUrl": "https://www.immowelt.de/classified-search?...",
    "scrapedAt": "2026-01-12T20:00:00.000Z",
    "source": "ufrn_detail"
}
```

---

## Output Fields Explanation

Below is a comprehensive explanation of every field in the output JSON, organized by category for easy reference. The scraper now extracts **120+ fields** covering all aspects of property data.

### Basic Identification & Brand

- **id**: Unique property identifier on Immowelt.de (e.g., `"25Y6EXGVK817"`). This ID is used in the property URL and for tracking purposes.
- **legacyId**: Legacy system identifier in UUID format (e.g., `"f3c84937-a9ab-4b32-9859-cb48d6ee0e5e"`). Used for internal database references.
- **brand**: Platform brand identifier (e.g., `"immowelt"`). Identifies the source platform.
- **status**: Publishing status of the listing (e.g., `"Published"`). Indicates if the property is active or inactive.
- **type**: Listing type (e.g., `"PROFESSIONAL"` or `"PRIVATE"`). Indicates if it's from a professional agency or private owner.
- **portal**: Portal name (e.g., `"immowelt"`). The platform hosting the listing.
- **display**: Display type (e.g., `"classified"`). How the listing is categorized internally.

### Metadata & Enrichment

- **metadataStatus**: Boolean indicating if metadata is available and valid (e.g., `true`).
- **metadataEnrichments**: Object showing enrichment status for various data categories:

- **contactSettings**: Boolean - Contact information enrichment status
- **geo**: Boolean - Geographic data enrichment status
- **intermediary**: Boolean - Agency/broker enrichment status
- **media**: Boolean - Media (images, videos) enrichment status
- **onlineId**: Boolean - Online identifier enrichment status

### URLs

- **url**: Direct link to the property detail page on Immowelt.de (e.g., `"https://www.immowelt.de/expose/25Y6EXGVK817"`). Use this to view the original listing.
- **searchUrl**: The original search URL that discovered this property. Useful for tracking which search criteria found this listing.
- **source**: Data source indicator (e.g., `"ufrn_detail"`, `"batch_api"`, `"combined"`). Shows whether data was extracted from detail page, batch API, or combined sources.

### Realtor profile runs (extra fields)

When the listing was discovered via a **`/profil/...`** start URL, rows may also include:

- **realtorName**: Agency display name from profile lifecycle data when available
- **realtorProfileUrl**: Canonical profile URL (without query string)
- **sourceProfileUrl**: Same canonical profile URL (stable reference to the originating profile)
- **profileFetchedWithAppParam**: `true` when detail was scraped in the mobile `?app=1` context

### Property Title & Basic Info

- **title**: Primary property classification (e.g., `"Wohnung zum Kauf"` = "Apartment for sale"). Indicates the main property type and transaction type.
- **headline**: Detailed property headline/description provided by the seller (e.g., `"Charmante, vermietete 2-Zimmer-Dachgeschosswohnung in Kolbermoor"`). This is the main marketing headline.
- **propertyType**: Property category in German (e.g., `"Wohnung"` = Apartment, `"Haus"` = House). Core classification of the property type.

### Key Property Facts

- **keyFacts**: Array of the most important property characteristics displayed prominently on the listing:

- Room count (e.g., `"2 Zimmer"`)
- Living space (e.g., `"57 m²"`)
- Floor level (e.g., `"3. Geschoss"`)

These are the primary selling points shown at the top of every listing.

### Pricing Information (Comprehensive)

- **price**: Numeric price value as integer (e.g., `1190000`). Pure number format for calculations.
- **priceFormatted**: Human-readable price with currency and thousand separators (e.g., `"1.190.000 €"`). Ready for display.
- **priceValue**: Price as formatted string (e.g., `"1.190.000 €"`). Original formatted value from source.
- **pricePerSqm**: Price per square meter calculation (e.g., `"1.582 €/m²"`). Essential metric for property value comparison.
- **priceAddition**: Object containing additional price information:

- **value**: Price per sqm formatted (e.g., `"1.582 €/m²"`)
- **ariaLabel**: Accessibility label with full precision (e.g., `"1582,45 Euro pro Quadratmeter"`)
- **priceAriaLabel**: Accessibility-friendly price label (e.g., `"1190000 €"`). For screen readers and accessibility.
- **priceFinancialLink**: Object containing financing information:

- **href**: Direct URL to financing inquiry page with pre-filled property data
- **label**: Button text (typically `"Finanzierung anfragen"` = "Request financing")
- **partnerName**: Financing partner name (e.g., `"KFW"`)
- **priceRaw**: Raw formatted price string (e.g., `"1.190.000 €"`). Original source format.
- **currency**: Currency code (e.g., `"EUR"`). ISO 4217 currency code.

### Location Details (Enhanced)

- **address**: Full address string, may be partially hidden for privacy (e.g., `"33613 Bielefeld"`). German privacy laws sometimes hide exact street addresses.
- **city**: City name (e.g., `"Bielefeld"`). The municipality where the property is located.
- **zipCode**: German postal code (e.g., `"33613"`). Five-digit PLZ (Postleitzahl).
- **country**: ISO 3166-1 alpha-2 or alpha-3 country code (e.g., `"DE"` or `"DEU"` for Germany).
- **region**: Administrative region name (e.g., `"Nordrhein-Westfalen"`). Federal state where property is located.
- **isAddressPublished**: Boolean indicating if exact address is publicly visible (e.g., `false`). Privacy protection feature.
- **geoIdHierarchy**: Array of geographic identifiers from neighborhood to country level. Each entry contains:

- **id**: Geographic area identifier (e.g., `"NBH2DE91294727"`)
- **typeKey**: Type of geographic area (`NBH2`=neighborhood, `AD08`=city district, `AD06`=city, `AD04`=region, `AD02`=country)

This hierarchy enables precise location-based filtering and analysis.

### Geographic Coordinates

- **coordinates**: Object containing geographic data:

- **lng**: Nested array structure containing longitude/latitude pairs. Format: `[[[lng1, lat1], [lng2, lat2], ...]]`
- First coordinate pair typically represents the property's location
- Additional pairs may define boundary polygons for privacy zones
- Example: `[[[12.07892, 47.84522], [12.07845, 47.84603], ...]]`

These coordinates can be used for mapping, distance calculations, and geographic analysis.

### Room & Space Details (Comprehensive)

- **rooms**: Number of rooms as integer (e.g., `13`). Represents total room count.
- **roomsFormatted**: Formatted room count with label (e.g., `"13 Zimmer"`). Ready for display in German.
- **livingSpace**: Living area in square meters as integer (e.g., `752`). Core metric for property size (interior space).
- **livingSpaceFormatted**: Formatted living space with unit (e.g., `"752 m²"`). Display-ready format.
- **plotSize**: Plot/land area in square meters as integer (e.g., `754`). Size of the land parcel the property sits on.
- **plotSizeFormatted**: Formatted plot size with unit (e.g., `"754 m² Grundstück"`). Display-ready format with "Grundstück" (plot) label.
- **floor**: Floor number as string (e.g., `"3."`). Indicates which floor/level the property is on.
- **floorFormatted**: Formatted floor information (e.g., `"3. Geschoss"` = "3rd floor"). Complete German format with "Geschoss" (floor) label.

### Structured Property Facts (Raw Data)

- **factsRaw**: Array of structured fact objects, each containing:

- **type**: Fact category identifier (e.g., `"numberOfRooms"`, `"livingSpace"`, `"numberOfFloors"`)
- **value**: Complete formatted value (e.g., `"2 Zimmer"`)
- **splitValue**: Numeric component only (e.g., `"2"`)
- **label**: Unit or descriptor (e.g., `"Zimmer"`, `"m²"`, `"Geschoss"`)

This structured format allows for easy programmatic parsing and data analysis.

### Energy Efficiency Information (Complete)

- **energyClass**: Energy efficiency class rating (e.g., `"F"`). German energy certificate classification from A+ (best) to H (worst).
- **energyRating**: Same as energyClass, alternative field name (e.g., `"F"`).
- **energyCertificate**: Energy certificate rating (e.g., `"F"`). Official energy performance certificate rating.
- **energyConsumption**: Annual energy consumption (e.g., `"230 kWh/(m²·a)"`). Kilowatt-hours per square meter per year.
- **heatingType**: Type of heating system (e.g., `"Zentralheizung"` = Central heating, `"Fußbodenheizung"` = Underfloor heating). Describes the property's heating infrastructure.
- **energySource**: Primary energy source (e.g., `"Gas"`, `"Öl"` = Oil, `"Fernwärme"` = District heating, `"Wärmepumpe"` = Heat pump). The fuel/energy type used for heating.
- **buildingState**: Building condition/state (e.g., `"Saniert"` = Renovated, `"Neuwertig"` = Like new, `"Gepflegt"` = Well-maintained). Describes the overall condition.

### Building Details

- **yearOfConstruction**: Year the building was constructed (e.g., `"1995"`). Original construction date.
- **condition**: Building type or construction method (e.g., `"Massivhaus"` = Solid construction house). Describes structural characteristics.

### Energy Features (Raw Structured Data)

- **energyFeaturesRaw**: Array of structured energy-related data objects:

- **type**: Feature identifier (e.g., `"yearOfConstruction"`, `"state"`, `"heatingSystem"`, `"energySource"`)
- **label**: German label for display (e.g., `"Baujahr"`, `"Zustand der Immobilie"`)
- **value**: The feature's value (e.g., `"1995"`, `"Massivhaus"`, `"Zentralheizung"`)

Provides structured access to all energy certificate data for detailed analysis.

### Property Descriptions

- **description**: Full property description in German (HTML formatted). Contains:

- Detailed property features and layout
- Room descriptions and special features
- Rental status and income information (if applicable)
- Additional amenities and highlights
- May include HTML `<br>` tags for formatting

This is the main marketing text written by the seller/agent.
- **locationDescription**: Detailed description of the location and neighborhood in German. Includes:

- Information about the city/district
- Local amenities and infrastructure
- Transportation connections
- Schools, shopping, and recreation facilities
- Cultural and historical context

Provides valuable context for location quality assessment.

### Images (Enhanced Metadata)

- **images**: Array of property image objects, each containing:

- **key**: Unique identifier for the image (e.g., `"abc123-def456-..."`). Internal image ID.
- **url**: Direct URL to the image file on Immowelt's CDN (e.g., `"https://mms.immowelt.de/...jpg?ci_seal=..."`). Includes security seal parameter.
- **description**: German description of what the image shows (e.g., `"Titelbild"`, `"Wohnen"`, `"Küche"`, `"Bad"`).
- **alt**: Alternative text for accessibility (e.g., `"Property image"`). For screen readers.
- **title**: Image title (e.g., `"Titelbild"`). Display title.
- **ariaLabel**: ARIA label for accessibility (e.g., `"Titelbild"`). Enhanced accessibility label.
- **classification**: Standardized room/area classification:

- `BUILDING_FACADE`: Exterior building view
- `LIVING_ROOM`: Living/dining area
- `KITCHEN`: Kitchen
- `BEDROOM`: Bedroom
- `BATHROOM`: Bathroom
- `BALCONY`: Balcony
- `TERRACE`: Terrace/patio
- `EXTERIOR_VIEW`: Outdoor views
- `GARAGE`: Parking/garage
- `CLOSET`: Hallway/entrance
- And more...
- **classificationVersion**: Version of the classification algorithm used (e.g., `"1.0"`).

Images are professionally hosted with CDN optimization and security seals.
- **imageCount**: Total number of images available (e.g., `15`). Quick count for data analysis.

### Floor Plans (Enhanced)

- **floorplans**: Array of floor plan objects, each containing:

- **key**: Unique identifier for the floor plan. Internal image ID.
- **url**: Direct URL to the floor plan image (e.g., `"https://mms.immowelt.de/...jpg?ci_seal=..."`).
- **description**: Description of the floor plan (e.g., `"Grundriss Dachgeschoss"` = "Attic floor plan").
- **alt**: Alternative text for accessibility.
- **title**: Floor plan title.
- **ariaLabel**: ARIA label for accessibility.
- **classification**: Classification of the floor plan type.

Floor plans show the property layout and room arrangement.
- **floorplanCount**: Total number of floor plans available (e.g., `2`). Quick count for inventory.

### Gallery Features

- **galleryAvailableFeatures**: Object indicating available media types:

- **floorplans**: Boolean - Whether floor plans are available (e.g., `true`)
- **virtualTours**: Boolean - Whether 3D/virtual tours are available (e.g., `false`)
- **hasFloorplans**: Boolean shortcut for floor plan availability (e.g., `true`).
- **hasVirtualTours**: Boolean shortcut for virtual tour availability (e.g., `false`).

### Provider & Contact Information (Comprehensive)

#### Provider Classification

- **providerType**: Type of publisher (e.g., `"AGENCY"`, `"PRIVATE"`). Indicates if listing is from real estate agency or private owner.
- **isPrivateOwner**: Boolean indicating if property is sold by private owner (e.g., `false`). True for direct owner sales.
- **displayLinks**: Boolean indicating if provider links should be displayed (e.g., `true`).

#### Contact Person Details

- **contactName**: Name of the contact person (e.g., `"John Doe"`). The agent or representative handling inquiries.
- **contactSubtitle**: Contact section label (e.g., `"Dein Kontakt"` = "Your contact"). Display label for the contact area.
- **contactDisplay**: Boolean indicating if contact information should be displayed (e.g., `true`).
- **contactLogoUrl**: URL to contact person's photo/logo (e.g., `"https://..."`). Profile picture.

#### Company Details

- **companyName**: Real estate company name (e.g., `"Real Estate AG"`). The brokerage or agency managing the listing.
- **companySubtitle**: Company section label (e.g., `"Gewerblicher Anbieter"` = "Commercial provider").
- **companyDisplay**: Boolean indicating if company information should be displayed (e.g., `true`).
- **companyLogo**: URL to company logo (e.g., `"https://..."`). Company branding image.
- **companyLogoHref**: Clickable link URL for company logo (e.g., `"https://www.immowelt.de/profil/..."`).
- **companyAddress**: Physical address of the real estate company (e.g., `"Hauptstraße 1, 33613 Bielefeld"`).

#### Contact Methods

- **phoneNumbers**: Array of phone numbers (e.g., `["+49 123 456789"]`). Direct contact numbers.
- **website**: Company website URL (e.g., `"https://example.com"`). Official website.
- **profileUrl**: Immowelt profile page URL (e.g., `"https://www.immowelt.de/profil/..."`). Agency profile on Immowelt.
- **imprintUrl**: Legal imprint/impressum URL (e.g., `"https://www.immowelt.de/profil/...#impressum"`). Required legal information.
- **agencyLegalInformations**: Array of legal information objects. Additional legal disclosures.

#### Branding & Quality

- **badge**: Quality badge name (e.g., `"immowelt Partner"`). Partnership or certification badge.
- **badgeImage**: URL to badge image (e.g., `"https://..."`). Badge graphic/logo.
- **agencyColor**: Brand color hex code (e.g., `"#2a835e"`). Primary brand color for agency strip.
- **agencyFontColor**: Font color hex code (e.g., `"#FFFFFF"`). Text color for agency branding.

#### Rating & Reviews

- **providerRating**: Object containing rating information:

- **rating**: Average rating score (e.g., `4.5`). Star rating out of 5.
- **reviews**: Number of reviews (e.g., `120`). Total review count.
- **link**: URL to reviews page (e.g., `"https://www.immowelt.de/profil/...#rating"`).

#### Card Provider (Contact Card Display)

- **cardProvider**: Object containing contact card display information:

- **title**: Display name for contact card
- **subtitle**: Subtitle for contact card
- **logoUrl**: Logo URL for contact card
- **agencyStrip**: Agency branding strip information

### Property Tags & Features

- **isExclusive**: Boolean indicating if this is an exclusive listing (e.g., `false`). True for properties exclusively listed with this agent.
- **has3DVisit**: Boolean indicating if 3D virtual tour is available (e.g., `false`). True for 360° tours.
- **hasBrokerageFee**: Boolean indicating if brokerage fee applies (e.g., `false`). True when agent commission is charged.
- **isNew**: Boolean indicating if this is a newly listed property (e.g., `true`). True for recent listings.
- **isHdExclusive**: Boolean indicating if this is an HD exclusive listing (e.g., `false`). Premium listing indicator.

### Tracking & Analytics Data

- **tracking**: Complete tracking object containing analytics data. Includes various metrics for market analysis.
- **estateType**: Estate type code for analytics (e.g., `"av_5"`). Internal classification code.
- **trackingDistributionType**: Distribution type code (e.g., `"2"`). Internal code for buy/rent classification.
- **productType**: Product/listing type (e.g., `"standard"`, `"premium"`). Listing tier or package.
- **clientId**: Client/agency identifier (e.g., `"1234567"`). Internal ID for the listing agency.
- **trackingDistributionType**: Secondary distribution tracking code.
- **trackingCountry**: Country for tracking purposes.
- **trackingCity**: City for tracking purposes.
- **trackingZipCode**: Zip code for tracking purposes.
- **trackingLegacyId**: Legacy system tracking ID.
- **trackingName**: Tracking name/identifier.
- **trackingListName**: List name for tracking.
- **trackingPrice**: Price value for tracking.

### Raw Data & Technical Details

- **rawData**: Complete raw data object from the API. Contains original unprocessed data.
- **distributionType**: Distribution type (e.g., `"BUY"`, `"RENT"`, `"AUCTION"`). Transaction type.
- **surface**: Object containing surface measurements:

- **main**: Main living area in square meters (e.g., `752`)
- **plot**: Plot/land area in square meters (e.g., `754`)
- **nbroom**: Number of rooms as stored in raw data (e.g., `13`). Alternative field for room count.
- **contactLocationEnabled**: Boolean indicating if contact location is enabled (e.g., `true`). Privacy setting.
- **offererMarketingKey**: Marketing key for the property offerer.
- **providerCity**: City where provider is located.
- **providerZipCode**: Zip code of provider location.

### Listing Metadata

- **createdAt**: ISO 8601 timestamp when the listing was first created (e.g., `"2025-12-01T10:00:00.000Z"`). Original publication date.
- **updatedAt**: ISO 8601 timestamp of the last listing update (e.g., `"2026-01-10T15:30:00.000Z"`). Shows when information was last modified.
- **scrapedAt**: ISO 8601 timestamp when this data was extracted by the scraper (e.g., `"2026-01-12T20:00:00.000Z"`). Data freshness indicator.
- **isNewBuild**: Boolean indicating if this is a new construction project (e.g., `false`). True for "Neubau" properties.

### Data Quality Notes

- **120+ Fields**: The scraper now captures comprehensive data covering all aspects of properties
- Fields marked as `null` indicate data not available or not applicable for this property
- German text fields may contain HTML formatting (e.g., `<br>` for line breaks)
- Prices are in Euros (€) unless otherwise specified
- Measurements use the metric system (square meters, kilometers)
- Dates and timestamps follow ISO 8601 format (UTC)
- Image URLs include security seals (`ci_seal`) and are CDN-optimized for fast loading
- Geographic coordinates use WGS84 format (longitude, latitude)
- Energy ratings follow German EnEV standards (A+ to H scale)
- Provider data includes ratings, contact methods, and legal information
- Tracking data enables market analysis and trend identification
- All enrichment statuses are included for data quality verification

---

## Benefits of the Immowelt.de Scraper

- Automates German real estate data collection, saving hours of manual research
- Provides detailed, accurate, and structured property data for investment analysis
- Smart pagination and retry logic for comprehensive data extraction
- Captures complete property specifications including amenities and energy ratings
- Extracts contact information for direct publisher outreach
- Reliable performance with proxy support and DataDome bypass
- Supports multiple property types and search filters

---

## Why Choose the Immowelt.de Scraper?

The Immowelt.de Scraper is an indispensable tool for real estate professionals, investors, and market analysts operating in the German property market. It streamlines property research by delivering high-quality, actionable data directly from one of Germany's largest real estate platforms, enabling better investment decisions and comprehensive market analysis.

**Use Cases:**

- Real estate investment research and deal sourcing
- Market analysis and pricing trends
- Lead generation for real estate agents
- Competitive analysis for property developers
- Academic research on German housing market
- Building property databases and search engines

---

## Technical Implementation

The scraper uses a sophisticated two-stage approach:

1. **Search Stage**: Utilizes Immowelt's browser API (`/serp-bff/search`) to retrieve property IDs from search results with smart pagination support.
2. **Detail Stage**: Fetches comprehensive property details from the mobile API endpoint (`/classified/v1/{propertyId}`) with complete specifications, images, and contact information.

**Key Features:**

- DataDome bot protection bypass with retry logic
- Cookie management for seamless pagination
- Proxy rotation support for reliable access
- Concurrent request processing for fast extraction
- Comprehensive error handling and logging

---

## Explore More Scrapers

If you found the Immowelt.de Scraper useful, check out other powerful scrapers and actors at [memo23's Apify profile](https://apify.com/memo23). We offer a wide range of tools to enhance your web scraping and automation needs.

---

## Support

- For issues or feature requests, please use the [Issues](https://console.apify.com/actors/ftbw0YFo17iTQ2qjv/issues) section of this actor.
- For further assistance, contact the author:

- Author's website: [https://muhamed-didovic.github.io/](https://muhamed-didovic.github.io/)
- Email: [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)

---

## Additional Services

- Request customization or a full dataset: [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)
- Need other platforms scraped? Contact [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)
- For API services of this scraper, reach out to [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)
- Custom integrations and automation solutions available

---

## Version History

- **v1.0**: Initial release with browser API search and mobile API detail extraction
- Full support for German property searches
- Comprehensive data extraction including images, amenities, and contact information

---

## Legal & Compliance

This scraper is designed for legitimate business and research purposes. Users are responsible for:

- Complying with Immowelt.de's terms of service
- Respecting robots.txt and rate limiting
- Using scraped data in accordance with GDPR and German data protection laws
- Obtaining necessary permissions for commercial use of data

---

## FAQ

**Q: How many properties can I scrape?**
A: Free users can scrape up to 50 properties per run. Paid users have unlimited access.

**Q: Does the scraper work with all German cities?**
A: Yes, the scraper works with any search URL from Immowelt.de, covering all German locations.

**Q: Are images downloaded?**
A: Image URLs are extracted. You can optionally enable image downloads if needed (contact for custom implementation).

**Q: How often should I scrape to stay updated?**
A: Immowelt updates listings frequently. Weekly or bi-weekly scraping is recommended for most use cases.

**Q: Can I scrape commercial properties?**
A: Yes, the scraper supports all property types including residential, commercial, and land plots.

**Q: What about DataDome protection?**
A: The scraper includes intelligent retry logic and session management to handle DataDome challenges effectively.