# Gold Investment Analysis Presentation

A German-language investment presentation comparing gold performance against the S&P 500 and DAX indices over 25 years (2000-2025).

## Overview

This project analyzes the investment performance of 10,000€ invested across four instruments:
- **Gold** (physical, no capital gains tax in Switzerland)
- **SMIC** (SMI with dividends)
- **S&P 500 Total Return**
- **DAX Performance Index**

Includes calculations for Swiss tax treatment and annualized returns after tax.

## Files

- **gold-slideshow.html** - Main presentation (German) with slides covering:
  - Investment analysis and historical context
  - Tax benefits comparison
  - Market performance comparisons
  - Interactive visualizations

- **gold-slideshow-en.html** - English version of the main presentation

- **gold-chart.html** - Interactive detailed chart showing historical performance with toggle controls:
  - After-tax values in EUR
  - Gross values before tax
  - After-tax percentage returns
  - Gross percentage returns

## Viewing the Project

### In a Browser
Simply open either HTML file directly:
```bash
open gold-slideshow.html
open gold-chart.html
```

### Local Server
For development or to serve over a network:
```bash
python3 -m http.server 8000
# Visit http://localhost:8000/gold-slideshow.html
```

## Technical Details

- **Framework**: Static HTML5 with embedded CSS and JavaScript
- **Charting**: Chart.js (loaded from CDN)
- **Language**: German (with English alternative)
- **Responsive Design**: CSS Grid and Flexbox
- **Currency Format**: EUR with German locale formatting
- **Tax Calculations**: Swiss cantonal tax rates (~12% average on dividend income for stocks, 0% for gold)

## Data

- **Period**: 2000-2025 (26 years)
- **Initial Investment**: 10,000€
- **Annualized Return**: Calculated as (Ending Value / Starting Value)^(1/25) - 1

### Tax Treatment
- Gold: 0% capital gains tax
- Stocks (SMIC, S&P 500, DAX): ~12% average tax on dividend income (varies by canton)

## Browser Compatibility

Works in all modern browsers supporting:
- ES6 JavaScript
- CSS Grid/Flexbox
- Chart.js library

## Development Notes

- No build process or dependencies required
- All styling is inline for portability
- No local setup needed beyond a web browser
- Static files only, no server backend required