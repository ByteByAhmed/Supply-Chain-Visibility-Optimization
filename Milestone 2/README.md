# Supply Chain Visibility & Optimization – Milestone 2

## Project Overview

This project is part of the **Supply Chain Visibility & Optimization** series. Milestone 2 focuses on building interactive **Inventory Analytics** and **Delivery Performance** dashboards using **Microsoft Power BI**.

The dashboards provide insights into inventory health, stock optimization, warehouse performance, delivery efficiency, and logistics performance using DAX measures, KPIs, and interactive visualizations.

---

# Objectives

## Inventory Analytics Dashboard

- Analyze inventory performance across warehouses and regions.
- Calculate Inventory Turnover Ratio.
- Identify Fast-Moving, Slow-Moving, and Dead Stock products.
- Monitor stock quantity, safety stock, and reorder levels.
- Track inventory value trends over time.
- Evaluate warehouse utilization and inventory optimization opportunities.

## Delivery Performance Dashboard

- Analyze On-Time vs Late Deliveries.
- Measure Delivery Lead Time.
- Evaluate Late Delivery Risk.
- Monitor regional delivery performance.
- Compare shipping modes.
- Analyze delivery trends over time.
- Support drill-down analysis by region and product category.

---

# Dashboard Features

## Inventory Analytics

### KPIs

- Total Inventory Value
- Total Stock Quantity
- Inventory Turnover Ratio
- Dead Stock Count
- Dead Stock Quantity
- Slow Moving Quantity
- Warehouse Capacity Used %
- Products to Reorder
- Products Below Safety Stock

### Analysis

- Inventory Value Trend
- Inventory by Warehouse
- Inventory by Region
- Inventory by Product Category
- Warehouse Utilization
- Stock Status Distribution
- Inventory Turnover Ranking
- Month-over-Month Inventory Value Change

---

## Delivery Performance

### KPIs

- Total Orders
- Late Delivery %
- On-Time Delivery %
- Advance Shipping %
- Fulfillment Rate
- Canceled Orders
- Lead Time Variance

### Analysis

- Delivery Trend Over Time
- Regional Late Delivery Rate
- Delivery Status Distribution
- Shipping Mode Performance
- Product-wise Delivery Analysis
- Regional Drill-down
- Late Delivery Trend

---

# Inventory Turnover Calculation Approach

Two Inventory Turnover metrics were implemented.

### Sales Based Inventory Turnover

```DAX
Inventory Turnover Ratio =
DIVIDE(
    [Total Sales],
    [Avg inventory value],
    0
)
```

This metric measures how efficiently inventory is converted into sales revenue.

A higher turnover ratio indicates:

- Better inventory utilization
- Faster stock movement
- Lower holding costs

---

### Unit Based Inventory Turnover

```DAX
Inventory Turnover Ratio (Units) =
DIVIDE(
    [Units Sold],
    AVERAGE(Fact_table[stock_qty]),
    0
)
```

This calculates inventory movement based on quantity sold instead of sales value.

---

# Slow-Moving and Fast-Moving Inventory Identification Logic

Inventory movement is determined using the number of days since the last sale.

### Days Since Last Sale

The latest sales date for each product is compared against the latest order date available in the dataset.

### Stock Classification Logic

| Condition | Status |
|-----------|--------|
| Stock = 0 | Out of Stock |
| More than 90 idle days | Dead Stock |
| Between 31–90 idle days | Slow-Moving |
| 30 days or less | Active (Fast-Moving) |

This logic helps identify:

- Dead inventory
- Overstocked products
- Frequently sold products
- Inventory requiring replenishment

---

# Reorder Logic

Products requiring replenishment are identified using Safety Stock and Reorder Level.

### Classification

- Critical – Below Safety Stock
- Reorder Now
- OK

Recommended reorder quantity is calculated using the Stock Optimization Gap.

---

# Delivery Performance Analysis Methodology

Delivery performance is evaluated using multiple operational KPIs.

### Metrics Used

- Total Orders
- On-Time Delivery %
- Late Delivery %
- Advance Shipping %
- Fulfillment Rate
- Lead Time Variance
- Regional Late Delivery Rate

### Lead Time Variance

```text
Actual Shipping Days
−
Scheduled Shipping Days
```

Positive values indicate delivery delays.

Negative values indicate deliveries completed earlier than scheduled.

---

# Key DAX Measures

Some important measures used include:

- Total Sales
- Total Profit
- Order Count
- Average Order Value
- Inventory Turnover Ratio
- Dead Stock Count
- Dead Stock Value
- Warehouse Capacity Used %
- Products to Reorder
- Late Delivery %
- On-Time Delivery %
- Fulfillment Rate
- Lead Time Variance
- Regional Late Rate

---

# Business Insights

The dashboards help organizations answer questions such as:

- Which products are not moving?
- Which warehouses require stock replenishment?
- Which regions experience the highest delivery delays?
- How efficiently is inventory utilized?
- Which product categories generate the highest sales?
- Where should inventory optimization efforts be focused?

---

# Business Recommendations

## Inventory

- Reduce inventory holding costs by clearing dead stock.
- Increase inventory turnover by improving demand forecasting.
- Replenish products falling below reorder levels.
- Monitor warehouse utilization to prevent overstocking.
- Optimize inventory allocation across warehouses.

## Delivery

- Improve logistics planning in regions with high late delivery rates.
- Monitor shipping performance regularly.
- Reduce lead time variance through better route planning.
- Improve supplier coordination.
- Analyze delayed shipments to identify operational bottlenecks.
BE – Information Science & Engineering

Nitte Meenakshi Institute of Technology (NMIT)

```

This README is suitable for a professional GitHub portfolio and includes all the sections requested in the milestone instructions while being well-formatted and easy to read.
