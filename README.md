# Jobdanmark Scraper

Extract structured data from [jobdanmark.dk](https://jobdanmark.dk) — structured job listings from jobdanmark.dk — Denmark's job portal with 14,500+ listings, contact info, and apply URLs.

**[Jobdanmark Scraper - Danish Job Board on Apify →](https://apify.com/blackfalcondata/jobdanmark-scraper?fpr=1h3gvi)**

---

## Key features






**Search with filters** — Search by keyword and location. Filter by job type, category, and more.

**Detail enrichment** — Fetch full job descriptions, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

**Compact output** — Emit core fields only (AI-agent / MCP-friendly). Keeps response size small for LLM workflows.

**Description truncation** — Cap description length per listing to control output size and cost.

**Result cap** — Stop after N listings (up to 5.000). Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases






**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from jobdanmark.dk on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from jobdanmark.dk.

**Change monitoring**
Run daily or hourly in incremental mode to capture only new, updated, or expired listings. Perfect for price-tracking, churn analysis, and alerting pipelines.

**Lead generation**
Extract employer contact details alongside listings to build outreach lists for recruiters, staffing agencies, or B2B sales teams.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
{
  "query": "software",
  "maxResults": 50,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `query` | string | — | Job search keywords. Matched against jobdanmark.dk's jobtitle catalog (1179 titles). Leave empty with a jobType to get all listings of that type. |
| `jobType` | enum | `""` | Filter by employment type. |
| `maxResults` | integer | `50` | Maximum total results (0 = unlimited). |
| `includeDetails` | boolean | `true` | Fetch full job description from detail pages. Slower but provides complete descriptions. |
| `descriptionMaxLength` | integer | `0` | Truncate description to N characters. 0 = no truncation. |
| `compact` | boolean | `false` | Core fields only (for AI-agent/MCP workflows). Omits description, logo URL, and metadata. |
| `incrementalMode` | boolean | `false` | Only output new/changed listings compared to previous run. |
| `stateKey` | string | — | Stable identifier for tracked universe. Different stateKeys maintain separate state. |

---

## FAQ

<!-- WRITE: 4-6 Q&A pairs relevant to this product -->

**Is it legal to scrape jobdanmark.dk?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check the target site's terms of service for your specific use case.

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->


## Output fields

Every listing returns the same 22-field schema. Missing values are `null` — never omitted.

- `jobId`
- `title`
- `companyName`
- `companyAddress`
- `companyLogoUrl`
- `jobTypes`
- `publishedDate`
- `applicationDeadline`
- `description`
- `contactName`
- `contactPhone`
- `applyUrl`
- `url`
- `portalUrl`
- `isPromoted`
- `scrapedAt`
- `source`
- `contactEmail`
- `employmentType`
- `addressLocality`
- `addressRegion`
- `postalCode`


## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "jobId": "31c7355d558ba4d2f1502f413c82c52607ce493cc193cf1b4b7aa12143fca68a",
  "title": "Teamleder sÃ¸ges til LysÃ¥ben Natur hos Naturstyrelsens enhed Arealer i RandbÃ¸l",
  "companyName": "Naturstyrelsen",
  "companyAddress": "FÃ¸rstballevej 2 7183 RandbÃ¸l",
  "companyLogoUrl": "https://jobdanmark.dk/media/y1lpnbmn/logo.png",
  "jobTypes": [
    "fuldtid"
  ],
  "publishedDate": "2026-03-26",
  "applicationDeadline": "2026-04-09",
  "description": "Vil du vÃ¦re med til at lede Naturstyrelsens overordnede forvaltning af nogle af Danmarks vigtigste naturomrÃ¥der? Har du naturforstÃ¥else, ledelseserfaring og lyst til at pÃ¥tage …",
  "contactName": "Kristian Ahlefeldt Gernow",
  "contactPhone": "2143 1452",
  "applyUrl": "https://candidate.hr-manager.net/ApplicationForm/SinglePageApplicationForm.aspx?cid=3010&departmentId=19734&ProjectId=159034&MediaId=4844"
}
```

*Truncated — full records contain 22 fields. See Output fields for the complete schema.*


**[Try Jobdanmark Scraper - Danish Job Board now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/jobdanmark-scraper?fpr=1h3gvi)**


## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.01 |
| Result | $0.002 |

See the [actor on Apify](https://apify.com/blackfalcondata/jobdanmark-scraper?fpr=1h3gvi) for current pricing.

---

## Related products by Black Falcon Data






- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board
- [Naukri Scraper](https://apify.com/blackfalcondata/naukri-scraper?fpr=1h3gvi) — India's largest job portal

---


## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) — $5 credit included
2. Open the actor and paste your input
3. Click Start — results download as JSON, CSV, or Excel

Need more volume? [See pricing](https://apify.com/pricing?fpr=1h3gvi).

---

---

*Last updated: 2026 03*
