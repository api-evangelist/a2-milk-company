---
name: a2-milk-company-site-index
description: Load The a2 Milk Company Careers site's machine-readable index (llms.txt, llms-full.txt, sitemap) and check liveness.
api: a2-milk-company:careers-public-api
operations:
- getHealth
- getLlmsIndex
- getLlmsFull
- getSitemap
---
# Load the site index

1. Optionally check `getHealth` (GET /health).
2. Fetch `getLlmsIndex` (GET /llms.txt) for the curated index and priority pages.
3. Fetch `getLlmsFull` (GET /llms-full.txt) to get the whole corpus in one request.
4. Use `getSitemap` (GET /sitemap.xml) to enumerate every indexable URL.

Rules: all GET, no authentication.
