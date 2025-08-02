# Classic Models Power BI Dashboard

This Power BI report delivers a detailed analysis of the **Classic Models** sales dataset. It highlights product performance, revenue trends, and customer ordering behavior through a range of interactive visualizations.

---

## 📁 Files Included

- `classicModels.pbix` — Main Power BI report file  
- `README.md` — Project overview and report details

---------------------------------------

## 📊 Visualizations and Report Features

### 🥧 Pie Chart: Sales Distribution by Product Line
- **Legend**: Product Line  
- **Values**: Sum of Sales  
- **Tooltips**: Linked to a visual showing the **Top 5 Products** by sales

### 📊 Clustered Column Chart: Total Quantity Ordered
- **X-Axis**: Order Year  
- **Y-Axis**: Sum of Quantity Ordered  
- Displays year-over-year quantity trends

---------------------------------------

## Top Selling Product (by quantity)

DAX
MostOrderedProduct = 
SELECTCOLUMNS(
    TOPN(
        1,
        SUMMARIZE(
            products,
            products[productName],
            "TotalOrdered", SUM(order_details[quantityOrdered])
        ),
        [TotalOrdered], DESC
    ),
    "MostOrderedProduct", products[productName]
)

---------------------------------------

## Total Profit Margin
Calculated using sales and cost fields

---------------------------------------

## Profit Margin %
Shows profitability as a percentage

---------------------------------------

## 📊 Bar Charts
Top 10 Selling Products — Based on total quantity or revenue

Bottom 10 Selling Products — Highlights underperforming products

---------------------------------------

## 📄 Additional Report Pages
Sum of Product Line and Product Name
Detailed view showing total sales grouped by product line and individual product name
Decomposition Tree: Sum of Quantity Ordered
Enables drill-down analysis across multiple dimensions

---------------------------------------

## 📦 Dataset Information
This report uses the Classic Models sample database, which includes:
Products and Product Lines
Orders and Order Details
Customers, Employees, and Offices

---------------------------------------

## 💻 How to View the Report
Download or clone the repository

Open classicModels.pbix using Power BI Desktop

Interact with visuals, filters, and drilldowns for insights
