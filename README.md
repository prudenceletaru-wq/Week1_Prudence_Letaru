
---

## Workbook Structure

The workbook `ShopSmart_Analysis.xlsx` contains the following sheets:

### Data Sheets (Cleaned)
| Sheet | Description |
|-------|-------------|
| `Customers` | Customer master data (5,000 records) |
| `Products` | Product catalog (500 records) |
| `Orders` | Sales transactions (50,000 records), enriched with Revenue, Customer_Name, Store_Name, Product_Name, Category, Brand, Selling_Price, Supplier_Name, State, Region, Gender, Customer_Segment, Month, Year |
| `Stores` | Store master data (25 records) |
| `Returns` | Return/refund records (2,500 records) |
| `Employees` | Employee master data |
| `Suppliers` | Supplier master data |
| `Inventory` | Inventory records with Stock_On_Hand and Reorder_Level |
| `Order_Items` | Line-item detail |
| `Data_Dictionary` | Column definitions and metadata (reference document) |

### Analysis Sheets
| Sheet | Purpose |
|-------|---------|
| `Part3_Formulas` | Part 3 — 13 KPI metrics (revenue, quantities, averages, counts, status breakdown) |
| `Part4_Lookups` | Part 4 — XLOOKUP demonstration |
| `Pivots` | Part 5 — 12 Pivot Tables |
| `Part6_Charts`, `Pivots2` | Part 6 — 6 charts |
| `Dashboard` | Part 7 — Executive Dashboard with KPI cards, 5 charts, 6 interactive slicers |
| `Part8_BusinessQuestions` | Part 8 — 10 business questions with answers |

---

## Data Cleaning Summary

- **Duplicates:** None found in any of the 9 data tables.
- **Missing values:** No blanks detected across any table.
- **Date formats:** All 6 date columns converted to real Date type via Power Query with **English (United States)** locale to correctly interpret MDY format.
- **Currency fields:** All monetary columns formatted as ₦ (Nigerian Naira), 2 decimal places.
- **Excel Tables:** All 9 source datasets converted to named Tables:
  - `ShopSmart_Orders`, `ALA_ShopSmart_Customers`, `ShopSmart_Products`, `ShopSmart_Stores__2`, `ShopSmart_Returns`, `ShopSmart_Employees`, `ALA_ShopSmart_Suppliers`, `ShopSmart_Inventory`, `ShopSmart_OrderItems`
- **Sheet names:** All worksheets renamed to match dataset names.

---

## Key Definitions

| Term | Definition |
|------|-----------|
| **Revenue** | `(Quantity × Unit_Price) − Discount` |
| **Sales Metrics** | Calculated on **Completed orders only** — Cancelled and Pending orders excluded |
| **Total Revenue** | ₦2,496,824,383 |
| **Completed Orders** | 16,529 |
| **Average Order Value** | ₦151,057.20 |
| **Return Rate** | 15.12% (2,500 returns ÷ 16,529 completed orders) |
| **Inventory Value** | ₦3,169,020,818 |

---

## Key Findings

1. **Beauty is the highest-revenue category** (₦580,991,275) but also the most-returned (614 returns, 24.6% of all returns).
2. **South region dominates** with ₦805,370,701 (32.3% of revenue); West lags at ₦389,023,533 (15.6%).
3. **December 2025** was the peak revenue month (₦224,707,991); February 2025 was the trough (₦189,830,041).
4. **ShopSmart Lagos** is the top-performing store (₦419,568,251); **ShopSmart Awka** has the lowest inventory (4,357 units).
5. **Inventory value (₦3.17B) exceeds annual revenue (₦2.50B)**.

---

## Assumptions

- Discount column is stored as a flat Naira amount, not a percentage.
- Returns are assumed to reference completed orders only.
- Supplier is linked to Products via Brand name (Products table has no Supplier_ID column).

---

## Tools Used

- **Microsoft Excel** (Power Query, Pivot Tables, XLOOKUP, Slicers, Charts)
- **Data Cleaning:** Power Query with locale-aware date parsing
- **Analysis:** Excel formulas (SUMIFS, COUNTIFS, MAXIFS, MINIFS, XLOOKUP)
- **Visualization:** PivotCharts, Dashboard with interactive slicers

---

## Limitations

- Products table lacks a Supplier_ID foreign key; supplier mapping is inferred from Brand name.
- Phone number formats in Customers and Suppliers are inconsistent.
- Gender values in Customers appear inconsistent with first names in several records (retained, flagged).
- Discount values (₦0–₦20) are implausibly small relative to product prices.

---

## Files Included

| File | Description |
|------|-------------|
| `ShopSmart_Analysis.xlsx` | Full analytical workbook (Parts 1–8) |
| `Part1_Data_Understanding.pdf` | One-page explanation of the data model, primary/foreign keys, and relationships (Part 1 deliverable) |
| `Executive_Dashboard.pdf` | PDF export of the Dashboard sheet |
| `Business_Report.pdf` | One-page business report (Part 9) |
| `README.md` | This file |

---

## How to Use the Workbook

1. Refer to `Part1_Data_Understanding.pdf` for the one-page explanation of the data model, keys, and relationships.
2. Open `ShopSmart_Analysis.xlsx` in Excel (2019 or later recommended).
2. Navigate to the `Dashboard` sheet for the executive summary.
3. Use the **6 slicers** (Year, Month, Region, Store, Category, Membership Level) to filter all charts interactively.
4. For detailed analysis, see the `Pivots`, `Part6_Charts`, and `Part3_Formulas` sheets.
5. Refer to `Business_Report.pdf` for narrative insights and recommendations.

---

**End of README**