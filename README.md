# NYC Airbnb Market Intelligence: Pricing, Demand & Availability EDA

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-orange)
![EDA](https://img.shields.io/badge/Project-Exploratory%20Data%20Analysis-purple)

## Project Overview

This project analyzes Airbnb listing data to uncover pricing, availability, review, host, and neighborhood-level patterns across New York City. The goal is to transform raw listing data into business-ready insights that could support marketplace strategy, pricing decisions, host segmentation, and neighborhood opportunity analysis.

The original dataset contains **20,770 records and 22 columns**. The upgraded notebook applies structured data cleaning, feature engineering, outlier handling, segmented analysis, and business-focused visualization.

## Business Problem

Airbnb marketplaces need to understand where supply is concentrated, how pricing varies across locations and room types, which host segments dominate inventory, and where pricing or availability patterns suggest business opportunity. This analysis answers those questions using Python-based EDA.

## Key Business Questions

1. Which boroughs and neighborhoods have the highest Airbnb supply?
2. How does nightly price vary by borough, neighborhood, and room type?
3. Which listing segments show the strongest revenue opportunity based on price and availability?
4. How do reviews and review frequency vary across listing types?
5. How do minimum-night requirements affect guest accessibility?
6. Are listings mostly controlled by individual hosts or multi-listing operators?
7. Where are listings geographically clustered across NYC?

## Dataset Features

The dataset includes listing-level information such as:

- Listing ID and listing name
- Host ID and host name
- Borough and neighborhood
- Latitude and longitude
- Room type
- Price
- Minimum nights
- Number of reviews
- Last review date
- Reviews per month
- Host listing count
- Availability across 365 days
- Rating, bedrooms, beds, and baths

## Tools Used

- **Python**: Core analysis workflow
- **Pandas / NumPy**: Data cleaning, transformation, and aggregation
- **Matplotlib / Seaborn**: Data visualization
- **Jupyter Notebook**: Project presentation and reproducible analysis

## Project Workflow

```text
1. Load raw Airbnb listing data
2. Audit structure, data types, missing values, and duplicates
3. Clean and standardize the dataset
4. Convert IDs, dates, and numeric-like text columns
5. Engineer business-focused fields
6. Analyze supply, pricing, availability, reviews, hosts, and location
7. Build executive insights and recommendations
8. Export cleaned data and summary tables
```

## Feature Engineering

The refined notebook creates several business-focused fields:

| Feature | Purpose |
|---|---|
| `price_per_bed` | Compares value across listings with different capacities |
| `availability_bucket` | Segments listings by yearly availability |
| `stay_policy` | Groups listings by minimum-night requirement |
| `host_portfolio_type` | Separates individual hosts from multi-listing operators |
| `estimated_annual_revenue_proxy` | Measures opportunity using price multiplied by available days |
| `review_recency_days` | Measures how recently a listing received a review |
| `opportunity_segment` | Classifies listings by price and availability quadrant |

## Key Analysis Areas

### 1. Market Supply Analysis
Identifies listing concentration across boroughs, neighborhoods, and room types.

### 2. Pricing Analysis
Compares median and average nightly prices by borough, room type, and neighborhood while using outlier-aware visualizations.

### 3. Availability and Stay Policy Analysis
Evaluates yearly availability and minimum-night requirements to understand market accessibility.

### 4. Review and Demand Signal Analysis
Uses review count, reviews per month, and review recency as directional demand signals.

### 5. Host Segmentation
Analyzes whether inventory is driven by individual hosts or professional/multi-listing hosts.

### 6. Geographic Analysis
Visualizes listing distribution using latitude and longitude to reveal spatial clustering.

### 7. Opportunity Segmentation
Classifies listings into price-versus-availability quadrants to identify revenue opportunities and underperforming inventory.

## Initial Findings from the Original Notebook

- The raw dataset contains **20,770 listings** and **22 columns**.
- The original analysis identified missing values in fields such as price, neighborhood, coordinates, room type, and review columns.
- The dataset contained **12 duplicate rows**, which were removed in the refined workflow.
- Price was highly right-skewed, with extreme outliers in the raw data.
- Manhattan showed the highest average price in the original focused analysis, followed by Brooklyn.
- Entire home/apartment listings generally priced higher than private rooms.
- Location, room type, availability, and host portfolio size are important drivers of market segmentation.

## Repository Structure

```text
.
├── Airbnb_NYC_EDA_Industry_Ready.ipynb     # Main refined analysis notebook
├── PROJECT_REPORT.md                       # Business project report
├── README.md                               # GitHub repository overview
├── requirements.txt                        # Python dependencies
└── outputs/                                # Generated files after running notebook
    ├── airbnb_cleaned_focused_dataset.csv
    ├── borough_supply_summary.csv
    ├── price_by_borough_summary.csv
    ├── price_by_room_type_summary.csv
    └── neighborhood_price_summary.csv
```

## How to Run This Project

1. Clone this repository.
2. Add the Airbnb dataset file to the project folder and name it `datasets.csv`.
3. Install required libraries:

```bash
pip install -r requirements.txt
```

4. Open the notebook:

```bash
jupyter notebook Airbnb_NYC_EDA_Industry_Ready.ipynb
```

5. Run all cells from top to bottom.

## Business Impact

This project demonstrates the ability to move beyond basic charting and deliver decision-ready analysis. The notebook frames EDA around marketplace questions, applies thoughtful data cleaning, builds reusable features, and converts patterns into recommendations for pricing, supply planning, host strategy, and opportunity discovery.

## Skills Demonstrated

- Exploratory Data Analysis
- Data Cleaning and Data Quality Auditing
- Feature Engineering
- Business Question Framing
- Segmented Aggregation and KPI Analysis
- Outlier Treatment
- Data Visualization
- Geographic Analysis
- Business Storytelling
- GitHub Project Documentation

## Limitations

- Review activity is a proxy for demand, not true booking volume.
- Estimated revenue is a directional proxy, not actual revenue.
- Price outliers are handled separately for visualization clarity.
- This project is exploratory and does not make causal claims.

## Next Steps

- Add predictive modeling to estimate price or booking likelihood.
- Build a dashboard in Power BI or Tableau for stakeholder consumption.
- Add neighborhood-level clustering based on price, availability, and demand signals.
- Compare Airbnb pricing with external hotel or tourism demand data.
- Build a recommendation engine for pricing optimization.
