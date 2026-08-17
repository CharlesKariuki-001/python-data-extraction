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
