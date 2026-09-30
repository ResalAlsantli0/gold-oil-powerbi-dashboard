# Gold & Oil Prices Analytics Dashboard

An interactive Power BI project that explores live and historical gold and West Texas Intermediate (WTI) crude-oil prices. The dashboard helps users examine price trends, volatility, growth, the gold-to-oil ratio, and the relationship between two globally important commodities.

## Project objectives

- Present gold and oil market data in a clear, interactive format.
- Track the latest, maximum, and minimum commodity prices.
- Explore monthly and annual price movements.
- Examine gold-price volatility and year-over-year growth.
- Compare gold and oil through the gold-to-oil ratio and correlation visuals.
- Support time-based exploration with connected filters and slicers.

## Data sources

The dashboard retrieves commodity data from the **Alpha Vantage API**:

| Dataset | Frequency | Unit |
| --- | --- | --- |
| Gold spot price (XAU/USD) | Daily | USD per troy ounce |
| WTI crude-oil price | Monthly | USD per barrel |

The supplied API documentation is available in `Data API.pdf`. Alpha Vantage request limits may affect refresh availability.

## Data model and preparation

Data is loaded from JSON web endpoints and transformed in Power Query. Gold and oil remain in separate fact tables and connect to a shared DAX Date Table in a star-schema design. The date dimension provides year, month, quarter, year-month, and year-quarter fields so the same time filters can control both datasets.

## Dashboard pages

### Page 1 — Overview

- KPI cards for the latest, maximum, and minimum gold and oil prices.
- Gold-price volatility gauge.
- Monthly gold and oil trend charts.
- Year-month slicer for focused analysis.

### Page 2 — Detailed analysis

- Annual gold-price comparison.
- Year-over-year gold-price growth.
- Average gold-to-oil ratio by year.
- Gold and oil correlation trend.
- Month slicer and interactive cross-filtering.

## Open and refresh

1. Install **Power BI Desktop**.
2. Download and open `BIProject_final2.pbix`.
3. Select **Home → Refresh** to request the latest API data.
4. Use the slicers and select chart elements to filter the other visuals.

If an API refresh fails, check the internet connection and the Alpha Vantage request limit. Data-source permissions can be reset from **File → Options and settings → Data source settings** in Power BI Desktop.

## Repository files

- `BIProject_final2.pbix` — interactive Power BI dashboard.
- `Data API.pdf` — API reference used by the project.
- `Read me dashboard-61s.docx` — dashboard installation, usage, refresh, and troubleshooting guide.

## Tools and techniques

- Microsoft Power BI Desktop
- Power Query
- DAX and time-intelligence calculations
- Star-schema data modeling
- REST API and JSON data ingestion
- Interactive filters, slicers, KPIs, gauges, and trend charts

## Scope

This is an academic business-intelligence project. The dashboard supports exploratory analysis and should not be treated as financial or investment advice. Commodity values depend on the API response and the most recent successful refresh.
