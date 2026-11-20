# Search Queries for Job Scraper

<!-- SETUP: Customize these queries based on your skills, target roles, and location -->

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. None ship with AI Job Search: copy the ones for your market from [community-portals](https://github.com/ai-job-search-dev/community-portals) (e.g. `linkedin-search`, `freehire-search` under `portals/global/`), or build one with `/add-portal`. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

**Language scope:** write every query category in every language listed in your CLAUDE.md Languages table (typically 1-2, sometimes more). A posting requiring a language you have *not* declared, as a job condition, is excluded before scoring; a posting requiring a *higher level* than you declared in a language you *do* work in is flagged for your own judgment, not excluded — see `04-job-evaluation.md`'s Language Gate, the single source of truth for this rule. Translate each category's keywords rather than machine-translating word-for-word (e.g. "Frontend Developer" -> "Desarrollador Frontend", not a literal word-for-word translation) if you work in more than one language.

## Search Sites

Primary:
- **linkedin.com/jobs** - main board (Easy Apply first); filter: Los Angeles, CA (50 mi) and United States (Remote); also covered by the community `linkedin-search` CLI once installed
- **indeed.com** - broad US board
- **builtinla.com** - LA tech and data roles
- **glassdoor.com** - additional US listings (optional)

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for target companies (greenhouse.io, lever.co, myworkdayjobs.com)

## Query Categories

Queries are grouped by priority. Candidate works in English only. Combine each query with "Los Angeles" or "Remote".

Each priority has two kinds of block. **Plain terms** blocks are what the portal CLIs consume: one term per line, one CLI call per term, no `OR`, no `site:` prefix, and no location. **WebSearch-only** blocks are Google syntax for the fallback path and are never passed to a CLI.

### Priority 1: Data & BI Analysis (core function)

Turning sales, inventory and operations data into dashboards, reports and decisions.

#### Plain terms (portal CLIs)

```
Data Analyst
Business Intelligence Analyst
BI Analyst
Power BI Analyst
Reporting Analyst
Business Analyst
```

#### WebSearch-only (`site:` fallback)

```
site:linkedin.com/jobs "Data Analyst" "Los Angeles"
site:linkedin.com/jobs "Business Intelligence Analyst" Remote "United States"
site:boards.greenhouse.io "Data Analyst" (Remote OR "Los Angeles")
site:jobs.lever.co "Business Analyst" (Remote OR "Los Angeles")
site:builtinla.com "Data Analyst"
```

### Priority 2: E-commerce, Pricing & Marketplace Analytics (domain strength)

#### Plain terms (portal CLIs)

```
E-commerce Analyst
Pricing Analyst
Marketplace Analyst
Inventory Analyst
Revenue Analyst
```

#### WebSearch-only (`site:` fallback)

```
site:linkedin.com/jobs "E-commerce Analyst" "Los Angeles"
site:linkedin.com/jobs "Pricing Analyst" (Remote OR "Los Angeles")
site:boards.greenhouse.io "Marketplace Analyst" Remote
```

### Priority 3: Adjacent - Analytics Engineering, Finance & Operations Analysis

#### Plain terms (portal CLIs)

```
Analytics Engineer
Associate BI Engineer
Financial Data Analyst
Operations Analyst
Product Analyst
Strategy Analyst
```

#### WebSearch-only (`site:` fallback)

```
site:linkedin.com/jobs "Analytics Engineer" (dbt OR Snowflake) Remote
site:linkedin.com/jobs "Financial Data Analyst" "Los Angeles"
site:boards.greenhouse.io "Operations Analyst" SQL Remote
```

### Priority 4: Broader net - construction & industry data roles

#### Plain terms (portal CLIs)

```
Project Controls Analyst
Construction Data Analyst
Cost Analyst
```

#### WebSearch-only (`site:` fallback)

```
site:linkedin.com/jobs "Construction Data Analyst" (Remote OR "Los Angeles")
site:linkedin.com/jobs "Project Controls Analyst" "Power BI"
```

## Location Filter

Home base: Los Angeles, CA.
- Los Angeles and surrounding areas (ideal) - hybrid or on-site fine
- Orange County, Long Beach, Pasadena, Burbank, Irvine, Pomona (acceptable, within ~50 miles)
- US Remote (acceptable)
- Inland Empire / Riverside, Ventura (borderline, ~60+ miles)
- Outside Southern California, on-site (relocation - flag for the user to decide per role)

## Eligibility & Experience Filter
- Skip postings that say "no sponsorship", "must be a US citizen", "green card holders only", "W2 only, no visa", or require a security clearance.
- Rank first: postings where the company sponsors visas.
- Skip roles requiring 6+ years or titled Senior / Lead / Manager / Principal.

## Language Filter

Your working languages and levels are in CLAUDE.md's Languages table. When filtering scraped results, apply `04-job-evaluation.md`'s Language Gate: a posting requiring a language you haven't declared at all is excluded; a posting requiring a higher level than you declared in a language you do work in is not excluded, flag it clearly instead (see `job-scraper/SKILL.md`'s Step 3 "Quick Fit Assessment" for how the flag surfaces in `/scrape` output). Postings simply *written* in a language you don't work in, that don't require it on the job, are fine.

## Date Filter

Only include jobs posted within the last 14 days, matching `/scrape` Step 1b.3: use a supported recency filter or filter the returned publication dates client-side. A future application deadline does not bypass this discovery window; `/rank` handles deadline expiry and urgency separately after discovery. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
