

**Title:** *Retail Sales Performance Analysis – Power BI Project*

---

 **Retail Sales Performance Analysis (Power BI Project)**

This project analyzes retail sales performance using an interactive Power BI dashboard.
The goal is to understand revenue trends, profitability, customer behavior, and product performance using a clean data model and clear visual insights.

 **Project Objectives**

The main objectives of this project were:

1. **Identify missing values and duplicates** in the Sales dataset and perform required cleaning.
2. **Perform univariate analysis** on Sales and Profit to understand distribution patterns.
3. **Analyze category-wise revenue & profit performance.**
4. **Compare regional sales performance** and identify high/low-performing areas.
5. **Create an efficient Star Schema model** using Sales, Customer, Product, and Date tables.
6. **Build DAX measures** for Total Sales, Total Profit, Profit Margin %, etc.
7. **Identify low-margin and low-performing products** for business decisions.
8. **Design a fully interactive dashboard** with multiple pages for analysis.
9. **Summarize business insights** and recommend product actions (promote/discontinue).


**Dataset Used**

The project uses 4 main tables:

* **Orders/Sales Table**
* **Customer/People Table**
* **Product Table**
* **Date Table (generated using DAX)**

 **Data Cleaning Steps**

Performed in Power Query:

* Checked for **missing values**, null entries, and replaced or removed them.
* Identified **duplicates** in keys like Order ID and removed them.
* Standardized:

  * Date formats
  * Product names
  * Region/Category fields
* Created a proper **Date Table** for time intelligence.
* Removed irrelevant columns to improve model performance.

**Data Model (Star Schema)**

**Fact Table:**

* `Orders`

**Dimension Tables:**

* `People/Customer`
* `Product`
* `Date`

**Relationships Created:**

* Orders[Customer_Name] → People[Person]
* Orders[Product] → Product[Product_Name]
* Orders[Order_Date] → Date[Date]

**Why Star Schema?**

* Faster performance
* Easier DAX writing
* Cleaner relationships
* Follows BI best practices

Dashboard Pages**

** Page 1 — Sales Overview**

* Total Sales
* Total Profit
* Sales Trend Over Time
* Category-Wise Revenue
* Top 10 Products
* Regional Sales Distribution

** Page 2 — Customer & Regional Analysis**

* Region-wise Total Sales
* Customer performance charts
* Highest buying customer segments
* Sales distribution by states/regions

 ** Page 3 — Return Analysis**

* Return quantity & rate
* Returned products
* Return trend
* Return percentage measure

** Page 4 — Product Profitability & Insights**

* Profit Margin %
* Most & least profitable products
* Profitability matrix (conditional formatting)
* Product trend over time
* Gauge Card showing goal achievement
* Final business recommendations


**Key DAX Measures Used**

```DAX
Total Sales = SUM(Orders[Sales])

Total Profit = SUM(Orders[Profit])

Profit Margin % = 
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)

Most Profitable Product =
CALCULATE(
    MAX(Orders[Profit]),
    ALL(Orders[Product])
)

Least Profitable Product =
CALCULATE(
    MIN(Orders[Profit]),
    ALL(Orders[Product])
)

Returned Qty = SUM(Returns[Return_Qty])
```

(Additional measures added for trends, goals, and insights)


 **Insights & Observations**

* Certain **product categories** contribute a major share of revenue and profit.
* Some **regions outperform others** in sales and profitability.
* A few products have **very low profit margins**, suggesting they might need promotion or discontinuation.
* Customer buying patterns show strong preference toward certain categories.
* Return rates for specific products indicate possible quality issues.

 **Recommendations**

* **Promote**: High-margin, high-demand products.
* **Discontinue/Review**: Low-margin or frequently-returned items.
* **Target marketing** in regions with lower sales performance.
* Improve **logistics** and **quality checks** for returned items.


 **Tools Used**

* **Power BI Desktop**
* Power Query
* DAX (Data Analysis Expressions)
* Data Modeling (Star Schema)

Final Deliverables

✔ Power BI Dashboard (PBIX file)
✔ Data Model
✔ DAX Measures
✔ Project Documentation
✔ GitHub Repository

Conclusion

This project successfully delivers a complete end-to-end retail sales analysis solution using Power BI.
It includes data cleaning, modeling, visualization, and final insights — following real industry BI standards.
# Retail-Sales-Performance
A dashboard which shows the retail sales analysis performance over the world
