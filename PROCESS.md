# 🛠️ Project Process — How This Dashboard Was Built

This document walks through the end-to-end process of building the Supplement Sales Analysis dashboard in Power BI, from raw data to the final interactive report.

---

## 1. Data Collection

- **Source:** [Supplement Sales dataset](https://www.kaggle.com/) on **Kaggle**
- **Format:** CSV file, imported directly into Power BI using `Get Data → Text/CSV`
- **Fields included:** Product Name, Category, Platform, Location, Units Sold, Units Returned, Revenue, Price, Date

> 📝 *Add the exact Kaggle dataset link here (right-click the dataset page → copy link) so anyone viewing the repo can find the original source.*

## 2. Data Cleaning & Preparation (Power Query)

Using Power BI's **Power Query Editor**, the following steps were applied to the Kaggle CSV:

1. **Imported** the dataset via `Get Data → Text/CSV`, which already included a `Platform` column distinguishing Amazon, Walmart, and iHerb records.
2. **Removed duplicates and blank rows** to ensure each record represents a unique transaction/line item.
3. **Checked and renamed columns** (e.g. `Location`, `Product Name`, `Category`, `Platform`) for consistency and readability.
4. **Fixed data types** — set `Revenue` and `Price` to Decimal, `Units Sold`/`Units Returned` to Whole Number, and `Date` to Date type.
5. **Handled missing values** — [describe: e.g. filled missing prices using average price per product, or removed incomplete rows].
6. **Standardized `Location` values** to ensure country names were consistent (e.g. "US" vs "USA" → "USA").

## 3. Data Modeling

- Built a simple **star schema**:
  - **Fact table:** Sales transactions (Revenue, Units Sold, Units Returned)
  - **Dimension tables:** Product, Platform, Location, Date
- Created relationships between the fact table and dimension tables using `Product Name`, `Platform`, and `Location` as keys.
- Built a **Date table** using DAX (`CALENDAR` or `CALENDARAUTO`) to enable time-based filtering, if applicable.

## 4. DAX Measures

Key measures created to power the KPI cards and visuals:

```dax
Total Revenue = SUM(Sales[Revenue])

Average Price = AVERAGE(Sales[Price])

Units Sold = SUM(Sales[Units Sold])

Units Returned = SUM(Sales[Units Returned])

Return % = DIVIDE([Units Returned], [Units Sold], 0)
```

## 5. Visualization Design

Each visual was chosen deliberately to answer a specific business question:

| Visual | Purpose |
|---|---|
| **KPI Cards** (Total Revenue, Avg Price, Units Sold, Units Returned, Return %) | Give an at-a-glance summary of overall performance |
| **Bar Chart — Revenue by Product Name** | Identify top and bottom-performing products |
| **Donut Chart — Revenue by Platform** | Compare channel contribution (Amazon vs Walmart vs iHerb) |
| **Map — Revenue by Location** | Show geographic distribution of sales |
| **Ribbon/Sankey — Revenue by Location & Product** | Reveal which products drive revenue in which markets |
| **Slicers** (Category, Platform, Product Name, Location) | Let users interactively filter the entire report |

Design choices:
- Used a consistent color palette to distinguish platforms across all visuals.
- Grouped KPI cards at the top for quick scanning before diving into detail.
- Positioned slicers on the right so they're accessible without disrupting the visual flow.

## 6. Testing & Validation

- Cross-checked KPI totals (Total Revenue, Units Sold) against the raw source data to confirm accuracy.
- Verified that slicer filters correctly cascade across all visuals.
- Checked for outliers/negative values (e.g. returns exceeding units sold) and corrected them in Power Query.

## 7. Publishing

- Published the report to **Power BI Service** (`Home → Publish` in Power BI Desktop).
- Generated a shareable/embed link via **Publish to Web** (or restricted sharing, depending on data sensitivity).
- Exported a static screenshot for the GitHub README, since `.pbix` files don't render natively on GitHub.

---

## 🔄 Possible Next Steps / Improvements

- Add a time-series trend view once historical/multi-month data is available.
- Incorporate profit margin (if cost data becomes available) alongside revenue.
- Add drill-through pages for per-product deep dives.

---

*Update the placeholder sections above ([in brackets]) with the specifics of your actual data source and cleaning steps before publishing.*
