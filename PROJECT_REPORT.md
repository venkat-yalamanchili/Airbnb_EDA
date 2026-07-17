# NYC Airbnb Market Intelligence: Pricing, Demand & Availability EDA

## 1. Executive Summary

This project analyzes Airbnb listing data for New York City to understand pricing behavior, neighborhood-level supply, availability patterns, review activity, and host segmentation. The analysis was upgraded from a basic EDA notebook into an industry-style project with business questions, documented data cleaning, feature engineering, visual storytelling, and actionable recommendations.

The original notebook showed that the dataset contains **20,770 listings and 22 columns**. It also identified missing values, duplicate records, and extreme price outliers. The refined notebook improves the analysis by applying controlled cleaning, retaining auditability, engineering business-relevant fields, and using segmented visualizations to produce decision-ready insights.

## 2. Business Context

Airbnb operates as a two-sided marketplace where supply quality, location, price, and availability directly affect guest choice and host performance. A business team may want to know:

- Where is Airbnb supply concentrated?
- Which boroughs and room types command higher prices?
- Which neighborhoods look premium or underpriced?
- How do review patterns signal demand?
- Are hosts mostly individuals or larger operators?
- Which listing segments may represent revenue opportunity?

This project answers those questions using Python-based exploratory data analysis.

## 3. Project Objectives

The objectives of this project are to:

1. Clean and prepare Airbnb listing data for reliable analysis.
2. Identify pricing patterns across boroughs, neighborhoods, and room types.
3. Analyze supply concentration and room-type mix.
4. Evaluate demand signals using reviews and review frequency.
5. Understand availability and minimum-night policies.
6. Segment hosts by portfolio size.
7. Create recruiter-ready documentation and a reproducible GitHub notebook.

## 4. Dataset Overview

The dataset includes Airbnb listing-level attributes such as listing ID, host ID, host name, neighborhood group, neighborhood, latitude, longitude, room type, price, minimum nights, number of reviews, review frequency, availability, rating, bedrooms, beds, and baths.

### Initial Dataset Profile

| Metric | Value |
|---|---:|
| Rows | 20,770 |
| Columns | 22 |
| Duplicate rows identified in original notebook | 12 |
| Raw average price observed in original notebook | $187.71 |
| Raw median price observed in original notebook | $125.00 |
| Raw max price observed in original notebook | $100,000 |

The high maximum price shows that pricing is heavily right-skewed and requires outlier-aware analysis.

## 5. Data Quality and Cleaning

The original notebook used `dropna()` to remove missing rows. The refined version uses a more realistic data-cleaning approach:

- Standardizes column names.
- Removes duplicate rows.
- Converts listing and host IDs to strings.
- Parses `last_review` as a date.
- Converts fields like rating, bedrooms, and baths into numeric values where possible.
- Removes records only when they are missing critical fields required for analysis, such as price, room type, borough, neighborhood, latitude, or longitude.
- Applies IQR-based price filtering only to create a focused analysis dataset while preserving the cleaned base dataset.

This approach is more professional because it avoids deleting useful data unnecessarily and explains why specific records are removed.

## 6. Feature Engineering

The refined notebook adds business-focused features that improve analysis quality.

| Feature | Business Use |
|---|---|
| `price_per_bed` | Compares relative value across listings with different capacities. |
| `availability_bucket` | Groups listings into availability segments. |
| `stay_policy` | Classifies listings by minimum-night requirement. |
| `host_portfolio_type` | Distinguishes individual hosts from multi-listing operators. |
| `estimated_annual_revenue_proxy` | Creates a directional revenue opportunity measure. |
| `review_recency_days` | Measures recent customer engagement. |
| `opportunity_segment` | Groups listings by price and availability quadrant. |

## 7. Analysis Framework

The refined EDA is organized around business questions rather than random charts.

### Business Question 1: Where is Airbnb supply concentrated?

The notebook analyzes listing count by borough, neighborhood, and room type. This reveals where competition is highest and which inventory types dominate each borough.

### Business Question 2: How does price vary by market segment?

The analysis compares median and average price across boroughs, room types, and neighborhoods. Median price is emphasized because Airbnb prices are skewed by luxury listings and extreme values.

### Business Question 3: Which neighborhoods are premium markets?

Neighborhoods are ranked by median price after applying a minimum listing threshold. This avoids overvaluing neighborhoods that have only a few listings.

### Business Question 4: How does availability affect opportunity?

The notebook groups listings by annual availability. High-price, high-availability listings may represent strong revenue potential, while low-price, high-availability listings may indicate underpricing or weaker demand.

### Business Question 5: What do reviews suggest about demand?

The analysis uses total reviews, reviews per month, and review recency as demand proxies. These signals help identify segments that may have stronger customer engagement.

### Business Question 6: Are hosts individual or professional operators?

Listings are segmented by host portfolio size. This helps identify whether inventory is fragmented across individual hosts or concentrated among larger operators.

### Business Question 7: Where are listings geographically clustered?

A latitude-longitude scatterplot shows how listings are distributed spatially and helps connect location with price and room type.

## 8. Key Insights from the Original Notebook

The initial notebook already revealed several important patterns:

1. The dataset has a strong price outlier problem. The raw maximum price reached $100,000, making outlier-aware analysis necessary.
2. Manhattan had the highest average price in the original filtered analysis, followed by Brooklyn.
3. Bronx, Queens, and Staten Island showed lower average prices compared with Manhattan and Brooklyn.
4. Entire home/apartment listings generally commanded higher prices than private rooms.
5. Room type and borough are important drivers of pricing differences.
6. Geographic visualization shows that listings are spatially clustered around dense NYC neighborhoods.
7. Reviews and price have a non-linear relationship, meaning review volume alone does not explain pricing.

## 9. Business Recommendations

### Recommendation 1: Use segmented pricing benchmarks
Pricing should be compared within borough, neighborhood, room type, and capacity segment. A single citywide price benchmark is too broad for marketplace decision-making.

### Recommendation 2: Prioritize premium neighborhood analysis
Neighborhood-level median price rankings can help identify premium markets and possible pricing opportunities.

### Recommendation 3: Monitor high-availability listings
Listings with high availability and low price may require repositioning, improved listing quality, or promotional support.

### Recommendation 4: Segment host strategy
Single-listing hosts and large-portfolio hosts likely need different support, pricing guidance, and marketplace policies.

### Recommendation 5: Use reviews as demand signals, not absolute demand
Review metrics should be used directionally because not every guest leaves a review.

### Recommendation 6: Combine geographic and pricing analysis
Location-based visuals should be paired with pricing and availability metrics to identify underperforming or premium areas.

## 10. Deliverables

This project package includes:

- `Airbnb_NYC_EDA_Industry_Ready.ipynb`: Refined notebook with comments, markdown, business questions, feature engineering, and advanced EDA.
- `README.md`: GitHub-ready repository documentation.
- `PROJECT_REPORT.md`: Business-style project report.
- `Airbnb_EDA_Project_Report.docx`: Word version of the project report.
- `requirements.txt`: Python dependencies.

## 11. Skills Demonstrated

This project demonstrates:

- Python data analysis
- Pandas and NumPy
- Data cleaning and quality auditing
- Feature engineering
- Data visualization
- Exploratory data analysis
- Outlier handling
- Business problem framing
- Marketplace analytics
- Data storytelling
- GitHub documentation

## 12. Limitations

- Review count is a proxy for demand and does not equal booking volume.
- Availability does not guarantee actual occupancy.
- Estimated revenue is a directional proxy, not actual revenue.
- Price outlier filtering is used for visualization clarity, not as a claim that excluded listings are invalid.
- The project is exploratory and does not establish causation.

## 13. Future Enhancements

Future project improvements could include:

1. Predictive price modeling.
2. Power BI or Tableau dashboard development.
3. Neighborhood clustering using price, reviews, and availability.
4. Time-series analysis if historical listing snapshots are available.
5. Integration with external tourism, hotel, or event data.
6. Recommendation engine for pricing optimization.

## 14. Conclusion

This project turns a basic Airbnb EDA into a recruiter-ready analytics case study. It demonstrates the ability to clean messy data, ask business-relevant questions, build meaningful features, create clear visuals, and translate exploratory findings into recommendations. The final notebook and documentation are structured for GitHub, portfolio presentation, and resume discussion.
