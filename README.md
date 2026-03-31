# ASOS Product & Stockout Analysis

## Overview
This project analyzes a dataset of approximately 30,800 ASOS products to identify inventory gaps and quantify revenue lost due to stockouts. By examining size availability across brands, the analysis surfaces which brands represent the greatest opportunity for revenue recovery through better inventory management.

---

## Dataset
- **Source:** `products_asos.csv`
- **Size:** 30,845 rows × 9 columns
- **Fields:** URL, product name, size availability, category, price, color, SKU, description, and images

---

## Methodology
1. Data Cleaning: Identified and handled 18 fully null rows across the dataset.
2. Stockout Quantification: Parsed the `size` column to calculate a stockout count and stockout rate per product (proportion of sizes listed as "Out of stock").
3. Lost Revenue Estimation: Approximated lost revenue per product as `price × stockout_count`, treating each unavailable size as a missed sale.
4. Brand-Level Aggregation: Grouped metrics by brand (filtered to brands with >10 products) to compare average price, average stockout rate, and total lost revenue.
5. Strategic Segmentation: Visualized brands on a price vs. stockout rate scatter plot, with bubble size representing lost revenue, to identify high-priority brands.

---

## Key Findings

<img width="1007" height="708" alt="image" src="https://github.com/user-attachments/assets/693872de-6a35-43a4-9b4e-122c6ae41c4c" />

1. Stockout rates across the catalog range between 10–30%, reflecting moderate but persistent availability issues.
2. Lost revenue is highly concentrated a small group of premium brands accounts for a disproportionate share of missed sales due to stockouts.
3. Top revenue-loss offenders include Wonderbra, Mango and Naked driven by a combination of high prices and lagging stock replenishment cycles. 
4. Premium brands with high stockout rates cluster in the high-risk quadrant of the brand strategy matrix, making them the clearest targets for inventory intervention.
5. Low-price brands contribute minimally to overall lost revenue, suggesting inventory resources are better directed elsewhere.

---

## Recommendations

### High-Price, High-Stockout Brands
These brands offer the greatest revenue recovery potential.
- Increase safety stock levels for top-selling SKUs.
- Shorten replenishment cycles to reduce the window of unavailability.
- Improve demand forecasting for high-value products, especially across size runs.

### High-Stockout, Low-Price Brands
Elevated stockout rates regardless of price may signal operational inefficiencies rather than demand spikes.
- Review supplier lead times and reliability.
- Evaluate reorder thresholds and inventory policies.
- Investigate whether warehouse or distribution bottlenecks are contributing to stockouts.

### Low-Stockout Brands
These brands show inventory levels well-aligned with demand.
- Maintain current forecasting and replenishment practices.
- Monitor stockout trends to catch early signs of deterioration.

### Ongoing Monitoring
- Track stockout rate by brand as a standing KPI.
- Set automated alerts for brands exceeding acceptable stockout thresholds.
- Review lost revenue metrics periodically to identify emerging risks before they escalate.

---

## Strategic Takeaway
Lost revenue from stockouts is concentrated among a small set of high-price brands. Directing inventory optimization efforts toward this group offers the highest return — both in recovered revenue and improved customer availability.

---

## Tools & Libraries
`Python` · `pandas` · `matplotlib` · `seaborn`
