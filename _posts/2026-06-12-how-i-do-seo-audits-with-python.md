---
title: "How I Do SEO Audits with Python (My Actual Workflow)"
date: 2026-06-12 10:00:00 +0530
categories: [SEO, Python]
tags: [seo, python, technical-seo, automation, audit]
---

Most SEO audits are done manually — crawl a site, export a CSV, open it in Excel, and spend hours filtering through thousands of rows. That works, but it doesn't scale.

Here's how I use Python to automate the heavy lifting in my SEO audits at [Compile & Commit](https://compileandcommit.com).

## Why Python for SEO?

Tools like Ahrefs and Semrush are excellent, but they have limits:
- API rate limits
- Can't combine data from multiple sources easily
- You're stuck in their UI for analysis

Python removes those walls. You pull data exactly how you need it, combine sources, and build reusable audit scripts you can run on any site in minutes.

## My Audit Workflow

### Step 1 — Crawl the Site with Screaming Frog (or requests + BeautifulSoup)

For smaller sites, I crawl directly with Python:

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

def crawl_page(url):
    response = requests.get(url, timeout=10)
    soup = BeautifulSoup(response.text, 'html.parser')
    
    return {
        'url': url,
        'title': soup.find('title').text if soup.find('title') else '',
        'meta_description': soup.find('meta', {'name': 'description'})['content'] if soup.find('meta', {'name': 'description'}) else '',
        'h1': soup.find('h1').text if soup.find('h1') else '',
        'status_code': response.status_code,
        'word_count': len(soup.get_text().split())
    }
```

### Step 2 — Pull Data from Google Search Console API

```python
from google.oauth2.credentials import Credentials
from googleapiclient.discovery import build

# Connect to GSC
service = build('searchconsole', 'v1', credentials=creds)

# Pull top pages by clicks
response = service.searchanalytics().query(
    siteUrl='https://yoursite.com',
    body={
        'startDate': '2026-01-01',
        'endDate': '2026-06-01',
        'dimensions': ['page'],
        'rowLimit': 500
    }
).execute()
```

### Step 3 — Identify Quick Win Opportunities

Pages ranking on positions 4–20 are my priority — they're close to page 1 with a small push:

```python
df = pd.DataFrame(rows)
quick_wins = df[(df['position'] >= 4) & (df['position'] <= 20)]
quick_wins = quick_wins.sort_values('impressions', ascending=False)
print(quick_wins[['page', 'query', 'position', 'clicks', 'impressions']].head(20))
```

### Step 4 — Output a Prioritised Action Report

I export everything into a structured Excel report with colour-coded priority levels — critical issues (red), medium (yellow), and optimisation opportunities (green).

## What This Saves Me

Running this on a 500-page site used to take a full day manually. Now it takes about 30 minutes — mostly just reviewing the output.

## Tools I Use Alongside Python

- **Ahrefs** — backlink data and keyword research
- **Google Search Console API** — real performance data
- **Screaming Frog** — for large site crawls (their Python API is handy)
- **Pandas + openpyxl** — data manipulation and report generation

---

If you want the full script, drop me a message on [LinkedIn](https://www.linkedin.com/in/rishavgc/) — I'm happy to share it.

