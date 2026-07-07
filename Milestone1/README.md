# Supply Chain Vision – End-to-End Logistics Dashboard (Milestone 1)

## Objective

The objective of this project is to develop a Power BI dashboard that provides end-to-end visibility into supply chain operations. The dashboard helps organizations monitor logistics performance, inventory movement, supplier performance, warehouse utilization, and delivery efficiency using interactive visualizations and Key Performance Indicators (KPIs).

Milestone 1 focuses on:
- Importing and preparing the supply chain dataset.
- Cleaning and transforming the data.
- Designing a Star Schema data model.
- Creating relationships between fact and dimension tables.
- Building the KPI foundation for future dashboard development.

---

## Dataset Source

**Primary Dataset**

DataCo Global Supply Chain Dataset

Kaggle:
https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

### Dataset Description

The DataCo Global Supply Chain Dataset contains real-world supply chain and logistics information, including:

- Customer Information
- Product Information
- Orders
- Shipments
- Delivery Status
- Warehouse Data
- Geographic Locations
- Sales and Profit Details

The dataset is used to analyze inventory management, transportation efficiency, delivery performance, supplier performance, and overall supply chain operations.

---

## Data Cleaning and Transformation Steps

The dataset was transformed using Power Query Editor in Power BI.

### Data Cleaning

- Imported the CSV dataset into Power BI.
- Renamed the imported table as **Fact_Table**.
- Removed unnecessary columns:
  - Customer Email
  - Customer Password
  - Order Zipcode
- Removed duplicate records from all dimension tables.
- Standardized the dataset before modeling.

### Dimension Tables Created

The following dimension tables were created by duplicating the Fact Table and selecting only the required columns:

- Dim_Customer
- Dim_Product
- Dim_Category
- Dim_Department
- Dim_Shipping
- Dim_Location
- Dim_Date

### Additional Transformations

- Generated Shipping_ID using an Index Column.
- Generated Location_ID using an Index Column.
- Merged Shipping and Location tables back into the Fact Table.
- Created a Date table using the DAX CALENDAR() function.
- Added Year, Month, Quarter, Week, Day, and Day Name columns in the Date table.

---

## Data Model Overview

The project follows a **Star Schema** for efficient reporting and analysis.

### Fact Table

**Fact_Order_SupplyChain**

Contains transactional data such as:

- Order ID
- Customer ID
- Product ID
- Shipping ID
- Location ID
- Sales
- Quantity
- Discount
- Profit
- Delivery Status
- Shipping Days

### Dimension Tables

- Dim_Customer
- Dim_Product
- Dim_Category
- Dim_Department
- Dim_Shipping
- Dim_Location
- Dim_Date

### Relationships

- One-to-Many relationship between Dimension tables and Fact Table.
- Active relationship between:
  - Dim_Date → Order Date
- Inactive relationship between:
  - Dim_Date → Shipping Date

This model improves query performance, reduces redundancy, and simplifies KPI calculations.

---

## Milestone 1 Deliverables

✔ Imported Supply Chain Dataset

✔ Cleaned and transformed the data

✔ Created Star Schema

✔ Built Fact and Dimension Tables

✔ Established Relationships

✔ Prepared KPI foundation for dashboard development

---

## Tools Used

- Microsoft Power BI Desktop
- Power Query Editor
- DAX (Data Analysis Expressions)
- DataCo Global Supply Chain Dataset
- GitHub (Project Version Control)

---

## Project Folder Structure

```
Milestone1/
│
├── SupplyChain_Milestone1.pbix
├── data/
│   └── SupplyChain.csv
├── screenshots/
│   └── Data_model.png
└── README.md
```

---

## Future Enhancements

- Inventory Turnover Dashboard
- Delivery Performance Dashboard
- Supplier Scorecards
- Transportation Cost Analysis
- Warehouse Efficiency Dashboard
- Executive KPI Dashboard
