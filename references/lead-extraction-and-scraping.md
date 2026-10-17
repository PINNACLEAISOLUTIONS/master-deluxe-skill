# Lead Extraction & Web Scraping Reference

## Apify Actor Selection Matrix

| Target & Platform | Recommended Actor ID | Best Use Case |
|---|---|---|
| **Google Maps / Local Businesses** | `compass/crawler-google-places` | Storefronts, contractors, clinics, restaurants |
| **Direct Email & Phone Extractor** | `vdrmota/contact-info-scraper` | Crawling websites for verified emails & phones |
| **Google Maps Contact Enrichment** | `poidata/google-maps-email-extractor` | Turn local map listings directly into email lists |
| **Facebook Business Pages** | `apify/facebook-pages-scraper` | B2B contact info, addresses, official websites |
| **Facebook Groups** | `apify/facebook-groups-scraper` | Community buyer intent, discussion monitoring |
| **Instagram Business Profiles** | `apify/instagram-profile-scraper` | Creator outreach, bio links, contact emails |
| **TikTok Creator Outreach** | `clockworks/tiktok-profile-scraper` | Influencer metrics, bio emails, follower count |
| **Google Search Scraping** | `apify/google-search-scraper` | Broad prospect discovery and SERP indexing |

---

## Puppeteer Dynamic Browsing Protocol
1. **Headless Execution**: Use realistic viewport dimensions (`1920x1080`) and legitimate user agent headers.
2. **Dynamic Waiting**: Never use hardcoded arbitrary sleeps. Always wait for specific selectors or network idle events (`waitForSelector`, `waitForNetworkIdle`).
3. **Form Handling**: Click input fields before typing, type with realistic delays, and verify form submission success state.
4. **Data Normalization**: Extract clean, structured JSON objects with uniform keys (`company_name`, `email`, `phone`, `website`, `address`, `scraped_at`).
