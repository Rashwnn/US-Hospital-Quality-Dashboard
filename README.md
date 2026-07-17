# US Hospital Quality Dashboard

An interactive Power BI dashboard exploring hospital quality ratings across the United States, built from CMS (Centers for Medicare & Medicaid Services) public data.

## Guiding Question

Where in the U.S. is hospital quality strongest vs. weakest, and how much of the system is at risk on safety/readmission performance?

## Key Findings

- **42.4%** of all US hospitals have at least one quality measure (mortality, safety, or readmissions) performing worse than the national average — a meaningful share of the system carrying real financial risk, since CMS ties Medicare reimbursement to these measures.
- **Ownership type correlates with quality.** Federal/public hospitals average a 4.16 rating (out of 5), compared to just 2.83 for for-profit hospitals — a 1.33-point gap.
- **Geographic risk is concentrated.** New Jersey (70.9%), Florida (65.6%), Maryland (60.7%), and New York (60.7%) have the highest share of hospitals underperforming relative to the national average.
- **National average hospital rating: 3.14 / 5** across 5,432 tracked hospitals.

## Dashboard Features

- **KPI cards** — national average rating, total hospitals tracked, % of hospitals below average on safety/readmissions
- **US map** — hospital quality rating by state (choropleth), with a matching color-scale legend
- **Ownership comparison** — average rating by ownership category (Federal/Public, Nonprofit, Government, For-Profit)
- **State ranking (scrollable)** — every state ranked by % of hospitals underperforming, not just a fixed top-N cutoff

## Data Source

- [CMS Provider Data Catalog — Hospital General Information](https://data.cms.gov/provider-data/dataset/xubh-q36u)

## Data Processing

Raw CMS data was cleaned and enriched using Python (pandas):
- Simplified hospital ownership into four broad categories
- Converted the overall star rating to a numeric field (excluding "Not Available" entries)
- Calculated a per-hospital count of "worse than national average" measures across mortality, safety, and readmissions
- Aggregated to state level: hospital count, average rating, and % of hospitals with at least one worse-than-average measure

See `data/hospitals_clean.csv` (hospital-level) and `data/hospitals_state_summary.csv` (state-level) for the processed outputs.

## Tools Used

- **Python (pandas)** — data cleaning and aggregation
- **Power BI** — dashboard design and visualization

## Files

```
hospital-quality-dashboard/
├── README.md
├── data/
│   ├── hospitals_clean.csv
│   └── hospitals_state_summary.csv
├── dashboard/
│   └── hospital_quality_dashboard.pbix
└── screenshots/
    └── dashboard_overview.png
```
