# Python Dynamic Data Extraction

Reliable extraction of data from modern, JavaScript-rendered websites turned into clean, structured CSV or JSON output.

## The Problem

A lot of useful web data isn't sitting in plain HTML anymore. Modern sites load content dynamically after scrolling, after a button click, after an API call finishes in the background. A basic scraper that just fetches the raw HTML gets nothing useful back.

This project demonstrates a reliable way to handle that: render the page properly, wait for the real content to load, then extract and validate it.

## Who This Is For

Anyone who needs structured data from a website that:
- Loads content via JavaScript after the initial page load
- Uses pagination or infinite scroll
- Needs the result as clean, ready-to-use CSV or JSON not raw HTML

## Features

- **Playwright-based rendering** — handles JavaScript-heavy pages properly, not just static HTML
- **Pagination handling** — follows multi-page results automatically
- **Data validation** — checks extracted fields before they're written out, so bad or missing data doesn't silently slip through
- **Structured output** — clean CSV and JSON, ready to open in Excel or load into another system
- **Error handling & logging** — failures are logged clearly instead of crashing silently
- **Retry logic** — handles timeouts and temporary network issues without losing the whole run

## Architecture

Target URL

↓

Playwright (render page, wait for content)

↓

Extract fields (selectors)

↓

Validate (check required fields, types, duplicates)

↓

Structured output (CSV / JSON)

↓

Log (successes, failures, skipped records)

## Installation

```bash
git clone https://github.com/CharlesKariuki-001/python-data-extraction.git
cd python-data-extraction
python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt
playwright install
```

## Usage

```bash
python src/main.py --url "https://example.com/products" --output data/output.csv
```

Example output (`data/output.csv`):
name,price,availability
Product A,$19.99,In Stock
Product B,$24.50,Out of Stock

## Testing

```bash
pytest
```

Tests cover: selector reliability, handling of missing fields, empty-result pages, and malformed HTML not just the "happy path" where everything works perfectly.

## Limitations

- Built and tested against publicly accessible pages. It does not attempt to bypass logins, CAPTCHAs, or any access control — see the Responsible Use note below.
- Site structures change over time; selectors may need updating if a target site redesigns its layout.
- Rate limiting and request pacing should be configured appropriately for the target site's terms.

## Responsible Use

This project extracts data only from public or explicitly authorized sources. It is **not** designed or intended to bypass authentication, CAPTCHAs, paywalls, or any other access control. For real client work, I always confirm the client has the right to request the data before starting.

## What I Learned

Building this reinforced that the hard part of scraping usually isn't "get the HTML"  it's handling the messy reality: pages that load slowly, elements that shift, and data that needs validating before you can trust it.

## Need This Built for Your Workflow?

If you have a website you need structured, reliable data from get in touch. I scope the job first (confirm the fields, check the site structure), then give a fixed price and delivery timeline.

📬 [LinkedIn](https://ke.linkedin.com/in/charles-mburu-838965382) · [X](https://x.com/KariukiBuilds__)
