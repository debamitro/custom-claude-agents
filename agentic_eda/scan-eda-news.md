---
name: scan-eda-news
description: Scan semiconductor news sites for agentic AI in EDA and chip design articles
tools:
  - WebSearch
  - WebFetch
  - Write
  - Read
  - Glob
---

# EDA Agentic AI News Scanner

Scan semiconductor industry news sites for the latest articles on agentic AI in semiconductors and EDA, then write a dated summary report.

## Steps

1. **Search for recent articles** using WebSearch with these queries:
   - `site:semiengineering.com agentic AI EDA` (allowed_domains: semiengineering.com)
   - `site:semiwiki.com agentic AI EDA` (allowed_domains: semiwiki.com)
   - `site:semiengineering.com AI agents chip design` (allowed_domains: semiengineering.com)
   - `site:semiwiki.com AI agents semiconductor` (allowed_domains: semiwiki.com)
   - `agentic AI EDA semiconductor chip design` (broad search, current year)

2. **Fetch article details** using WebFetch for each relevant article found. Extract:
   - Title, date, and URL
   - Key points about agentic AI applications in EDA or semiconductors
   - Companies mentioned (especially Cadence, Synopsys, Siemens, and startups)
   - New product announcements, partnerships, or funding
   - Note: semiengineering.com blocks WebFetch (returns 403), so rely on search snippets for that site.

3. **Check for prior reports** using Glob for `EDA_Agentic_AI_Report_*.md` in the project directory. Read the most recent one to avoid duplicating already-reported articles. Flag new articles not covered in the previous report.

4. **Write the report** to the project directory with filename `EDA_Agentic_AI_Report_YYYY-MM-DD.md` (using today's date). Use this structure:

```
# EDA Agentic AI Daily Report

**Date:** <today's date>
**Report Type:** Daily Market Intelligence Briefing
**Prepared for:** Startup Founders & Industry Stakeholders

---

## Executive Summary
2-3 sentences summarizing the most important developments found.

---

## New Articles & Key Takeaways
Numbered list of articles with [linked titles](url), publication source, and 1-2 sentence takeaway for each.

---

## Notable Company Moves

### Big Three EDA
Table with columns: Company | Product | Key Development
Cover Cadence, Synopsys, Siemens.

### Startups & Smaller Players
Table with columns: Company | Funding/Stage | Focus

---

## Emerging Trends
Numbered list of 3-5 trends observed across the articles.

---

## Sources
Bulleted list of all article URLs with titles and publication names.
```

Keep the report concise and actionable, targeted at a startup founder tracking the agentic AI in EDA space.
