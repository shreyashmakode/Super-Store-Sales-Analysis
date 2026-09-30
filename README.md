# Superstore Sales & Profit Dashboard (Excel)

An interactive-style, one-page **Excel dashboard** built from a 150-order Superstore sales dataset (India regions, 2025). It answers: *what sells, who buys, where is the profit made, and how do customers pay?*

![Dashboard preview](images/dashboard_preview.png)

## Tools & Skills
- **Microsoft Excel:** PivotTables, formulas (`SUMIFS`, `COUNTIFS`, `INDEX/MATCH`, `LARGE`), charts, conditional formatting
- **Data analysis:** KPI design, ranking, category / region / customer analysis
- **Dashboard design:** KPI cards, consistent colour palette, grid layout

## Dataset
`data/superstore_sales.csv`: 150 orders, 1 Jan 2025 to 30 Dec 2025, no missing values.

| Column | Description |
|---|---|
| Order_ID, Order_Date | Order identifier and date |
| Customer_ID, Customer_Name, Segment | Customer details (Consumer / Corporate / Home Office) |
| Region, State, City | Location (North, South, East, West) |
| Category, Sub_Category, Product_Name | Product hierarchy |
| Sales, Quantity, Discount, Profit | Order value (₹), units, discount rate, profit (₹) |
| Payment_Mode | Debit Card, Net Banking, Cash, Credit Card, UPI |

## Dashboard contents
| Visual | Purpose |
|---|---|
| KPI cards | Total Sales, Total Profit, Top Customer, Profit Margin |
| Sales & Profit by Category | Compare revenue vs profit per category |
| Category-wise Profit | Where profit really comes from |
| Product-wise Sales | All 17 products, ranked |
| Top 10 Customers by Sales | Key accounts, ranked |
| Payment Mode | Share of orders by payment method |
| Region + State-wise Profit | Ranked table with colour scale |

## Key metrics
| Metric | Value |
|---|---|
| Total Sales | ₹8,856,641 |
| Total Profit | ₹1,206,686 |
| Profit Margin | 13.6% |
| Top Customer | Kavya Deshmukh (₹1,394,190) |

## Key insights
1. **Technology drives the business.** It brings in 93% of sales and 94% of profit, even though it has only 64 of the 150 orders.
2. **Four products make up 92% of sales.** HP Pavilion Laptop (35%), iPhone 15 (23%), Samsung Galaxy S24 (19%) and Dell Inspiron (14%). Sales are heavily dependent on a few high-value products.
3. **Office Supplies has the best margin (18.3%) but the smallest sales.** It contributes only about 1% of revenue, so its profit (₹17K) is minor. Furniture has the lowest margin (10.4%).
4. **Customer concentration is high.** The top 3 customers account for 42% of sales and the top 10 for 97% (the dataset has only 12 customers).
5. **Profit is spread across West and East.** West Bengal, Gujarat and Maharashtra together give 38% of profit. North has the smallest profit but the best margin (16.4%), while East has the lowest (12.5%).
6. **Discounts appear to hurt margin.** Orders with 0-5% discount earn about a 17% margin, while orders with 10% or more fall to about 10-13%.
7. **Debit Card is the most used payment mode (25% of orders)**, followed by Net Banking (21%). UPI is the least used (16%).

> Insights are based on a small sample (150 orders), so treat them as indicative rather than conclusive.

## Repository structure
```
superstore-sales-dashboard-excel/
├── README.md
├── LICENSE
├── .gitignore
├── data/
│   └── superstore_sales.csv                  # raw dataset
├── excel/
│   ├── Superstore_Simple_Dashboard.xlsx      # final dashboard (formula-driven)
│   └── Superstore_Pivot_Analysis.xlsx        # original PivotTable analysis
└── images/
    └── dashboard_preview.png
```

## How the dashboard is built
`Superstore_Simple_Dashboard.xlsx` has three sheets:
1. **Dashboard:** the one-page report that reads from the Calc sheet.
2. **Calc:** summary tables built with `SUMIFS` / `COUNTIFS`, plus dynamic rankings using `LARGE` + `INDEX/MATCH` (so the product, customer and state lists re-sort themselves when data changes).
3. **Superstore Sales:** the raw data.

`Superstore_Pivot_Analysis.xlsx` holds the original PivotTable work the dashboard is based on. Dashboard totals match these pivots exactly.

## How to use
1. Download or clone the repo.
2. Open `excel/Superstore_Simple_Dashboard.xlsx` in Excel.
3. To use new data, paste it into the **Superstore Sales** sheet (same 16 columns). Formulas read up to row 2000. If new products, customers, states or payment modes appear, add them to the matching lists on the **Calc** sheet.

## Author
**Shreyash Makode** — Mechanical Engineering graduate moving into data analytics.
Skills: Excel, SQL, Power BI, Python (NumPy, Pandas).
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/)  <!-- replace with your profile links -->

## License
Released under the [MIT License](LICENSE).
