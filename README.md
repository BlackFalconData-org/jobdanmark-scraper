# Jobdanmark Scraper

Extract structured data from [jobdanmark.dk](https://jobdanmark.dk) — structured job listings from jobdanmark.dk — Denmark's job portal with 14,500+ listings, contact info, and apply URLs.

**[Jobdanmark Scraper - Danish Job Board on Apify →](https://apify.com/blackfalcondata/jobdanmark-scraper)**

---

## Key features




**Search with filters** — Search by keyword and location. Filter by job type, category, and more.

**Detail enrichment** — Fetch full job descriptions, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

---

## Use cases




**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from jobdanmark.dk on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from jobdanmark.dk.

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

---

## Related products by Black Falcon Data




- [StepStone Scraper](https://github.com/BlackFalconData-org/stepstone-scraper) — Job listings from 18 European portals
- [Indeed Job Scraper](https://github.com/BlackFalconData-org/indeed-job-scraper) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://github.com/BlackFalconData-org/glassdoor-job-scraper) — Glassdoor listings with company ratings

---

*Last updated: 2026 03*
