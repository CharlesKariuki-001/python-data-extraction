# Python Dynamic Data Extraction

A practical Python automation project for extracting structured data from modern JavaScript-rendered websites.

## Problem

Many modern websites do not place all their useful information directly in the initial HTML page. Instead, JavaScript loads or changes the content after the page opens.

This project explores how Python automation can reliably collect that information and turn it into clean, structured data.

## Goals

- Extract data from dynamic websites
- Automate browser interaction
- Validate collected information
- Produce structured CSV and JSON output
- Make the extraction process reliable and repeatable

## Technologies

- Python
- Playwright
- CSV
- JSON
- pytest

## Project Structure

```text
python-data-extraction/
│
├── src/
│   └── main.py
│
├── tests/
│   └── test_main.py
│
├── data/
│   └── sample/
│
├── docs/
│
├── .env.example
├── .gitignore
├── requirements.txt
└── README.md
