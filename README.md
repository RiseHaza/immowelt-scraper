[Immowelt Scraper](https://apify.com/rigelbytes/immowelt-scraper?fpr=data)

The **Immowelt Scraper** is a powerful Apify Actor designed to scrape **UNLIMITED** real estate listings from [immowelt.de](https://www.immowelt.de) for just $30/month. Whether you're looking to gather data for market analysis, lead generation, or personal use, this scraper has you covered.

## Features

- **Unlimited Listings**: Scrape as many listings as you need without restrictions.
- **Retries Implemented**: Ensures reliable data extraction by retrying failed requests.
- **Flexible Data Export**: Export your data in multiple formats:

- JSON
- CSV
- Excel
- API integration for seamless automation.

## Input

The actor accepts the following input:

- location (string, required): The Search String
- pages (int, 60): Number of pages to scrape (one page contains 60 listings)
- proxy (string, optional): The proxy URL to use for scraping. This ensures you can scrape images from multiple listings without being rate-limited.

### 📝 Copy for Use:

```
{
  "location": "Berlin"
}
```

## Pricing

- **$30/month**: Unlimited scraping with retries and flexible export options.
- No hidden fees or limits on usage.

---

## Why Choose This Scraper?

- **Affordable**: Unlimited scraping for just $25/month.
- **Comprehensive**: Extracts all listings and contact information.
- **Easy to Use**: Simple setup and integration with the Apify platform.
- **Reliable**: Built with retry mechanisms to handle network issues.

---

## Recommended Proxy Providers

- ## **Shifter**

- Reliable residential proxies all over the world.
- Cheap rates
- [Order Shifter Now](https://shifter.io/r/YoBB/order)
- Get 10% Off any product, use coupan `rigelbytes-YoBB`.
- ## **OxyLabs**

- **100M+ Proxies**
- Fastest proxies in the market
- Real profile, human-like Residential IPs
- Quality assurance framework for most reliable IPs
- [Get Proxies](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=1366&url_id=7)
- ## **DataImpulse**

- Covers **200+ Counties**
- Reliable Residential Proxies for just $1/GB
- [Get Residential Proxies](https://dataimpulse.com/?aff=89421)

## ![Learn More About Proxies](https://img.shields.io/badge/Learn_More-About_Proxies-blue?style=for-the-badge)

## 🙌 Why Buy Through Our Affiliate Link?

- Exclusive Deals: Some providers may offer special discounts or bonuses when you use our link.
- Support Our Work: Each purchase helps us maintain and improve the tools and services we provide.
- No Extra Cost: You pay the same price, but part of it goes to supporting our efforts.

### Running via Apify Console

You can run this actor from the Apify Console by providing the necessary input parameters.

### Running via API

You can trigger this actor using the Apify API, passing the required input in the request body.

## API Request Example (Python)

```
from apify_client import ApifyClient

# Initialize the ApifyClient with your API token
client = ApifyClient("<YOUR_API_TOKEN>")

# Prepare the Actor input
run_input = {
    "location": "Berlin"
}

# Run the Actor and wait for it to finish
run = client.actor("rigelbytes/immowelt-scraper").call(run_input=run_input)
```

## JavaScript

```
import { ApifyClient } from 'apify-client';

// Initialize the ApifyClient with your API token
const client = new ApifyClient({
    token: '<YOUR_API_TOKEN>',
});

// Prepare Actor input
const input = {
  "location":"Berlin",
};

(async () => {
    // Run the Actor and wait for it to finish
    const run = await client.actor("rigelbytes/immowelt-scraper").call(input);

})();
```

## Running with cURL

```
# Set API token
API_TOKEN=<YOUR_API_TOKEN>

# Prepare Actor input
cat > input.json <<'EOF'
{
  "location": "Berlin"
}
EOF

# Run the Actor
curl "https://api.apify.com/v2/acts/rigelbytes/immowelt-scraper/runs?token=$API_TOKEN" \
  -X POST \
  -d @input.json \
  -H 'Content-Type: application/json'
```

- ## Output

![Output](https://images.apifyusercontent.com/5fngcs691rLNx6xPrSybXLt5nOqx-hzQd6xRbEW-I6w/w:1800/cb:1/aHR0cHM6Ly9naXRodWIuY29tL2ZhaXphbmFsaWkvYXBpZnktaW1hZ2VzL2Jsb2IvbWFpbi9JbW1vd2VsdC1zY3JhcGVyLmdpZj9yYXc9dHJ1ZQ.webp)

## ![View Detailed Data](https://img.shields.io/badge/Detailed-Data-green?style=for-the-badge)

## 🚀 Other Tools by Rigel Bytes

[![Airbnb Images Downloader](https://img.shields.io/badge/Airbnb_Images_Downloader-blue?style=for-the-badge)](https://apify.com/rigelbytes/airbnb-images-downloader)

A focused Airbnb image scraper that extracts all photos from an Airbnb listing page and packages the listing's image files into a compressed archive. The Act...

[![Zillow Scraper](https://img.shields.io/badge/Zillow_Scraper-green?style=for-the-badge)](https://apify.com/rigelbytes/zillow-scraper)

A Zillow-focused web scraper that extracts structured property listing data for real estate analysis and monitoring. The Actor crawls Zillow listings to coll...

[![Zillow Detail Scraper](https://img.shields.io/badge/Zillow_Detail_Scraper-orange?style=for-the-badge)](https://apify.com/rigelbytes/zillow-detail-scraper)

Zillow scraper with customizable proxy support. Extract comprehensive property data, including pricing, images, and location details, using your proxies for better control and efficiency. Check the recommended proxy providers below.

[![Daraz](https://img.shields.io/badge/Daraz-blueviolet?style=for-the-badge)](https://apify.com/rigelbytes/daraz)

A web scraping Actor that extracts product listings and detailed product and seller data from Daraz.pk (Pakistan ecommerce marketplace) for monitoring and an...

[![Airbnb Listing](https://img.shields.io/badge/Airbnb_Listing-red?style=for-the-badge)](https://apify.com/rigelbytes/airbnb-listing)

A web-scraping Actor that bulk-extracts structured Airbnb listing data from listing pages: it retrieves listing metadata, descriptive content, property featu...

[![Google Maps Scraper](https://img.shields.io/badge/Google_Maps_Scraper-yellow?style=for-the-badge)](https://apify.com/rigelbytes/google-maps-scraper)

A Google Maps scraping Actor that extracts structured business profiles and local place intelligence at scale: it crawls Google Maps listings to collect busi...

[![Airbnb Availability Calendar](https://img.shields.io/badge/Airbnb_Availability_Calendar-purple?style=for-the-badge)](https://apify.com/rigelbytes/airbnb-availability-calendar)

Exports Airbnb listing availability calendars by scraping listing pages and producing structured, per-date calendar data. The Actor extracts date entries and...

[![Instagram Profile Scraper](https://img.shields.io/badge/Instagram_Profile_Scraper-pink?style=for-the-badge)](https://apify.com/rigelbytes/instagram-profile-scraper)

A web-scraping Actor that extracts detailed Instagram profile and media metadata from profile pages: it retrieves profile-level metrics (follower/following c...

[![Land.com Scraper](https://img.shields.io/badge/Land.Com_Scraper-cyan?style=for-the-badge)](https://apify.com/rigelbytes/landdotcom-scraper)

A Land.com-focused web scraper that crawls Land.com property listings and extracts structured real estate data for specified geographic areas and listing typ...

[![Airbnb Reviews](https://img.shields.io/badge/Airbnb_Reviews-success?style=for-the-badge)](https://apify.com/rigelbytes/airbnb-reviews)

A web-scraping Actor that extracts unlimited reviews from Airbnb listings: it crawls listing review pages and produces structured review records containing r...

[![FurnishedFinder](https://img.shields.io/badge/Furnishedfinder-important?style=for-the-badge)](https://apify.com/rigelbytes/furnishedfinder)

A web-scraping Actor designed to extract large-scale furnished rental data from Furnished Finder: it crawls listing pages to collect listing metadata (proper...

[![Immobilienscout24](https://img.shields.io/badge/Immobilienscout24-critical?style=for-the-badge)](https://apify.com/rigelbytes/immobilienscout24)

A scraper for immobilienscout24.de that extracts large-scale real estate listing data and contact information, optimized for bulk property data collection, i...

[![Airbnb Listing Urls](https://img.shields.io/badge/Airbnb_Listing_Urls-informational?style=for-the-badge)](https://apify.com/rigelbytes/airbnb-listing-urls)

A web scraper that extracts unlimited Airbnb listings from search queries and returns structured listing metadata for analysis. The Actor crawls Airbnb searc...

[![Instagram Engagement Tool](https://img.shields.io/badge/Instagram_Engagement_Tool-9cf?style=for-the-badge)](https://apify.com/rigelbytes/instagram-engagement-tool)

Analyzes public Instagram profiles by scraping recent posts and profile metadata to compute engagement metrics for images and videos. The Actor extracts prof...

[![Instagram Post Scraper](https://img.shields.io/badge/Instagram_Post_Scraper-blue?style=for-the-badge)](https://apify.com/rigelbytes/instagram-post-scraper)

An Instagram scraping Actor that extracts every post from Instagram profiles and produces structured post-level metadata and media assets for social media an...

[![BBB Scraper](https://img.shields.io/badge/Bbb_Scraper-green?style=for-the-badge)](https://apify.com/rigelbytes/bbb-scraper)

A web-scraping Actor that extracts detailed business listings from the Better Business Bureau (BBB). It crawls BBB listings and produces structured business ...

[![Linkedin Company Scraper](https://img.shields.io/badge/Linkedin_Company_Scraper-orange?style=for-the-badge)](https://apify.com/rigelbytes/linkedin-company-scraper)

A LinkedIn Company Scraper that extracts structured company profile data from LinkedIn company pages for lead generation and competitive intelligence. The Ac...

[![linkedin-company-details](https://img.shields.io/badge/Linkedin_Company_Details-blueviolet?style=for-the-badge)](https://apify.com/rigelbytes/linkedin-company-details)

A LinkedIn Company Scraper for extracting comprehensive company profiles and social content from LinkedIn: it scrapes and returns structured company profile ...

[![Instagram Reel Scraper](https://img.shields.io/badge/Instagram_Reel_Scraper-red?style=for-the-badge)](https://apify.com/rigelbytes/instagram-reel-scraper)

A web-scraping Actor that extracts all Instagram Reels from public profiles and produces structured reel-level metadata for content analysis, research, and m...

[![Rottentomatoes Reviews Scraper](https://img.shields.io/badge/Rottentomatoes_Reviews_Scraper-yellow?style=for-the-badge)](https://apify.com/rigelbytes/rottentomatoes-reviews-scraper)

A web-scraping Apify Actor that extracts user and critic reviews from Rotten Tomatoes pages, producing structured review records for analysis. It crawls unli...

[![Extract Furnished Finder Hosts](https://img.shields.io/badge/Extract_Furnished_Finder_Hosts-purple?style=for-the-badge)](https://apify.com/rigelbytes/furnished-finder-hosts)

Scrapes Furnished Finder listings and extracts structured listing and host profile data for furnished rentals, including listing titles, property types, geol...

[![Trustpilot Reviews Scraper](https://img.shields.io/badge/Trustpilot_Reviews_Scraper-pink?style=for-the-badge)](https://apify.com/rigelbytes/trustpilot-reviews)

A Trustpilot review scraper that collects structured review records and full reviewer profile data at scale. It extracts review content (titles and body text...

[![Furnished Finder Fast](https://img.shields.io/badge/Furnished_Finder_Fast-cyan?style=for-the-badge)](https://apify.com/rigelbytes/furnished-finder-fast)

An Apify Actor for scraping Furnished Finder rental listings and optional host profiles, extracting structured listing data such as photos, textual descripti...

[![Zillow Agents](https://img.shields.io/badge/Zillow_Agents-success?style=for-the-badge)](https://apify.com/rigelbytes/zillow-agents)

A Zillow agent profile scraper that extracts structured agent data from Zillow for location-based queries (city, neighborhood, ZIP). The Actor scrapes agent ...

[![Bayut Scraper](https://img.shields.io/badge/Bayut_Scraper-important?style=for-the-badge)](https://apify.com/rigelbytes/bayut-scraper)

A web-scraping Actor for extracting structured property listings and market intelligence from Bayut.com (UAE). It crawls Bayut property pages and returns str...

[![dubai-listing-scraper](https://img.shields.io/badge/Dubai_Listing_Scraper-critical?style=for-the-badge)](https://apify.com/rigelbytes/dubai-listing-scraper)

A web scraping Actor for Bayut.com that extracts structured UAE property listing data for sale and rent across Dubai, Abu Dhabi and other Emirates. It progra...

[![Tiktok Comment Scraper](https://img.shields.io/badge/Tiktok_Comment_Scraper-informational?style=for-the-badge)](https://apify.com/rigelbytes/tiktok-comment-scraper)

A TikTok comment scraping Actor that extracts all comments from TikTok videos given a video URL. It collects commenter metadata (usernames, display names, pr...

[![Tiktok Engagement Rate](https://img.shields.io/badge/Tiktok_Engagement_Rate-9cf?style=for-the-badge)](https://apify.com/rigelbytes/tiktok-engagement-rate)

A TikTok profile scraper that analyzes public TikTok accounts to extract profile metadata and recent video-level interaction metrics and to compute engagemen...

[![Company Service Finder](https://img.shields.io/badge/Company_Service_Finder-blue?style=for-the-badge)](https://apify.com/rigelbytes/company-service-finder)

Company Service Finder scrapes business listings from Google Search and Google Maps across cities and states, extracts company websites, names, phone numbers...

[![Website Services Finder](https://img.shields.io/badge/Website_Services_Finder-green?style=for-the-badge)](https://apify.com/rigelbytes/website-services-finder)

Website Services Finder extracts and AI-analyzes company services and business information from business websites using web crawling plus large-language and ...

[![Airbnb Address Finder](https://img.shields.io/badge/Airbnb_Address_Finder-orange?style=for-the-badge)](https://apify.com/rigelbytes/airbnb-address-finder)

A web-scraping Apify Actor that bulk-extracts Airbnb listing addresses and comprehensive listing metadata from provided Airbnb listing URLs. It parses listin...

[![Propertyfinder Scraper](https://img.shields.io/badge/Propertyfinder_Scraper-blueviolet?style=for-the-badge)](https://apify.com/rigelbytes/propertyfinder-scraper)

A scraper for propertyfinder.ae that extracts unlimited real estate listings and related metadata at scale. Implements asynchronous concurrency, automatic re...

[![Publix Scraper](https://img.shields.io/badge/Publix_Scraper-red?style=for-the-badge)](https://apify.com/rigelbytes/publix-scraper)

A web scraping Actor for Publix.com that extracts grocery product data from Publix collection pages using a collection URL and a delivery/pickup location to ...

[![Redfin Scraper](https://img.shields.io/badge/Redfin_Scraper-yellow?style=for-the-badge)](https://apify.com/rigelbytes/redfin-scraper)

Redfin Scraper extracts large-scale real estate listing data from Redfin search and city pages and returns structured property records for downstream analysi...

[![Instacart Scraper](https://img.shields.io/badge/Instacart_Scraper-purple?style=for-the-badge)](https://apify.com/rigelbytes/instacart-scraper)

A web-scraping Actor that extracts structured product data from instacart.com using a collection/search keyword combined with a delivery or pickup location; ...

[![Homedepot Scraper](https://img.shields.io/badge/Homedepot_Scraper-pink?style=for-the-badge)](https://apify.com/rigelbytes/homedepot-scraper)

A web scraper for homedepot.com that crawls collection pages and performs location-aware scraping (delivery or pickup) to extract structured product data. Th...

[![Doctify Scraper](https://img.shields.io/badge/Doctify_Scraper-cyan?style=for-the-badge)](https://apify.com/rigelbytes/doctify-scraper)

A web scraping Actor that extracts structured healthcare provider and practice data from doctify.com starting from a Doctify search-results URL. The Actor ha...

[![Facebook Ads Scraper](https://img.shields.io/badge/Facebook_Ads_Scraper-success?style=for-the-badge)](https://apify.com/rigelbytes/facebook-ads-scraper)

Extracts structured ad data from the Facebook Ads Library using a search URL: scrapes ad metadata and creative assets (ad copy, titles, captions), destinatio...

[![Ticketmaster Scraper](https://img.shields.io/badge/Ticketmaster_Scraper-important?style=for-the-badge)](https://apify.com/rigelbytes/ticketmaster-scraper)

A Ticketmaster-focused web scraper that extracts structured event metadata by location and date range for event monitoring, market research, and entertainmen...

[![Scrape Instagram Creators](https://img.shields.io/badge/Scrape_Instagram_Creators-critical?style=for-the-badge)](https://apify.com/rigelbytes/scrape-instagram-creators)

Scrape Instagram Creators is an Instagram profile and media scraper that extracts detailed creator profile metadata and media-level information. It captures ...

[![Immowelt Property Scraper](https://img.shields.io/badge/Immowelt_Property_Scraper-informational?style=for-the-badge)](https://apify.com/rigelbytes/immowelt-property-scraper)

A scraper for immowelt.de (Germany) that harvests large volumes of real estate listings and returns structured property records for analysis. It extracts lis...

[![Immobilienscout24-scraper](https://img.shields.io/badge/Immobilienscout24_Scraper-9cf?style=for-the-badge)](https://apify.com/rigelbytes/immobilienscout24-scraper)

A web scraping Actor that extracts large volumes of real estate listings and contact information from immobilienscout24.de, focused on German property market...

[![Instagram Creator Stats](https://img.shields.io/badge/Instagram_Creator_Stats-blue?style=for-the-badge)](https://apify.com/rigelbytes/instagram-creator-stats)

A scraping and analytics Actor that extracts Instagram profile metadata and per-post media details to compute engagement metrics for creator/influencer analy...

[![Etsy Scraper](https://img.shields.io/badge/Etsy_Scraper-green?style=for-the-badge)](https://apify.com/rigelbytes/etsy-scraper)

A web-scraping Actor that extracts structured product data from Etsy.com from category pages, search results, or individual product list URLs. It crawls list...

[![Rightmove Scraper](https://img.shields.io/badge/Rightmove_Scraper-orange?style=for-the-badge)](https://apify.com/rigelbytes/rightmove-scraper)

Scrapes Rightmove.co.uk property listings and returns structured property records for real estate data extraction and analysis. The Actor crawls Rightmove se...

[![Outdoorsy Scraper](https://img.shields.io/badge/Outdoorsy_Scraper-blueviolet?style=for-the-badge)](https://apify.com/rigelbytes/outdoorsy-scraper)

A web scraping Actor that extracts rental listing data from outdoorsy.com search result pages. It processes multiple search result URLs in a single run, issu...

[![Instagram Comment Scraper](https://img.shields.io/badge/Instagram_Comment_Scraper-red?style=for-the-badge)](https://apify.com/rigelbytes/instagram-comment-scraper)

A web scraping Actor that extracts all comments from Instagram posts and reels given their URLs; it captures commenter metadata (username, display name, prof...

## Understanding Proxies:

When scraping data or browsing anonymously, proxies are essential. They act as intermediaries, masking your original IP address and allowing you to send requests from another location.

### Why Use Proxies?

- Avoid IP Blocks: By routing requests through proxies, you prevent the target website from recognizing your IP as a scraper or spammer.
- Access Geo-restricted Content: Proxies let you access content or websites restricted by location.
- Enhance Anonymity: Hide your actual IP, ensuring privacy while scraping or browsing.

### Types of Proxies

1. Residential Proxies

- Real IP addresses provided by ISPs to home users.
- They mimic regular users, making them harder to detect.
- Best for: Long-term, undetectable scraping, and avoiding blocks.
2. Data Center Proxies

- IP addresses from servers in data centers.
- Faster and cheaper than residential proxies but easier to detect and block.
- Best for: High-speed scraping, but with a higher risk of detection.
3. Mobile Proxies

- IPs provided by mobile carriers (3G/4G/5G networks).
- Very difficult to detect, as they appear as regular mobile users.
- Best for: Mobile-related scraping or avoiding sophisticated blocks.

### Rotating Proxies vs. Straight Proxies

- Rotating Proxies: Every request you send goes through a different proxy, making it harder for websites to detect patterns.
- Straight Proxies: All requests are sent through the same proxy, making it easier to track your IP.

## About Rigel Bytes

[Rigel Bytes](https://www.rigelbytes.com/) specializes in web scraping, automation, and data analytics. We help businesses extract and leverage valuable data for informed decision-making.

## Contact Us

Ready to unlock the power of data? Reach out to us at ([contact@rigelbytes.com](mailto:contact@rigelbytes.com)) or [book an appointment](https://cal.com/faizanali/appointments) with us to learn more about how we can help you achieve your data goals.

## Detailed Data

```
[
  {
    "brand": "immowelt",
    "id": "25979LCR1HET",
    "status": "Published",
    "metadata": {
      "id": "25979LCR1HET",
      "legacyId": "5e521041-9fb0-4bd3-9313-bc73e58f88c6",
      "creationDate": "2025-11-14T19:06:19.627Z",
      "updateDate": "2025-11-14T19:07:12.726Z",
      "status": {
        "status": true,
        "enrichments": {
          "contactSettings": false,
          "geo": false,
          "intermediary": false,
          "media": false,
          "onlineId": false
        }
      }
    },
    "location": {
      "address": {
        "country": "DEU",
        "city": "Berlin",
        "zipCode": "12203",
        "street": "Unter den Eichen 55",
        "district": "Lichterfelde"
      },
      "isAddressPublished": true
    },
    "hardFacts": {
      "title": "Wohnung zum Kauf",
      "titleAdditions": ["provisionsfrei"],
      "keyfacts": ["5 Zimmer", "131 m²", "1. Geschoss"],
      "facts": [
        {
          "type": "numberOfRooms",
          "value": "5 Zimmer",
          "splitValue": "5",
          "label": "Zimmer"
        },
        {
          "type": "livingSpace",
          "value": "131 m²",
          "splitValue": "131",
          "label": "m²"
        },
        {
          "type": "numberOfFloors",
          "value": "1. Geschoss",
          "splitValue": "1.",
          "label": "Geschoss"
        }
      ],
      "price": {
        "value": "798.500 €",
        "formatted": "798.500 €",
        "additionalInformation": "6.095 €/m²",
        "addition": {
          "value": "6.095 €/m²",
          "ariaLabel": "6095,42 Euro pro Quadratmeter"
        },
        "financialLink": {
          "href": "https://www.immowelt.de/immobilienfinanzierung-anfragen/?price=798500&originvariant=expose-hardfacts&zip=12203&city=Berlin&classifiedid=5e521041-9fb0-4bd3-9313-bc73e58f88c6&m=classified_detail_request_offer_find_financing_partners_step1",
          "label": "Finanzierung anfragen",
          "partnerName": "KFW"
        },
        "ariaLabel": "798500 €"
      }
    },
    "gallery": {
      "images": [
        {
          "key": "815dd29e-ca15-40b1-b745-2e31f08ad9b4",
          "url": "https://mms.immowelt.de/8/1/5/d/815dd29e-ca15-40b1-b745-2e31f08ad9b4.jpg?ci_seal=e40bfd1d22097130d7e859d569758cc8e0127df1",
          "description": "Inspiration Schlafzimmer",
          "alt": "Wohnung zum Kauf provisionsfrei 798.500 € 5 Zimmer 131 m² 1. Geschoss Unter den Eichen 55 Lichterfelde Berlin 12203",
          "title": "Inspiration Schlafzimmer",
          "ariaLabel": "Inspiration Schlafzimmer",
          "classification": {
            "name": "BEDROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "794e009c-96db-4af0-a173-207c9a1f0d2e",
          "url": "https://mms.immowelt.de/7/9/4/e/794e009c-96db-4af0-a173-207c9a1f0d2e.jpg?ci_seal=97da0f1ff3609fbca9048e267fe7a5cba340b6ca",
          "description": "Inspiration Wohnzimmer",
          "title": "Inspiration Wohnzimmer",
          "ariaLabel": "Inspiration Wohnzimmer",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "7e9e1889-9668-499d-bae5-94db0c0df11a",
          "url": "https://mms.immowelt.de/7/e/9/e/7e9e1889-9668-499d-bae5-94db0c0df11a.jpg?ci_seal=f8fb4a9ce6c73efa1b1aa1d42c1ec7266ac162ea",
          "description": "Inspiration Home Office",
          "title": "Inspiration Home Office",
          "ariaLabel": "Inspiration Home Office",
          "classification": {
            "name": "HOME_OFFICE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "cc97a03b-e8a0-4ffc-9e00-8d32c606f30d",
          "url": "https://mms.immowelt.de/c/c/9/7/cc97a03b-e8a0-4ffc-9e00-8d32c606f30d.jpg?ci_seal=7d6806383ee5fd49833578393075975a10874d28",
          "description": "Inspiration Küche",
          "title": "Inspiration Küche",
          "ariaLabel": "Inspiration Küche",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "3179d97f-344f-432c-b9fd-15d815709f03",
          "url": "https://mms.immowelt.de/3/1/7/9/3179d97f-344f-432c-b9fd-15d815709f03.jpg?ci_seal=2051af36d91fca53fc9eea6da52c2963d49fb94a",
          "description": "Inspiration Kinderzimmer",
          "title": "Inspiration Kinderzimmer",
          "ariaLabel": "Inspiration Kinderzimmer",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "a4f44829-613a-4445-91f7-6182fa225fe0",
          "url": "https://mms.immowelt.de/a/4/f/4/a4f44829-613a-4445-91f7-6182fa225fe0.jpg?ci_seal=d6b5c6056a205f2afe64dc5d5b9d9e7c74f3d1b2",
          "description": "Gründerzeitbau im Grünen",
          "title": "Gründerzeitbau im Grünen",
          "ariaLabel": "Gründerzeitbau im Grünen",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "2899306c-fe87-47e4-97d3-29e5df8a33a6",
          "url": "https://mms.immowelt.de/2/8/9/9/2899306c-fe87-47e4-97d3-29e5df8a33a6.jpg?ci_seal=3828820e3bb1256948ba11030c166d33ad4115d0",
          "description": "Gründerzeitbau im Grünen",
          "title": "Gründerzeitbau im Grünen",
          "ariaLabel": "Gründerzeitbau im Grünen",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "28874041-7186-47ea-9da0-f2e6e3f0f97c",
          "url": "https://mms.immowelt.de/2/8/8/7/28874041-7186-47ea-9da0-f2e6e3f0f97c.jpg?ci_seal=c179add32b9d3ceea7d60a1bee252731fbc83ead",
          "description": "Schlafzimmer mit Balkon",
          "title": "Schlafzimmer mit Balkon",
          "ariaLabel": "Schlafzimmer mit Balkon",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "17f8896c-bdbc-4f47-b1b5-6c1eae58895d",
          "url": "https://mms.immowelt.de/1/7/f/8/17f8896c-bdbc-4f47-b1b5-6c1eae58895d.jpg?ci_seal=8b3a84720f7094493a21d7dc92910aeed84bdef3",
          "description": "Schlafzimmer mit Balkon",
          "title": "Schlafzimmer mit Balkon",
          "ariaLabel": "Schlafzimmer mit Balkon",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "c4eb60d9-bf21-4852-a942-bff215c475e0",
          "url": "https://mms.immowelt.de/c/4/e/b/c4eb60d9-bf21-4852-a942-bff215c475e0.jpg?ci_seal=c28acecda103705e8248c4abc70664cf3ba7fdf0",
          "description": "Ruhiger sonniger Balkon",
          "title": "Ruhiger sonniger Balkon",
          "ariaLabel": "Ruhiger sonniger Balkon",
          "classification": {
            "name": "BALCONY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "e16dfb43-2185-4b11-b671-de2aa4b0bc88",
          "url": "https://mms.immowelt.de/e/1/6/d/e16dfb43-2185-4b11-b671-de2aa4b0bc88.jpg?ci_seal=73979347b713f3bb0134b7d1538521091072e5ca",
          "description": "Ruhiger sonniger Balkon",
          "title": "Ruhiger sonniger Balkon",
          "ariaLabel": "Ruhiger sonniger Balkon",
          "classification": {
            "name": "BALCONY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "280db3df-6cc3-49e4-a329-6e7a6538f84a",
          "url": "https://mms.immowelt.de/2/8/0/d/280db3df-6cc3-49e4-a329-6e7a6538f84a.jpg?ci_seal=ae8c9ac61d2554a8119141c25105f3897efda7e9",
          "description": "Kinderzimmer 1",
          "title": "Kinderzimmer 1",
          "ariaLabel": "Kinderzimmer 1",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "ef90242e-151b-45d5-8892-c7265189eedc",
          "url": "https://mms.immowelt.de/e/f/9/0/ef90242e-151b-45d5-8892-c7265189eedc.jpg?ci_seal=0e1b5f149b9d49e2760a648eccc8763f4ac7c8ae",
          "description": "Tageslichtbad 1 mit Badewanne",
          "title": "Tageslichtbad 1 mit Badewanne",
          "ariaLabel": "Tageslichtbad 1 mit Badewanne",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "046423d4-7b16-4099-be37-ddec988d9a12",
          "url": "https://mms.immowelt.de/0/4/6/4/046423d4-7b16-4099-be37-ddec988d9a12.jpg?ci_seal=26499ed56eb5e7f948d89c729bb52cb9878f2b22",
          "description": "Tageslichtbad 1 mit Badewanne",
          "title": "Tageslichtbad 1 mit Badewanne",
          "ariaLabel": "Tageslichtbad 1 mit Badewanne",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "8f0c115d-701d-4e46-8a9c-5a3ce56a8a63",
          "url": "https://mms.immowelt.de/8/f/0/c/8f0c115d-701d-4e46-8a9c-5a3ce56a8a63.jpg?ci_seal=8527da0a57de00a03fdccccadeb60e91dede57fc",
          "description": "Home Office",
          "title": "Home Office",
          "ariaLabel": "Home Office",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "714cd82a-e0c8-44e2-b491-93cb2b6be31b",
          "url": "https://mms.immowelt.de/7/1/4/c/714cd82a-e0c8-44e2-b491-93cb2b6be31b.jpg?ci_seal=2eaf599304705eceb43214c7be6226a7c5eaf464",
          "description": "Home Office",
          "title": "Home Office",
          "ariaLabel": "Home Office",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "7d95d2cc-a36b-446b-9cf1-47a99fecf4fc",
          "url": "https://mms.immowelt.de/7/d/9/5/7d95d2cc-a36b-446b-9cf1-47a99fecf4fc.jpg?ci_seal=50e79b52ed25f56f50ab8a3ac180468fc698d54e",
          "description": "Küche",
          "title": "Küche",
          "ariaLabel": "Küche",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "fb7c82b0-719e-4390-b89f-0deacccedce4",
          "url": "https://mms.immowelt.de/f/b/7/c/fb7c82b0-719e-4390-b89f-0deacccedce4.jpg?ci_seal=213ac9eab7e49b3b7a38e4278f90d383551526a2",
          "description": "Flur - Diele",
          "title": "Flur - Diele",
          "ariaLabel": "Flur - Diele",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "66f9f3b3-b3c6-4065-93ec-c7c762600214",
          "url": "https://mms.immowelt.de/6/6/f/9/66f9f3b3-b3c6-4065-93ec-c7c762600214.jpg?ci_seal=4599c53b7006c8e428fb310349bd3e40666de1ac",
          "description": "Flur - Diele",
          "title": "Flur - Diele",
          "ariaLabel": "Flur - Diele",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "369de335-13a7-4cd7-ae82-aa5efa96ef28",
          "url": "https://mms.immowelt.de/3/6/9/d/369de335-13a7-4cd7-ae82-aa5efa96ef28.jpg?ci_seal=4f5535f973b52114c472fc98518a55087e1a57a5",
          "description": "Tageslichtbad 2 mit Badewanne",
          "title": "Tageslichtbad 2 mit Badewanne",
          "ariaLabel": "Tageslichtbad 2 mit Badewanne",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "1877ae26-4874-41cd-b9eb-cc1a27a553e8",
          "url": "https://mms.immowelt.de/1/8/7/7/1877ae26-4874-41cd-b9eb-cc1a27a553e8.jpg?ci_seal=94e029c10ca6a72825281f760953c58a2f6269ff",
          "description": "Tageslichtbad 2 mit Badewanne",
          "title": "Tageslichtbad 2 mit Badewanne",
          "ariaLabel": "Tageslichtbad 2 mit Badewanne",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "8c34d26d-2041-4bd9-afab-6cd6fc90cec2",
          "url": "https://mms.immowelt.de/8/c/3/4/8c34d26d-2041-4bd9-afab-6cd6fc90cec2.jpg?ci_seal=3cc504101f8cbb6268427a4e8a50c5f6a29ac799",
          "description": "Tageslichtbad 2 mit Badewanne",
          "title": "Tageslichtbad 2 mit Badewanne",
          "ariaLabel": "Tageslichtbad 2 mit Badewanne",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "95d9f19d-361e-4ec8-8be9-23bc057e381b",
          "url": "https://mms.immowelt.de/9/5/d/9/95d9f19d-361e-4ec8-8be9-23bc057e381b.jpg?ci_seal=db1bf2ebf5ce8aabbca7972e2e43f8eff91a9b04",
          "description": "Detailshot Badezimmer",
          "title": "Detailshot Badezimmer",
          "ariaLabel": "Detailshot Badezimmer",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "d8b5f5c5-d126-4c14-84c1-a83b83bdaef7",
          "url": "https://mms.immowelt.de/d/8/b/5/d8b5f5c5-d126-4c14-84c1-a83b83bdaef7.jpg?ci_seal=8f7fe20285443d16830143941b54a0612b9da724",
          "description": "Kinderzimmer 2",
          "title": "Kinderzimmer 2",
          "ariaLabel": "Kinderzimmer 2",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "fb40ee9d-1cf1-4b3a-9acc-d121e501ecc4",
          "url": "https://mms.immowelt.de/f/b/4/0/fb40ee9d-1cf1-4b3a-9acc-d121e501ecc4.jpg?ci_seal=c60b61865b6d6e9184c26f89b13439ce2366c6c3",
          "description": "Kinderzimmer 2",
          "title": "Kinderzimmer 2",
          "ariaLabel": "Kinderzimmer 2",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "23f9e3b8-1679-4f24-b4fe-322a06a41baa",
          "url": "https://mms.immowelt.de/2/3/f/9/23f9e3b8-1679-4f24-b4fe-322a06a41baa.jpg?ci_seal=1ce7a730da8f45bddc93246d355ff0716aa82b0b",
          "description": "Wohnzimmer mit Balkon",
          "title": "Wohnzimmer mit Balkon",
          "ariaLabel": "Wohnzimmer mit Balkon",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "afd491dc-bc61-4c8c-836b-9fe6624dc5b7",
          "url": "https://mms.immowelt.de/a/f/d/4/afd491dc-bc61-4c8c-836b-9fe6624dc5b7.jpg?ci_seal=82de78c05ba2c6c8dcc80ca5410ce38633a43936",
          "description": "Wohnzimmer mit Balkon",
          "title": "Wohnzimmer mit Balkon",
          "ariaLabel": "Wohnzimmer mit Balkon",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "c199386c-859a-4713-8e76-bd2283fc083e",
          "url": "https://mms.immowelt.de/c/1/9/9/c199386c-859a-4713-8e76-bd2283fc083e.jpg?ci_seal=6d77a5ba6d11fccec59008d4455c286bd647ab33",
          "description": "Balkon mit Blick ins Grüne",
          "title": "Balkon mit Blick ins Grüne",
          "ariaLabel": "Balkon mit Blick ins Grüne",
          "classification": {
            "name": "BALCONY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "c280b47b-e04e-4220-8511-5a606ceb0adb",
          "url": "https://mms.immowelt.de/c/2/8/0/c280b47b-e04e-4220-8511-5a606ceb0adb.jpg?ci_seal=462de6d8d124f7ed54652e52bd24af6d948c3e89",
          "description": "Umgebung: FU Berlin",
          "title": "Umgebung: FU Berlin",
          "ariaLabel": "Umgebung: FU Berlin",
          "classification": {
            "name": "LOGO",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "e721e200-33fe-4976-817a-4145229e9ab1",
          "url": "https://mms.immowelt.de/e/7/2/1/e721e200-33fe-4976-817a-4145229e9ab1.jpg?ci_seal=521f13957fab8a787c5c42b16264c2b3071fb9ef",
          "description": "Umgebung: Teltowkanal",
          "title": "Umgebung: Teltowkanal",
          "ariaLabel": "Umgebung: Teltowkanal",
          "classification": {
            "name": "YARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "1bb998e9-f294-45b4-8118-ad15fa1a30ba",
          "url": "https://mms.immowelt.de/1/b/b/9/1bb998e9-f294-45b4-8118-ad15fa1a30ba.jpg?ci_seal=898c2b9cc1bd0d298384491626bb573d42e3aaec",
          "description": "Umgebung: Kirschblütenallee",
          "title": "Umgebung: Kirschblütenallee",
          "ariaLabel": "Umgebung: Kirschblütenallee",
          "classification": {
            "name": "YARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "157604d0-3524-4c0c-8da3-c754cfddd092",
          "url": "https://mms.immowelt.de/1/5/7/6/157604d0-3524-4c0c-8da3-c754cfddd092.jpg?ci_seal=e10d08054dae7ad476008690c1ea874d99ca7a8d",
          "description": "Umgebung: Botanischer Garten",
          "title": "Umgebung: Botanischer Garten",
          "ariaLabel": "Umgebung: Botanischer Garten",
          "classification": {
            "name": "HOUSE_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ],
      "floorplans": [
        {
          "key": "6b263b1b-0818-4d08-b6c7-72bb15801cce",
          "url": "https://mms.immowelt.de/6/b/2/6/6b263b1b-0818-4d08-b6c7-72bb15801cce.jpg?ci_seal=1d363553263db3823e2afadf8eb6d1baf14c7e73",
          "description": "Grundriss 3D + Visualisierung",
          "alt": "Wohnung zum Kauf provisionsfrei 798.500 € 5 Zimmer 131 m² 1. Geschoss Unter den Eichen 55 Lichterfelde Berlin 12203",
          "title": "Grundriss 3D + Visualisierung",
          "ariaLabel": "Grundriss 3D + Visualisierung",
          "classification": {
            "name": "FLOORPLAN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "72424fbc-fb60-40c4-99e0-1f9909c3edd2",
          "url": "https://mms.immowelt.de/7/2/4/2/72424fbc-fb60-40c4-99e0-1f9909c3edd2.jpg?ci_seal=d04b7ed47f6268acf0d0a0194a4bc76133ceca49",
          "description": "Grundriss 3D + Visualisierung",
          "title": "Grundriss 3D + Visualisierung",
          "ariaLabel": "Grundriss 3D + Visualisierung",
          "classification": {
            "name": "FLOORPLAN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ],
      "availableFeatures": {
        "floorplans": true,
        "virtualTours": false
      }
    },
    "tracking": {
      "name": "classified",
      "list_name": "classified_detail_similars_bottom",
      "id": "25979LCR1HET",
      "price": 798500,
      "estate_type": "av_2",
      "distribution_type": "2",
      "country": "Germany",
      "city": "Berlin",
      "region": "Berlin",
      "province": "Berlin",
      "currency": "EUR",
      "zip_code": "12203",
      "building_state": "FULLY_RENOVATED",
      "legacy_id": "5e521041-9fb0-4bd3-9313-bc73e58f88c6",
      "product_type": "standard",
      "client_id": "678606"
    },
    "provider": {
      "intermediaryCard": {
        "title": "ohne-makler.net - Immobilien selbst vermarkten",
        "subtitle": "Gewerblicher Anbieter",
        "display": true,
        "logoUrl": "https://mms.immowelt.de/b/a/7/8/ba78ace8-18c8-4054-a182-3a0844e0884f.jpg?ci_seal=631ed3080956ae691db156718b40a9af8d063437",
        "logoHref": "https://www.immowelt.de/profil/5ba347d760714ccc97f0f7d38252a296"
      },
      "contactCard": {
        "title": "Privat vom Eigentümer",
        "subtitle": "Dein Kontakt",
        "display": true,
        "logoUrl": null
      },
      "website": "https://www.ohne-makler.net/",
      "isPrivateOwner": false,
      "profileUrl": "https://www.immowelt.de/profil/5ba347d760714ccc97f0f7d38252a296",
      "imprintUrl": "https://www.immowelt.de/profil/5ba347d760714ccc97f0f7d38252a296#impressum",
      "agencyLegalInformations": [],
      "publisherType": "AGENCY",
      "displayLinks": true,
      "badge": {
        "title": "Premium Partner",
        "imageUrl": "https://s.immowelt.org/shared/images/partner-badges/premium-partner.svg"
      },
      "address": "Humboldtstr. 25 A, 21509 Glinde",
      "agencyStrip": {
        "agencyColor": "#133C7E",
        "fontColor": "#FFFFFF"
      }
    },
    "cardProvider": {
      "title": "Privat vom Eigentümer",
      "subtitle": "Dein Kontakt",
      "logoUrl": null,
      "agencyStrip": {
        "agencyColor": "#133C7E",
        "fontColor": "#FFFFFF"
      }
    },
    "energyClass": "E",
    "mainDescription": {
      "headline": "Kernsanierter Altbautraum mit hohen Decken, Badewanne & Balkon (sofort provisionsfrei einziehen)",
      "description": "360°-Rundgang: https://www.ohne-makler.net/panorama/407162/ Frisch saniert - sofort bezugsfrei &amp; keine Provision (Verkauf direkt durch den Eigentümer) Liebevoll kernsanierte Altbauwohnung im 1. O...",
      "metadata": {
        "language": "de"
      }
    },
    "type": "PROFESSIONAL",
    "url": "https://www.immowelt.de/expose/5e521041-9fb0-4bd3-9313-bc73e58f88c6",
    "portal": "immowelt",
    "rawData": {
      "distributionType": "BUY",
      "propertyType": "APARTMENT",
      "geoIdHierarchy": [
        {
          "id": "NBH2DE91302107",
          "typeKey": "NBH2"
        },
        {
          "id": "AD09DE480",
          "typeKey": "AD09"
        },
        {
          "id": "AD08DE8634",
          "typeKey": "AD08"
        },
        {
          "id": "AD06DE326",
          "typeKey": "AD06"
        },
        {
          "id": "AD04DE11",
          "typeKey": "AD04"
        },
        {
          "id": "AD02DE1",
          "typeKey": "AD02"
        }
      ],
      "price": 798500,
      "offererMarketingKey": "407162",
      "providercity": "Glinde",
      "providerzipcode": "21509",
      "surface": {
        "main": 131,
        "plot": null
      },
      "nbroom": 5,
      "contactLocationEnabled": true
    },
    "tags": {
      "isExclusive": false,
      "has3DVisit": false,
      "hasBrokerageFee": false,
      "isNew": true,
      "isHdExclusive": false
    },
    "display": "classified",
    "title": "Wohnung zum Kauf",
    "image": "https://mms.immowelt.de/8/1/5/d/815dd29e-ca15-40b1-b745-2e31f08ad9b4.jpg?ci_seal=e40bfd1d22097130d7e859d569758cc8e0127df1",
    "price": 798500,
    "facts": [
      {
        "type": "numberOfRooms",
        "value": "5 Zimmer",
        "splitValue": "5",
        "label": "Zimmer"
      },
      {
        "type": "livingSpace",
        "value": "131 m²",
        "splitValue": "131",
        "label": "m²"
      },
      {
        "type": "numberOfFloors",
        "value": "1. Geschoss",
        "splitValue": "1.",
        "label": "Geschoss"
      }
    ],
    "city": "Berlin"
  },
  {
    "brand": "immowelt",
    "id": "25J65GGQB6RZ",
    "status": "Published",
    "metadata": {
      "id": "25J65GGQB6RZ",
      "legacyId": "196e56a5-a9f4-4f96-93da-69e2845dabbe",
      "creationDate": "2025-11-14T08:48:18.077Z",
      "updateDate": "2025-11-15T06:07:32.773Z",
      "status": {
        "status": true,
        "enrichments": {
          "contactSettings": false,
          "geo": false,
          "intermediary": false,
          "media": false,
          "onlineId": false
        }
      }
    },
    "location": {
      "address": {
        "country": "DEU",
        "city": "Berlin",
        "zipCode": "12559",
        "street": "Staudernheimer Str. 35b",
        "district": "Müggelheim"
      },
      "isAddressPublished": true
    },
    "hardFacts": {
      "title": "Einfamilienhaus zum Kauf",
      "titleAdditions": ["provisionsfrei"],
      "keyfacts": ["6 Zimmer", "200 m²", "600 m² Grundstück"],
      "facts": [
        {
          "type": "numberOfRooms",
          "value": "6 Zimmer",
          "splitValue": "6",
          "label": "Zimmer"
        },
        {
          "type": "livingSpace",
          "value": "200 m²",
          "splitValue": "200",
          "label": "m²"
        },
        {
          "type": "plotSpace",
          "value": "600 m² Grundstück",
          "splitValue": "600",
          "label": "m² Grundstück"
        }
      ],
      "price": {
        "value": "780.000 €",
        "formatted": "780.000 €",
        "additionalInformation": "3.900 €/m²",
        "addition": {
          "value": "3.900 €/m²",
          "ariaLabel": "3900 Euro pro Quadratmeter"
        },
        "financialLink": {
          "href": "https://www.immowelt.de/immobilienfinanzierung-anfragen/?price=780000&originvariant=expose-hardfacts&zip=12559&city=Berlin&classifiedid=196e56a5-a9f4-4f96-93da-69e2845dabbe&m=classified_detail_request_offer_find_financing_partners_step1",
          "label": "Finanzierung anfragen",
          "partnerName": "KFW"
        },
        "ariaLabel": "780000 €"
      }
    },
    "gallery": {
      "images": [
        {
          "key": "9296655e-ef26-48b3-8f11-a56664c8652e",
          "url": "https://mms.immowelt.de/9/2/9/6/9296655e-ef26-48b3-8f11-a56664c8652e.jpg?ci_seal=5be98c30366636616219a78de202da1ccadf48cb",
          "description": "Außenansicht",
          "alt": "Einfamilienhaus zum Kauf provisionsfrei 780.000 € 6 Zimmer 200 m² 600 m² Grundstück Staudernheimer Str. 35b Müggelheim Berlin 12559",
          "title": "Außenansicht",
          "ariaLabel": "Außenansicht",
          "classification": {
            "name": "HOUSE_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "aa25574f-f6ae-46e3-aa99-3fd99ae1a7b3",
          "url": "https://mms.immowelt.de/a/a/2/5/aa25574f-f6ae-46e3-aa99-3fd99ae1a7b3.jpg?ci_seal=1f340012e619bbeed8a1d015a2758c0d16857d07",
          "description": "EG Diele mit Blick auf Kamin",
          "title": "EG Diele mit Blick auf Kamin",
          "ariaLabel": "EG Diele mit Blick auf Kamin",
          "classification": {
            "name": "BALCONY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "0174f428-6568-4521-88ec-0fb7b78322b9",
          "url": "https://mms.immowelt.de/0/1/7/4/0174f428-6568-4521-88ec-0fb7b78322b9.jpg?ci_seal=d167fcda98ed10567eef7a2606eb9a1a3d04ee7a",
          "description": "EG Gästebad ",
          "title": "EG Gästebad ",
          "ariaLabel": "EG Gästebad ",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "8ab03735-4c83-40cb-ac7f-31e804b25844",
          "url": "https://mms.immowelt.de/8/a/b/0/8ab03735-4c83-40cb-ac7f-31e804b25844.jpg?ci_seal=9620e4162e60f3349aa599c129cbf2742cfd484d",
          "description": "EG Essbereich mit Panorama ",
          "title": "EG Essbereich mit Panorama ",
          "ariaLabel": "EG Essbereich mit Panorama ",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "4c39e3c1-8aa6-4b8a-8d4f-a3f7aaed6120",
          "url": "https://mms.immowelt.de/4/c/3/9/4c39e3c1-8aa6-4b8a-8d4f-a3f7aaed6120.jpg?ci_seal=6e771b42db1fdb92a6a0b326a74ce60aeae66004",
          "description": "EG Wohnbereich und Kamin",
          "title": "EG Wohnbereich und Kamin",
          "ariaLabel": "EG Wohnbereich und Kamin",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "ba902c3f-8628-4321-89f2-29ebe86a5815",
          "url": "https://mms.immowelt.de/b/a/9/0/ba902c3f-8628-4321-89f2-29ebe86a5815.jpg?ci_seal=d998900e9bfd52244349c47ead8df13b845e3a94",
          "description": "EG Küche",
          "title": "EG Küche",
          "ariaLabel": "EG Küche",
          "classification": {
            "name": "KITCHEN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "c6f2aa65-4f17-4c20-98d6-94f8c8495c37",
          "url": "https://mms.immowelt.de/c/6/f/2/c6f2aa65-4f17-4c20-98d6-94f8c8495c37.jpg?ci_seal=3e10f30f2aa9d03563a5e5c86f5afd17ce98d7f5",
          "description": "OG Kind 1 schlafen",
          "title": "OG Kind 1 schlafen",
          "ariaLabel": "OG Kind 1 schlafen",
          "classification": {
            "name": "BEDROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "da3fd5d3-6679-4d51-91f9-02617b9cf21d",
          "url": "https://mms.immowelt.de/d/a/3/f/da3fd5d3-6679-4d51-91f9-02617b9cf21d.jpg?ci_seal=0b02cacdc9ccd22130eb964fd0704a7c9759afbb",
          "description": "OG Kind 2 Blick auf Garten",
          "title": "OG Kind 2 Blick auf Garten",
          "ariaLabel": "OG Kind 2 Blick auf Garten",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "0ca62983-d594-4401-83a1-eab5767ecb7a",
          "url": "https://mms.immowelt.de/0/c/a/6/0ca62983-d594-4401-83a1-eab5767ecb7a.jpg?ci_seal=4bd9e9901425afab9f7b62a0b8982f10ccf61000",
          "description": "OG Kind 2 schlafen",
          "title": "OG Kind 2 schlafen",
          "ariaLabel": "OG Kind 2 schlafen",
          "classification": {
            "name": "BEDROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "a77a7407-6d41-4243-b883-2225ded9a6c9",
          "url": "https://mms.immowelt.de/a/7/7/a/a77a7407-6d41-4243-b883-2225ded9a6c9.jpg?ci_seal=0cf96176ba9b5bcdd90352be4da900be19c73c47",
          "description": "OG schlafen Eltern",
          "title": "OG schlafen Eltern",
          "ariaLabel": "OG schlafen Eltern",
          "classification": {
            "name": "BEDROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "0262d4c5-677b-49f5-a92f-d0a7497a2da7",
          "url": "https://mms.immowelt.de/0/2/6/2/0262d4c5-677b-49f5-a92f-d0a7497a2da7.jpg?ci_seal=4ab1cc5b329f7dad1056e4e7ccd28bec8858ad5b",
          "description": "OG Masterbad WC",
          "title": "OG Masterbad WC",
          "ariaLabel": "OG Masterbad WC",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "b17551ca-5e19-459f-98c6-587e1109bed4",
          "url": "https://mms.immowelt.de/b/1/7/5/b17551ca-5e19-459f-98c6-587e1109bed4.jpg?ci_seal=efaacb1af2e9276ea3b9c560c2f51c64b3403699",
          "description": "OG Masterbad Badewanne",
          "title": "OG Masterbad Badewanne",
          "ariaLabel": "OG Masterbad Badewanne",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "f7ef97eb-04c4-4092-8a06-d7d58901e832",
          "url": "https://mms.immowelt.de/f/7/e/f/f7ef97eb-04c4-4092-8a06-d7d58901e832.jpg?ci_seal=d340aa92bef2f9b728de52a6dd24668105481a7b",
          "description": "Erdgeschoss",
          "title": "Erdgeschoss",
          "ariaLabel": "Erdgeschoss"
        }
      ],
      "floorplans": [
        {
          "key": "cfa8fe5c-7495-455c-b164-3d842a087793",
          "url": "https://mms.immowelt.de/c/f/a/8/cfa8fe5c-7495-455c-b164-3d842a087793.jpg?ci_seal=0aba0028807f4470ea32e0a1a81d6634a06104a2",
          "description": "Keller",
          "alt": "Einfamilienhaus zum Kauf provisionsfrei 780.000 € 6 Zimmer 200 m² 600 m² Grundstück Staudernheimer Str. 35b Müggelheim Berlin 12559",
          "title": "Keller",
          "ariaLabel": "Keller",
          "classification": {
            "name": "FLOORPLAN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "5f2599fc-dc8e-44f4-94cb-4dccf61bdc7f",
          "url": "https://mms.immowelt.de/5/f/2/5/5f2599fc-dc8e-44f4-94cb-4dccf61bdc7f.jpg?ci_seal=0bf1199b99bbc24a390e1b103552204ce68eeeeb",
          "description": "Obergeschoss",
          "title": "Obergeschoss",
          "ariaLabel": "Obergeschoss",
          "classification": {
            "name": "FLOORPLAN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ],
      "availableFeatures": {
        "floorplans": true,
        "virtualTours": false
      }
    },
    "tracking": {
      "name": "classified",
      "list_name": "classified_detail_similars_bottom",
      "id": "25J65GGQB6RZ",
      "price": 780000,
      "estate_type": "av_5",
      "distribution_type": "2",
      "country": "Germany",
      "city": "Berlin",
      "region": "Berlin",
      "province": "Berlin",
      "currency": "EUR",
      "zip_code": "12559",
      "building_state": "MINT_CONDITION",
      "legacy_id": "196e56a5-a9f4-4f96-93da-69e2845dabbe",
      "product_type": "standard",
      "client_id": "678606"
    },
    "provider": {
      "intermediaryCard": {
        "title": "ohne-makler.net - Immobilien selbst vermarkten",
        "subtitle": "Gewerblicher Anbieter",
        "display": true,
        "logoUrl": "https://mms.immowelt.de/b/a/7/8/ba78ace8-18c8-4054-a182-3a0844e0884f.jpg?ci_seal=631ed3080956ae691db156718b40a9af8d063437",
        "logoHref": "https://www.immowelt.de/profil/5ba347d760714ccc97f0f7d38252a296"
      },
      "contactCard": {
        "title": "Privat vom Eigentümer",
        "subtitle": "Dein Kontakt",
        "display": true,
        "logoUrl": null
      },
      "website": "https://www.ohne-makler.net/",
      "isPrivateOwner": false,
      "profileUrl": "https://www.immowelt.de/profil/5ba347d760714ccc97f0f7d38252a296",
      "imprintUrl": "https://www.immowelt.de/profil/5ba347d760714ccc97f0f7d38252a296#impressum",
      "agencyLegalInformations": [],
      "publisherType": "AGENCY",
      "displayLinks": true,
      "badge": {
        "title": "Premium Partner",
        "imageUrl": "https://s.immowelt.org/shared/images/partner-badges/premium-partner.svg"
      },
      "address": "Humboldtstr. 25 A, 21509 Glinde",
      "agencyStrip": {
        "agencyColor": "#133C7E",
        "fontColor": "#FFFFFF"
      }
    },
    "cardProvider": {
      "title": "Privat vom Eigentümer",
      "subtitle": "Dein Kontakt",
      "logoUrl": null,
      "agencyStrip": {
        "agencyColor": "#133C7E",
        "fontColor": "#FFFFFF"
      }
    },
    "energyClass": "A_PLUS",
    "mainDescription": {
      "headline": "Modernes Einfamilienhaus mit Garten - Technik & Komfort perfekt vereint (provisionsfrei)",
      "description": "Willkommen in Ihrem neuen Zuhause - einem modernen, energieeffizienten Einfamilienhaus in einer der grünsten und familienfreundlichsten Lagen Berlins: Müggelheim. Das Haus wurde 2018 in hochwertiger ...",
      "metadata": {
        "language": "de"
      }
    },
    "type": "PROFESSIONAL",
    "url": "https://www.immowelt.de/expose/196e56a5-a9f4-4f96-93da-69e2845dabbe",
    "portal": "immowelt",
    "rawData": {
      "distributionType": "BUY",
      "propertyType": "HOUSE",
      "geoIdHierarchy": [
        {
          "id": "NBH2DE91302061",
          "typeKey": "NBH2"
        },
        {
          "id": "AD09DE483",
          "typeKey": "AD09"
        },
        {
          "id": "AD08DE8634",
          "typeKey": "AD08"
        },
        {
          "id": "AD06DE326",
          "typeKey": "AD06"
        },
        {
          "id": "AD04DE11",
          "typeKey": "AD04"
        },
        {
          "id": "AD02DE1",
          "typeKey": "AD02"
        }
      ],
      "price": 780000,
      "offererMarketingKey": "406460",
      "providercity": "Glinde",
      "providerzipcode": "21509",
      "surface": {
        "main": 200,
        "plot": 600
      },
      "nbroom": 6,
      "contactLocationEnabled": true
    },
    "tags": {
      "isExclusive": false,
      "has3DVisit": false,
      "hasBrokerageFee": false,
      "isNew": true,
      "isHdExclusive": false
    },
    "display": "classified",
    "title": "Einfamilienhaus zum Kauf",
    "image": "https://mms.immowelt.de/9/2/9/6/9296655e-ef26-48b3-8f11-a56664c8652e.jpg?ci_seal=5be98c30366636616219a78de202da1ccadf48cb",
    "price": 780000,
    "facts": [
      {
        "type": "numberOfRooms",
        "value": "6 Zimmer",
        "splitValue": "6",
        "label": "Zimmer"
      },
      {
        "type": "livingSpace",
        "value": "200 m²",
        "splitValue": "200",
        "label": "m²"
      },
      {
        "type": "plotSpace",
        "value": "600 m² Grundstück",
        "splitValue": "600",
        "label": "m² Grundstück"
      }
    ],
    "city": "Berlin"
  },
  {
    "brand": "immowelt",
    "id": "25DF1MZUHAJR",
    "status": "Published",
    "metadata": {
      "id": "25DF1MZUHAJR",
      "legacyId": "8bf6362a-258f-45c0-975c-270c9b2bb845",
      "creationDate": "2025-10-28T13:56:11.88Z",
      "updateDate": "2025-11-11T13:05:16.949Z",
      "status": {
        "status": true,
        "enrichments": {
          "contactSettings": false,
          "geo": false,
          "intermediary": false,
          "media": false,
          "onlineId": false
        }
      }
    },
    "location": {
      "address": {
        "country": "DEU",
        "city": "Berlin",
        "zipCode": "10245",
        "street": "Corinthstraße 53",
        "district": "Friedrichshain"
      },
      "isAddressPublished": true
    },
    "hardFacts": {
      "title": "Wohnung zum Kauf",
      "titleAdditions": ["provisionsfrei"],
      "keyfacts": ["3 Zimmer", "84,4 m²", "EG"],
      "facts": [
        {
          "type": "numberOfRooms",
          "value": "3 Zimmer",
          "splitValue": "3",
          "label": "Zimmer"
        },
        {
          "type": "livingSpace",
          "value": "84,4 m²",
          "splitValue": "84,4",
          "label": "m²"
        },
        {
          "type": "numberOfFloors",
          "value": "EG",
          "splitValue": "EG",
          "label": ""
        }
      ],
      "price": {
        "value": "409.200 €",
        "formatted": "409.200 €",
        "additionalInformation": "4.850 €/m²",
        "addition": {
          "value": "4.850 €/m²",
          "ariaLabel": "4850,07 Euro pro Quadratmeter"
        },
        "financialLink": {
          "href": "https://www.immowelt.de/immobilienfinanzierung-anfragen/?price=409200&originvariant=expose-hardfacts&zip=10245&city=Berlin&classifiedid=8bf6362a-258f-45c0-975c-270c9b2bb845&m=classified_detail_request_offer_find_financing_partners_step1",
          "label": "Finanzierung anfragen",
          "partnerName": "KFW"
        },
        "ariaLabel": "409200 €"
      }
    },
    "gallery": {
      "images": [
        {
          "key": "77364e0f-b024-4557-860a-25cd9733f95a",
          "url": "https://mms.immowelt.de/7/7/3/6/77364e0f-b024-4557-860a-25cd9733f95a.png?ci_seal=94b1bb2cb8d2c77a2491798915e7f6444f0631e3",
          "description": "Außenansicht",
          "alt": "Wohnung zum Kauf provisionsfrei 409.200 € 3 Zimmer 84,4 m² EG Corinthstraße 53 Friedrichshain Berlin 10245",
          "title": "Außenansicht",
          "ariaLabel": "Außenansicht",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "e36379fa-78a2-4b6a-a748-dd134e93ead7",
          "url": "https://mms.immowelt.de/e/3/6/3/e36379fa-78a2-4b6a-a748-dd134e93ead7.jpg?ci_seal=546288a0eb2e9f83ef748c7f719d9e03c856089a",
          "description": "Außenansicht ",
          "title": "Außenansicht ",
          "ariaLabel": "Außenansicht ",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "b980293d-81e3-4abf-9b3c-bf866b8e55cb",
          "url": "https://mms.immowelt.de/b/9/8/0/b980293d-81e3-4abf-9b3c-bf866b8e55cb.jpg?ci_seal=42920dd713c13903848a1c6f9e08faaf49f50b8f",
          "description": "Wohnzimmer Beispiel",
          "title": "Wohnzimmer Beispiel",
          "ariaLabel": "Wohnzimmer Beispiel",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "2a810836-df81-4267-8152-9b5f29961ec6",
          "url": "https://mms.immowelt.de/2/a/8/1/2a810836-df81-4267-8152-9b5f29961ec6.jpg?ci_seal=debcde2787b15eef58ea44fc1bb0e8887f7176b5",
          "description": "Flur Beispiel",
          "title": "Flur Beispiel",
          "ariaLabel": "Flur Beispiel",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "bfe014be-d051-4e5a-8735-6c7f83018364",
          "url": "https://mms.immowelt.de/b/f/e/0/bfe014be-d051-4e5a-8735-6c7f83018364.jpg?ci_seal=3a62a0efb5bee8ca5ad995bacdfcf02014888b4a",
          "description": "Schlafzimmer Beispiel",
          "title": "Schlafzimmer Beispiel",
          "ariaLabel": "Schlafzimmer Beispiel",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "fdf31ad7-e9f9-4402-ac22-aa5fa92a4058",
          "url": "https://mms.immowelt.de/f/d/f/3/fdf31ad7-e9f9-4402-ac22-aa5fa92a4058.jpg?ci_seal=13b6a14872b0a5ec65f5d94cd5ce512854f24268",
          "description": "Küche Beispiel",
          "title": "Küche Beispiel",
          "ariaLabel": "Küche Beispiel",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "4db66f75-f945-45d8-98ea-88056fd40732",
          "url": "https://mms.immowelt.de/4/d/b/6/4db66f75-f945-45d8-98ea-88056fd40732.jpg?ci_seal=5b8fca8dd6b38b3dca6d17288387df002237728a",
          "description": "Badezimmer Beispiel",
          "title": "Badezimmer Beispiel",
          "ariaLabel": "Badezimmer Beispiel",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "0c1dc0dc-6f9f-4de7-ab97-bbe38a16fb84",
          "url": "https://mms.immowelt.de/0/c/1/d/0c1dc0dc-6f9f-4de7-ab97-bbe38a16fb84.jpg?ci_seal=61bbfe31cc9ad9eba37a66534582dd642d5bdfe3",
          "description": "Außenansicht ",
          "title": "Außenansicht ",
          "ariaLabel": "Außenansicht ",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "00aaa47b-c0c2-49cb-8fce-d4b7af98d458",
          "url": "https://mms.immowelt.de/0/0/a/a/00aaa47b-c0c2-49cb-8fce-d4b7af98d458.jpg?ci_seal=597dc74c9fc8ef3f49665e0bb79a30d15bd4ffcd",
          "description": "Außenansicht",
          "title": "Außenansicht",
          "ariaLabel": "Außenansicht",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "a2142dad-45eb-46d6-9358-e1dbd4959256",
          "url": "https://mms.immowelt.de/a/2/1/4/a2142dad-45eb-46d6-9358-e1dbd4959256.jpg?ci_seal=6c96eb410bc9a37dd20ac66415379bcb4b728a11",
          "description": "Außenansicht ",
          "title": "Außenansicht ",
          "ariaLabel": "Außenansicht ",
          "classification": {
            "name": "COURTYARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "82f2fa7d-5099-4d05-b1b4-c38c6026a298",
          "url": "https://mms.immowelt.de/8/2/f/2/82f2fa7d-5099-4d05-b1b4-c38c6026a298.jpg?ci_seal=4ef60ab51067bed4923e1149de34f12e911f8094",
          "description": "Außenansicht ",
          "title": "Außenansicht ",
          "ariaLabel": "Außenansicht ",
          "classification": {
            "name": "COURTYARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "3132df59-08da-4064-8fcc-5d19765c9a72",
          "url": "https://mms.immowelt.de/3/1/3/2/3132df59-08da-4064-8fcc-5d19765c9a72.jpg?ci_seal=82ff78b711266ecd43c3bbb2ecf001b8406929bc",
          "description": "Außenansicht",
          "title": "Außenansicht",
          "ariaLabel": "Außenansicht",
          "classification": {
            "name": "COURTYARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "aff5fb88-fd1a-4fc4-bfa4-75df4596fcd2",
          "url": "https://mms.immowelt.de/a/f/f/5/aff5fb88-fd1a-4fc4-bfa4-75df4596fcd2.jpg?ci_seal=75087b7e2718f381b0eb9b3de07a49aaab3516ad",
          "description": "Außenansicht",
          "title": "Außenansicht",
          "ariaLabel": "Außenansicht",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "3b67c966-f062-4626-8a67-7ee1d1299872",
          "url": "https://mms.immowelt.de/3/b/6/7/3b67c966-f062-4626-8a67-7ee1d1299872.jpg?ci_seal=1ca7a3779e434d847dc6bfb36adc084cb484a20f",
          "description": "ACCENTRO",
          "title": "ACCENTRO",
          "ariaLabel": "ACCENTRO",
          "classification": {
            "name": "LOGO",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "c8b87210-90c4-40b9-864b-424e695d6ec9",
          "url": "https://mms.immowelt.de/c/8/b/8/c8b87210-90c4-40b9-864b-424e695d6ec9.jpg?ci_seal=91f4ca0ab8c5fba13fee87d5942358a144aa59b0",
          "description": "Lageplan",
          "title": "Lageplan",
          "ariaLabel": "Lageplan",
          "classification": {
            "name": "GMAP",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ],
      "floorplans": [
        {
          "key": "4b3509af-bcb7-433c-8732-0b0fedd6df09",
          "url": "https://mms.immowelt.de/4/b/3/5/4b3509af-bcb7-433c-8732-0b0fedd6df09.jpg?ci_seal=15b90f94c109262c825957cd8a5e9efa05e40c0c",
          "description": "Grundriss",
          "alt": "Wohnung zum Kauf provisionsfrei 409.200 € 3 Zimmer 84,4 m² EG Corinthstraße 53 Friedrichshain Berlin 10245",
          "title": "Grundriss",
          "ariaLabel": "Grundriss",
          "classification": {
            "name": "FLOORPLAN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ],
      "availableFeatures": {
        "floorplans": true,
        "virtualTours": false
      }
    },
    "tracking": {
      "name": "classified",
      "list_name": "classified_detail_similars_bottom",
      "id": "25DF1MZUHAJR",
      "price": 409200,
      "estate_type": "av_2",
      "distribution_type": "2",
      "country": "Germany",
      "city": "Berlin",
      "region": "Berlin",
      "province": "Berlin",
      "currency": "EUR",
      "zip_code": "10245",
      "building_state": "FULLY_RENOVATED",
      "legacy_id": "8bf6362a-258f-45c0-975c-270c9b2bb845",
      "product_type": "standard",
      "client_id": "37830"
    },
    "provider": {
      "intermediaryCard": {
        "title": "Accentro GmbH",
        "subtitle": "Gewerblicher Anbieter",
        "display": true,
        "logoUrl": "https://mms.immowelt.de/d/3/9/c/d39cb3f3-d2ee-4478-90eb-988db45ec7e6.jpg?ci_seal=b4e50671cdd39c697ed308f9806e4b82f300a7a2",
        "logoHref": "https://www.immowelt.de/profil/fa260f013904402192a7dc8bbd7d8b20"
      },
      "contactCard": {
        "title": "Herr Jürgen Twelker",
        "subtitle": "Dein Kontakt",
        "display": true,
        "logoUrl": null
      },
      "website": "http://www.accentro.de/",
      "isPrivateOwner": false,
      "profileUrl": "https://www.immowelt.de/profil/fa260f013904402192a7dc8bbd7d8b20",
      "imprintUrl": "https://www.immowelt.de/profil/fa260f013904402192a7dc8bbd7d8b20#impressum",
      "agencyLegalInformations": [],
      "publisherType": "AGENCY",
      "displayLinks": true,
      "badge": {
        "title": "immowelt Partner",
        "imageUrl": "https://s.immowelt.org/shared/images/partner-badges/partner.svg"
      },
      "address": "Kantstraße 44/45, 10625 Berlin",
      "agencyStrip": {
        "agencyColor": "#508090",
        "fontColor": "#000000"
      }
    },
    "cardProvider": {
      "title": "Herr Jürgen Twelker",
      "subtitle": "Dein Kontakt",
      "logoUrl": null,
      "agencyStrip": {
        "agencyColor": "#508090",
        "fontColor": "#000000"
      }
    },
    "energyClass": "E",
    "mainDescription": {
      "headline": "Preisnachlass: Bezugsfreie, sanierte 3-Zimmerwohnung mit Wanne & Dusche im Stralauer Kiez",
      "description": "Sichern Sie sich den Preisnachlass und sparen Sie 120.000 €* . EG . 3 Zimmer, ca. 84 m² . Saniert . Dusch- und Wannenbad . Altbau . Unvermietet . Provisionsfrei Gebäudedetails: Unweit der Spree, mitt...",
      "metadata": {
        "language": "de"
      }
    },
    "type": "PROFESSIONAL",
    "url": "https://www.immowelt.de/expose/8bf6362a-258f-45c0-975c-270c9b2bb845",
    "portal": "immowelt",
    "rawData": {
      "distributionType": "BUY",
      "propertyType": "APARTMENT",
      "geoIdHierarchy": [
        {
          "id": "NBH2DE91302026",
          "typeKey": "NBH2"
        },
        {
          "id": "AD09DE476",
          "typeKey": "AD09"
        },
        {
          "id": "AD08DE8634",
          "typeKey": "AD08"
        },
        {
          "id": "AD06DE326",
          "typeKey": "AD06"
        },
        {
          "id": "AD04DE11",
          "typeKey": "AD04"
        },
        {
          "id": "AD02DE1",
          "typeKey": "AD02"
        }
      ],
      "price": 409200,
      "offererMarketingKey": "1001-2",
      "providercity": "Berlin",
      "providerzipcode": "10625 ",
      "surface": {
        "main": 84.37,
        "plot": null
      },
      "nbroom": 3,
      "contactLocationEnabled": false
    },
    "tags": {
      "isExclusive": false,
      "has3DVisit": false,
      "hasBrokerageFee": false,
      "isNew": false,
      "isHdExclusive": false
    },
    "display": "classified",
    "title": "Wohnung zum Kauf",
    "image": "https://mms.immowelt.de/7/7/3/6/77364e0f-b024-4557-860a-25cd9733f95a.png?ci_seal=94b1bb2cb8d2c77a2491798915e7f6444f0631e3",
    "price": 409200,
    "facts": [
      {
        "type": "numberOfRooms",
        "value": "3 Zimmer",
        "splitValue": "3",
        "label": "Zimmer"
      },
      {
        "type": "livingSpace",
        "value": "84,4 m²",
        "splitValue": "84,4",
        "label": "m²"
      },
      {
        "type": "numberOfFloors",
        "value": "EG",
        "splitValue": "EG",
        "label": ""
      }
    ],
    "city": "Berlin"
  },
  {
    "brand": "immowelt",
    "id": "257V6WIBRUKW",
    "status": "Published",
    "metadata": {
      "id": "257V6WIBRUKW",
      "legacyId": "c482e22a-067a-4ded-b621-afe2f12bc7c8",
      "creationDate": "2025-11-13T16:32:18.187Z",
      "updateDate": "2025-11-13T16:32:28.765Z",
      "status": {
        "status": true,
        "enrichments": {
          "contactSettings": false,
          "geo": false,
          "intermediary": false,
          "media": false,
          "onlineId": false
        }
      }
    },
    "location": {
      "address": {
        "country": "DEU",
        "city": "Berlin",
        "zipCode": "10719",
        "street": "Meinekestraße 10",
        "district": "Charlottenburg"
      },
      "isAddressPublished": true
    },
    "hardFacts": {
      "title": "Wohnung zum Kauf",
      "keyfacts": ["3 Zimmer", "102,8 m²", "2. Geschoss"],
      "facts": [
        {
          "type": "numberOfRooms",
          "value": "3 Zimmer",
          "splitValue": "3",
          "label": "Zimmer"
        },
        {
          "type": "livingSpace",
          "value": "102,8 m²",
          "splitValue": "102,8",
          "label": "m²"
        },
        {
          "type": "numberOfFloors",
          "value": "2. Geschoss",
          "splitValue": "2.",
          "label": "Geschoss"
        }
      ],
      "price": {
        "value": "995.000 €",
        "formatted": "995.000 €",
        "additionalInformation": "9.680 €/m²",
        "addition": {
          "value": "9.680 €/m²",
          "ariaLabel": "9680 Euro pro Quadratmeter"
        },
        "financialLink": {
          "href": "https://www.immowelt.de/immobilienfinanzierung-anfragen/?price=995000&originvariant=expose-hardfacts&zip=10719&city=Berlin&classifiedid=c482e22a-067a-4ded-b621-afe2f12bc7c8&m=classified_detail_request_offer_find_financing_partners_step1",
          "label": "Finanzierung anfragen",
          "partnerName": "KFW"
        },
        "ariaLabel": "995000 €"
      }
    },
    "gallery": {
      "images": [
        {
          "key": "f9c2500d-4edb-4803-a309-c20a57f2d140",
          "url": "https://mms.immowelt.de/f/9/c/2/f9c2500d-4edb-4803-a309-c20a57f2d140.jpg?ci_seal=3000617e488769e973da190fe603facb381face4",
          "description": "Zimmer",
          "alt": "Wohnung zum Kauf 995.000 € 3 Zimmer 102,8 m² 2. Geschoss Meinekestraße 10 Charlottenburg Berlin 10719",
          "title": "Zimmer",
          "ariaLabel": "Zimmer",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "42f214a2-7cbb-494c-b9c0-31734e9a9d80",
          "url": "https://mms.immowelt.de/4/2/f/2/42f214a2-7cbb-494c-b9c0-31734e9a9d80.jpg?ci_seal=479c3641c958c672ac548e2e0aed8e4f2204beab",
          "description": "Objektansicht",
          "title": "Objektansicht",
          "ariaLabel": "Objektansicht",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "a45944e7-6bb7-4118-a5a6-049fab5f4908",
          "url": "https://mms.immowelt.de/a/4/5/9/a45944e7-6bb7-4118-a5a6-049fab5f4908.jpg?ci_seal=e6c4ff72f098b6cfb8f50b2c019abb59af127197",
          "description": "Balkon",
          "title": "Balkon",
          "ariaLabel": "Balkon",
          "classification": {
            "name": "BALCONY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "45bb98c2-4d7f-4e26-a014-07abf555cd91",
          "url": "https://mms.immowelt.de/4/5/b/b/45bb98c2-4d7f-4e26-a014-07abf555cd91.jpg?ci_seal=dedba09894fba1a0dc0df9c08ce30c0300e70d2d",
          "description": "Flur",
          "title": "Flur",
          "ariaLabel": "Flur",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "3ebe1423-e072-4ba1-8eab-a09fdfdbc6c0",
          "url": "https://mms.immowelt.de/3/e/b/e/3ebe1423-e072-4ba1-8eab-a09fdfdbc6c0.jpg?ci_seal=a8af0d58b8345971388e3073e202367d3555a7b7",
          "description": "Küche",
          "title": "Küche",
          "ariaLabel": "Küche",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "c4dca905-917a-4b87-9fee-8770f101d85b",
          "url": "https://mms.immowelt.de/c/4/d/c/c4dca905-917a-4b87-9fee-8770f101d85b.jpg?ci_seal=dc6fd5c852d1010409e26e10184fc745ca56bf7e",
          "description": "Küche",
          "title": "Küche",
          "ariaLabel": "Küche",
          "classification": {
            "name": "KITCHEN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "245447d7-498c-4ae5-bb48-141f7942300d",
          "url": "https://mms.immowelt.de/2/4/5/4/245447d7-498c-4ae5-bb48-141f7942300d.jpg?ci_seal=7624c5ec88e423276084b2f3b4474de3931ea895",
          "description": "Zimmer",
          "title": "Zimmer",
          "ariaLabel": "Zimmer",
          "classification": {
            "name": "BEDROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "395d8174-36af-4466-bceb-8b88b817d293",
          "url": "https://mms.immowelt.de/3/9/5/d/395d8174-36af-4466-bceb-8b88b817d293.jpg?ci_seal=3a1cb8a5444bf8abffa9f487ebf139bfb2530c0b",
          "description": "Flur",
          "title": "Flur",
          "ariaLabel": "Flur",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "b509e26e-bff4-40d8-b45e-5f8f7ae90c67",
          "url": "https://mms.immowelt.de/b/5/0/9/b509e26e-bff4-40d8-b45e-5f8f7ae90c67.jpg?ci_seal=5ed8d5a087633dfddd75dfcbe5bb5d6e4672f520",
          "description": "Badezimmer",
          "title": "Badezimmer",
          "ariaLabel": "Badezimmer",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "2df36ad2-0036-47fe-88d4-33004f4aa044",
          "url": "https://mms.immowelt.de/2/d/f/3/2df36ad2-0036-47fe-88d4-33004f4aa044.jpg?ci_seal=1a9530508dcd1527442ac86a187d01d064c72b24",
          "description": "Hauseingang",
          "title": "Hauseingang",
          "ariaLabel": "Hauseingang",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "086cb1b2-48a9-4d21-8596-76b657d72e44",
          "url": "https://mms.immowelt.de/0/8/6/c/086cb1b2-48a9-4d21-8596-76b657d72e44.jpg?ci_seal=fcfbec93cc4de4486d5379f9f0908159fd85cd97",
          "description": "Objektansicht",
          "title": "Objektansicht",
          "ariaLabel": "Objektansicht",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "9f03d50c-fec1-46a5-88c9-75d725d1b9db",
          "url": "https://mms.immowelt.de/9/f/0/3/9f03d50c-fec1-46a5-88c9-75d725d1b9db.jpg?ci_seal=055978c4bcc2758329b8351d5a9d12d3decd70c8",
          "description": "Berliner Festspiele",
          "title": "Berliner Festspiele",
          "ariaLabel": "Berliner Festspiele",
          "classification": {
            "name": "LOGO",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "7222ac3a-3f2d-4558-ae55-17c92c16fcfe",
          "url": "https://mms.immowelt.de/7/2/2/2/7222ac3a-3f2d-4558-ae55-17c92c16fcfe.jpg?ci_seal=93b3b39bf1763a731ba94a65b5aa801b35a38d35",
          "description": "U-Uhlandstraße",
          "title": "U-Uhlandstraße",
          "ariaLabel": "U-Uhlandstraße",
          "classification": {
            "name": "LOGO",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "7ba16a58-b668-47e8-bdcf-0bad88951544",
          "url": "https://mms.immowelt.de/7/b/a/1/7ba16a58-b668-47e8-bdcf-0bad88951544.jpg?ci_seal=88f81a1440dbce0341562c1895146536fd7f3837",
          "description": "Café im Literaturhaus",
          "title": "Café im Literaturhaus",
          "ariaLabel": "Café im Literaturhaus",
          "classification": {
            "name": "YARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "c24242b0-3d83-4443-9ab2-80f78c212bbf",
          "url": "https://mms.immowelt.de/c/2/4/2/c24242b0-3d83-4443-9ab2-80f78c212bbf.jpg?ci_seal=0e129dfe0d81d6baa355a9a423b026951e69e123",
          "description": "Kaufhaus des Westens",
          "title": "Kaufhaus des Westens",
          "ariaLabel": "Kaufhaus des Westens",
          "classification": {
            "name": "LOGO",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ],
      "floorplans": [
        {
          "key": "359ef82f-df47-4176-abd8-d578aab1a3e2",
          "url": "https://mms.immowelt.de/3/5/9/e/359ef82f-df47-4176-abd8-d578aab1a3e2.jpg?ci_seal=0eccbe4ad28abac70a442919ed1b928d6ae786f3",
          "description": "Grundriss",
          "alt": "Wohnung zum Kauf 995.000 € 3 Zimmer 102,8 m² 2. Geschoss Meinekestraße 10 Charlottenburg Berlin 10719",
          "title": "Grundriss",
          "ariaLabel": "Grundriss",
          "classification": {
            "name": "FLOORPLAN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ],
      "availableFeatures": {
        "floorplans": true,
        "virtualTours": false
      }
    },
    "tracking": {
      "name": "classified",
      "list_name": "classified_detail_similars_bottom",
      "id": "257V6WIBRUKW",
      "price": 995000,
      "estate_type": "av_2",
      "distribution_type": "2",
      "country": "Germany",
      "city": "Berlin",
      "region": "Berlin",
      "province": "Berlin",
      "currency": "EUR",
      "zip_code": "10719",
      "building_state": "WELL_KEPT",
      "legacy_id": "c482e22a-067a-4ded-b621-afe2f12bc7c8",
      "product_type": "standard",
      "client_id": "1467247"
    },
    "provider": {
      "intermediaryCard": {
        "title": "David Borck Immobiliengesellschaft mbH",
        "subtitle": "Gewerblicher Anbieter",
        "display": true,
        "logoUrl": "https://mms.immowelt.de/d/6/e/a/d6ea2171-56b7-4d05-b352-53744eaa4566.jpg?ci_seal=7db2d5c10ce394057a57b8d7e0f20b4e8bb6a811",
        "logoHref": "https://www.immowelt.de/profil/f123db0323b34d77bfb91d0e7833a95f"
      },
      "contactCard": {
        "title": "Frau Nele Steinberg",
        "subtitle": "Dein Kontakt",
        "display": true,
        "logoUrl": "//filestore.immowelt.de/ProfilBilder/150_f096285c4ad5487b8d99b3dea42fa0a3.jpg"
      },
      "website": "http://www.david-borck.de/",
      "isPrivateOwner": false,
      "profileUrl": "https://www.immowelt.de/profil/f123db0323b34d77bfb91d0e7833a95f",
      "imprintUrl": "https://www.immowelt.de/profil/f123db0323b34d77bfb91d0e7833a95f#impressum",
      "feeUrl": "https://mms.immowelt.de/6/1/9/5/6195798a-e3f1-4568-9fff-f965071e4f98.pdf?ci_seal=2593148c9d80e835d04506b5ee1a72fdb0ab292a",
      "agencyLegalInformations": [],
      "publisherType": "AGENCY",
      "displayLinks": true,
      "address": "Schlüterstr. 45, 10707 Berlin",
      "agencyStrip": {
        "agencyColor": "#3070b0",
        "fontColor": "#FFFFFF"
      }
    },
    "cardProvider": {
      "title": "Frau Nele Steinberg",
      "subtitle": "Dein Kontakt",
      "logoUrl": "//filestore.immowelt.de/ProfilBilder/150_f096285c4ad5487b8d99b3dea42fa0a3.jpg",
      "agencyStrip": {
        "agencyColor": "#3070b0",
        "fontColor": "#FFFFFF"
      }
    },
    "mainDescription": {
      "headline": "Elegante Altbauwohnung mit Südwest-Balkon in Charlottenburger Toplage",
      "description": "Im ruhigen Gartenhaus eines gepflegten Altbaus aus der Gründerzeit befindet sich diese rund 102 m² große Wohnung im zweiten Obergeschoss. Die Eigentumswohnung überzeugt durch ihren klaren Grundriss, ...",
      "metadata": {
        "language": "de"
      }
    },
    "type": "PROFESSIONAL",
    "url": "https://www.immowelt.de/expose/c482e22a-067a-4ded-b621-afe2f12bc7c8",
    "portal": "immowelt",
    "rawData": {
      "distributionType": "BUY",
      "propertyType": "APARTMENT",
      "geoIdHierarchy": [
        {
          "id": "NBH2DE91302007",
          "typeKey": "NBH2"
        },
        {
          "id": "AD09DE478",
          "typeKey": "AD09"
        },
        {
          "id": "AD08DE8634",
          "typeKey": "AD08"
        },
        {
          "id": "AD06DE326",
          "typeKey": "AD06"
        },
        {
          "id": "AD04DE11",
          "typeKey": "AD04"
        },
        {
          "id": "AD02DE1",
          "typeKey": "AD02"
        }
      ],
      "price": 995000,
      "offererMarketingKey": "6185",
      "providercity": "Berlin",
      "providerzipcode": "10707",
      "surface": {
        "main": 102.79,
        "plot": null
      },
      "nbroom": 3,
      "contactLocationEnabled": false
    },
    "tags": {
      "isExclusive": false,
      "has3DVisit": false,
      "hasBrokerageFee": false,
      "isNew": true,
      "isHdExclusive": false
    },
    "display": "classified",
    "title": "Wohnung zum Kauf",
    "image": "https://mms.immowelt.de/f/9/c/2/f9c2500d-4edb-4803-a309-c20a57f2d140.jpg?ci_seal=3000617e488769e973da190fe603facb381face4",
    "price": 995000,
    "facts": [
      {
        "type": "numberOfRooms",
        "value": "3 Zimmer",
        "splitValue": "3",
        "label": "Zimmer"
      },
      {
        "type": "livingSpace",
        "value": "102,8 m²",
        "splitValue": "102,8",
        "label": "m²"
      },
      {
        "type": "numberOfFloors",
        "value": "2. Geschoss",
        "splitValue": "2.",
        "label": "Geschoss"
      }
    ],
    "city": "Berlin"
  },
  {
    "brand": "immowelt",
    "id": "25XYU7E8MIR8",
    "status": "Published",
    "metadata": {
      "id": "25XYU7E8MIR8",
      "legacyId": "5f06aac5-57cb-424e-9a55-f3c03cc76db4",
      "creationDate": "2025-11-05T00:14:43.457Z",
      "updateDate": "2025-11-07T00:58:29.186Z",
      "status": {
        "status": true,
        "enrichments": {
          "contactSettings": false,
          "geo": false,
          "intermediary": false,
          "media": false,
          "onlineId": false
        }
      }
    },
    "location": {
      "address": {
        "country": "DE",
        "city": "Berlin",
        "zipCode": "12249",
        "street": "Derfflingerstraße 45",
        "district": "Lankwitz"
      },
      "isAddressPublished": true
    },
    "hardFacts": {
      "title": "Wohnung zum Kauf",
      "keyfacts": ["3 Zimmer", "80 m²", "Geschoss 1/4", "frei ab 01.02.2026"],
      "facts": [
        {
          "type": "numberOfRooms",
          "value": "3 Zimmer",
          "splitValue": "3",
          "label": "Zimmer"
        },
        {
          "type": "livingSpace",
          "value": "80 m²",
          "splitValue": "80",
          "label": "m²"
        },
        {
          "type": "numberOfFloors",
          "value": "Geschoss 1/4",
          "splitValue": "Geschoss",
          "label": "1/4"
        },
        {
          "type": "availability",
          "value": "frei ab 01.02.2026",
          "splitValue": "frei",
          "label": "ab 01.02.2026"
        }
      ],
      "price": {
        "value": "450.000 €",
        "formatted": "450.000 €",
        "additionalInformation": "5.625 €/m²",
        "addition": {
          "value": "5.625 €/m²",
          "ariaLabel": "5625 Euro pro Quadratmeter"
        },
        "financialLink": {
          "href": "https://www.immowelt.de/immobilienfinanzierung-anfragen/?price=450000&originvariant=expose-hardfacts&zip=12249&city=Berlin&classifiedid=5f06aac5-57cb-424e-9a55-f3c03cc76db4&m=classified_detail_request_offer_find_financing_partners_step1",
          "label": "Finanzierung anfragen",
          "partnerName": "KFW"
        },
        "ariaLabel": "450000 €"
      }
    },
    "gallery": {
      "images": [
        {
          "key": "85d5348f-261f-4f63-8fdb-ca58887fa7af",
          "url": "https://mms.immowelt.de/8/5/d/5/85d5348f-261f-4f63-8fdb-ca58887fa7af.jpg?ci_seal=54cfc7fa8c8d86d0101aa9ea5acad9bfd2d7f3bf",
          "description": "Schlafzimmer I",
          "alt": "Wohnung zum Kauf 450.000 € 3 Zimmer 80 m² Geschoss 1/4 frei ab 01.02.2026 Derfflingerstraße 45 Lankwitz Berlin 12249",
          "title": "Schlafzimmer I",
          "ariaLabel": "Schlafzimmer I",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "e0504714-8246-422b-aec3-a05e3a8161e3",
          "url": "https://mms.immowelt.de/e/0/5/0/e0504714-8246-422b-aec3-a05e3a8161e3.jpg?ci_seal=e5ec30fe53707270268896330ac6b4f5d00a2dc8",
          "description": "Schlafzimmer I",
          "title": "Schlafzimmer I",
          "ariaLabel": "Schlafzimmer I",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "95eb3424-e71c-420b-a396-55b22f32969d",
          "url": "https://mms.immowelt.de/9/5/e/b/95eb3424-e71c-420b-a396-55b22f32969d.jpg?ci_seal=db4364288cdb4a151f6d32c8dd9109b476268790",
          "description": "Schlafzimmer II",
          "title": "Schlafzimmer II",
          "ariaLabel": "Schlafzimmer II",
          "classification": {
            "name": "EMPTY_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "5a8471de-5a0a-4d06-8747-db8e988fa931",
          "url": "https://mms.immowelt.de/5/a/8/4/5a8471de-5a0a-4d06-8747-db8e988fa931.jpg?ci_seal=2fccd22f158db2c5e7c6772dc56cbab1b99c9b20",
          "description": "Wohnzimmer",
          "title": "Wohnzimmer",
          "ariaLabel": "Wohnzimmer",
          "classification": {
            "name": "LIVING_ROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "1bb7e710-484d-49bc-8de3-845f91541ceb",
          "url": "https://mms.immowelt.de/1/b/b/7/1bb7e710-484d-49bc-8de3-845f91541ceb.jpg?ci_seal=cdddbc5c8a1aca244da90665362201157a0ed0c3",
          "description": "Küche",
          "title": "Küche",
          "ariaLabel": "Küche",
          "classification": {
            "name": "KITCHEN",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "996f8c85-37a8-42f3-b589-f52e645e1eaa",
          "url": "https://mms.immowelt.de/9/9/6/f/996f8c85-37a8-42f3-b589-f52e645e1eaa.jpg?ci_seal=7fee65c360961af18e7cd75436c99c2a9c449af7",
          "description": "Tageslichtbad mit Badewanne",
          "title": "Tageslichtbad mit Badewanne",
          "ariaLabel": "Tageslichtbad mit Badewanne",
          "classification": {
            "name": "BATHROOM",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "bff18fd9-366a-4896-aefa-4fc2d3defd67",
          "url": "https://mms.immowelt.de/b/f/f/1/bff18fd9-366a-4896-aefa-4fc2d3defd67.jpg?ci_seal=98ea504f46f7eb0d8dc57d08033040b1447fe802",
          "description": "Eingangsbereich",
          "title": "Eingangsbereich",
          "ariaLabel": "Eingangsbereich",
          "classification": {
            "name": "HALLWAY",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "659ff2ce-2025-42c9-a113-a778ee8e658d",
          "url": "https://mms.immowelt.de/6/5/9/f/659ff2ce-2025-42c9-a113-a778ee8e658d.jpg?ci_seal=accba2c92765408baf6a34564f8e2266f438e86c",
          "description": "Innenhof",
          "title": "Innenhof",
          "ariaLabel": "Innenhof",
          "classification": {
            "name": "YARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "477c3022-46b4-43b7-9b01-cf20d6b17f6c",
          "url": "https://mms.immowelt.de/4/7/7/c/477c3022-46b4-43b7-9b01-cf20d6b17f6c.jpg?ci_seal=8a17ee170722c7a593533aeb6d83f1871fdb0491",
          "description": "Fassade",
          "title": "Fassade",
          "ariaLabel": "Fassade",
          "classification": {
            "name": "BUILDING_FACADE",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        },
        {
          "key": "9a3340a7-8972-4011-bf66-fb120efbe4f8",
          "url": "https://mms.immowelt.de/9/a/3/3/9a3340a7-8972-4011-bf66-fb120efbe4f8.jpg?ci_seal=924e22aa34e25e3f59cbe61fbda07d22a36e4446",
          "description": "Innenhof",
          "title": "Innenhof",
          "ariaLabel": "Innenhof",
          "classification": {
            "name": "COURTYARD",
            "version": "scene-classification-sagemaker-endpoint-live-1-3-10"
          }
        }
      ]
    },
    "tracking": {
      "name": "classified",
      "list_name": "classified_detail_similars_bottom",
      "id": "25XYU7E8MIR8",
      "price": 450000,
      "estate_type": "av_2",
      "distribution_type": "2",
      "country": "Germany",
      "city": "Berlin",
      "region": "Berlin",
      "province": "Berlin",
      "currency": "EUR",
      "zip_code": "12249",
      "building_state": "REFURBISHED",
      "legacy_id": "5f06aac5-57cb-424e-9a55-f3c03cc76db4",
      "product_type": "standard",
      "client_id": "11952173"
    },
    "provider": {
      "intermediaryCard": {
        "title": "Estabo Real Estate (UG)",
        "subtitle": "Gewerblicher Anbieter",
        "display": true,
        "logoUrl": "https://mms.immowelt.de/e/4/3/4/e4344c59-da7f-4567-93b4-bc9947e86214.jpg?ci_seal=49c148c507f121c121e5c062804eb72afe452927",
        "logoHref": "https://www.immowelt.de/profil/85ef5542ad9149699207a1113bb514fb"
      },
      "contactCard": {
        "title": null,
        "subtitle": "Dein Kontakt",
        "display": false,
        "logoUrl": null
      },
      "isPrivateOwner": false,
      "profileUrl": "https://www.immowelt.de/profil/85ef5542ad9149699207a1113bb514fb",
      "imprintUrl": "https://www.immowelt.de/profil/85ef5542ad9149699207a1113bb514fb#impressum",
      "agencyLegalInformations": [],
      "publisherType": "AGENCY",
      "rating": {
        "rating": 5,
        "reviews": 1,
        "link": "https://www.immowelt.de/profil/85ef5542ad9149699207a1113bb514fb#rating"
      },
      "displayLinks": true,
      "badge": {
        "title": "immowelt Partner",
        "imageUrl": "https://s.immowelt.org/shared/images/partner-badges/partner.svg"
      },
      "address": "Kurfürstendamm 11 c/o WeWork, 10719 Berlin",
      "agencyStrip": {
        "agencyColor": "#00032e",
        "fontColor": "#FFFFFF"
      }
    },
    "cardProvider": {
      "title": null,
      "subtitle": "Dein Kontakt",
      "logoUrl": null,
      "agencyStrip": {
        "agencyColor": "#00032e",
        "fontColor": "#FFFFFF"
      }
    },
    "energyClass": "E",
    "mainDescription": {
      "headline": "Helle 3-Zimmer-Wohnung in Berlin-Lankwitz mit Balkon & modernem Ambiente – frisch renoviert, ruhig gelegen & sofort bezugsfrei!",
      "description": "Diese lichtdurchflutete 3-Zimmer-Wohnung in der Derfflingerstraße 45 verbindet Modernität, Klarheit und Wohnkomfort auf harmonische Weise. Im ersten Obergeschoss eines gepflegten Mehrfamilienhauses g...",
      "metadata": {
        "language": "de"
      }
    },
    "type": "PROFESSIONAL",
    "url": "https://www.immowelt.de/expose/5f06aac5-57cb-424e-9a55-f3c03cc76db4",
    "portal": "immowelt",
    "rawData": {
      "distributionType": "BUY",
      "propertyType": "APARTMENT",
      "geoIdHierarchy": [
        {
          "id": "NBH2DE91302091",
          "typeKey": "NBH2"
        },
        {
          "id": "AD09DE480",
          "typeKey": "AD09"
        },
        {
          "id": "AD08DE8634",
          "typeKey": "AD08"
        },
        {
          "id": "AD06DE326",
          "typeKey": "AD06"
        },
        {
          "id": "AD04DE11",
          "typeKey": "AD04"
        },
        {
          "id": "AD02DE1",
          "typeKey": "AD02"
        }
      ],
      "price": 450000,
      "providercity": "Berlin",
      "providerzipcode": "10719",
      "surface": {
        "main": 80,
        "plot": null
      },
      "nbroom": 3,
      "contactLocationEnabled": false
    },
    "tags": {
      "isExclusive": false,
      "has3DVisit": false,
      "hasBrokerageFee": false,
      "isNew": false,
      "isHdExclusive": false
    },
    "display": "classified",
    "title": "Wohnung zum Kauf",
    "image": "https://mms.immowelt.de/8/5/d/5/85d5348f-261f-4f63-8fdb-ca58887fa7af.jpg?ci_seal=54cfc7fa8c8d86d0101aa9ea5acad9bfd2d7f3bf",
    "price": 450000,
    "facts": [
      {
        "type": "numberOfRooms",
        "value": "3 Zimmer",
        "splitValue": "3",
        "label": "Zimmer"
      },
      {
```