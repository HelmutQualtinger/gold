# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a German-language investment presentation comparing gold performance vs. S&P 500 and DAX indices since 2000. The project consists of static HTML files with embedded JavaScript and CSS, using Chart.js for data visualization.

**Files:**
- `gold-slideshow.html`: Main presentation with slides covering investment analysis, tax benefits, and market comparisons
- `gold-chart.html`: Interactive chart page showing detailed historical performance with toggle between absolute values (€) and percentage changes

## Key Architecture

Both HTML files are self-contained with:
- Embedded CSS for styling (dark theme with gold accents)
- Chart.js library loaded from CDN for visualizations
- Vanilla JavaScript for interactivity
- German language content throughout

**Data:**
- Historical investment values from 2000-2025 (26 years of data)
- Starting investment: 10,000€
- Four instruments tracked: Gold, SMIC (SMI with dividends), S&P 500 Total Return, DAX Performance Index
- Calculations include:
  - Absolute Euro values before and after Swiss tax rates
  - Percentage change calculations
  - Annualized returns after tax (25-year period)

**Key Features:**
- Interactive chart controls:
  - "Nach Steuern (€)" - After-tax values in EUR
  - "Brutto-Werte (€)" - Gross values before tax
  - "Nach Steuern (%)" - After-tax percentage returns
  - "Brutto (%)" - Gross percentage returns
- Swiss tax treatment calculations:
  - Gold: 0% (no capital gains tax in Switzerland)
  - Stocks (SMIC, S&P 500, DAX): ~12% average on dividend income (varies by canton)
- Annualized return calculation: (Ending Value / Starting Value)^(1/25) - 1
- After-tax values calculated as: Value - (Gain × Tax Rate)

## Viewing the Project

Since this is static HTML, open either file directly in a web browser:
```bash
open gold-slideshow.html
open gold-chart.html
```

Or serve locally using Python:
```bash
python3 -m http.server 8000
# Then visit http://localhost:8000/gold-slideshow.html
```

## Development Notes

- No build process, linter, or test framework required
- All styling is inline with responsive design using CSS Grid/Flexbox
- Chart.js version loaded via CDN (no local dependencies)
- German locale formatting for currency and number display
