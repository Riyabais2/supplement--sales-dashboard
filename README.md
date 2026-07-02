# 💊 Supplement Sales Analysis | Power BI Dashboard

An interactive Power BI dashboard analyzing supplement sales performance across **Amazon, Walmart, and iHerb**, covering revenue, units sold/returned, and geographic performance across Canada, the UK, and the USA.

![Dashboard Overview](assets/dashboard-overview.png)

---

## 📊 Overview

This project explores supplement sales data across three major retail platforms to uncover revenue trends, product performance, and return patterns. The dashboard is fully interactive, allowing users to filter by **Category, Platform, Product Name, and Location**.

## 🔑 Key Metrics

| Metric | Value |
|---|---|
| Total Revenue | **$22.91M** |
| Average Price | **$34.78** |
| Units Sold | **658K** |
| Units Returned | **7K** |
| Return Rate | **1.02%** |

## 📈 Insights

- **Platform performance is well balanced**: iHerb (34.28%), Amazon (33.47%), and Walmart (32.25%) each contribute roughly a third of total revenue, with no single platform dominating.
- **Product mix spans 16+ categories**, including Biotin, Zinc, Pre-Workout, BCAA, Fish Oil, Green Tea, Collagen, Creatine, Iron Supplements, Whey Protein, Vitamins, Electrolytes, Ashwagandha, Melatonin, Multivitamins, and Magnesium.
- **Return rate is low (1.02%)**, suggesting strong product-market fit and customer satisfaction across the catalog.
- **Geographic reach** spans Canada, the UK, and the USA, with revenue broken down by both location and product for cross-market comparison.

## 🛠️ Tools & Technologies

- **Power BI Desktop** — data modeling, DAX measures, and dashboard design
- **Power Query** — data cleaning and transformation
- Data visuals used: KPI cards, bar chart, donut chart, map visual, and Sankey (ribbon) flow chart

## 📁 Repository Structure

```
supplement-sales-dashboard/
│
├── assets/
│   └── dashboard-overview.png     # Dashboard screenshot
├── data/
│   └── supplement_sales.csv       # (optional) source dataset
├── supplement_sales_dashboard.pbix   # Power BI file
└── README.md
```

## 🚀 How to View

Since Power BI (`.pbix`) files can't be rendered directly on GitHub:

1. **Download** `supplement_sales_dashboard.pbix` from this repo.
2. Open it in [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop) (free).
3. Alternatively, view the static screenshot above, or publish it to [Power BI Service](https://app.powerbi.com) and paste a shareable link here:

   > 🔗 **Live Dashboard:** *[add your published Power BI link here]*

## 📌 Dashboard Features

- **Dynamic slicers** for Category, Platform, Product Name, and Location
- **Revenue by Product** bar chart to identify top and bottom performers
- **Revenue by Platform** donut chart for channel comparison
- **Revenue by Location** map visual for geographic distribution
- **Revenue flow by Location and Product** using a Sankey-style ribbon chart

## 👤 Author

**[Your Name]**
📧 [your.email@example.com] | 🔗 [LinkedIn](https://linkedin.com/in/yourprofile) | 💻 [Portfolio](https://yourportfolio.com)

## 📄 License

This project is available under the [MIT License](LICENSE).
