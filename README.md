# Retail-Sales Analytics Dashboard
##  Overview

Retail companies generate large volumes of data across product categories, customer regions, and delivery methods. This dashboard showcases how data from a fictitious office supply store can be transformed into meaningful insights for business decision-making.

Key business questions answered:

✅ Which regions are the most profitable?
 
✅ What product categories have the highest return rates?
 
✅ How does shipping method affect profit and delivery volume?
 
✅ Are profits increasing over time across product categories?


 ##   Features

✅ Profit & Sales KPIs 

✅ Time Series Analysis (Sales vs PY) 

✅ Regional Sales Breakdown 

✅ Product Category Comparison 

✅ Ship Mode Impact  

✅ Pie & Bar Charts for quick segmentation 

✅ Interactive filtering via Power BI

### Dax Measures
Metrics

1. % Returned orders = 
VAR _total_orders = DISTINCTCOUNT(Orders[Order ID])
VAR _returned_orders =DISTINCTCOUNT(Returns[Order ID])
VAR _perc =
DIVIDE(
    _returned_orders,
    _total_orders)
RETURN
_perc

2. profit = SUM(Orders[Profit])

3. sales = SUM(Orders[Sales])

4. % Returned orders py = 
CALCULATE(
    [% Returned orders],
    SAMEPERIODLASTYEAR('date table'[Date])
)

5. profit py = 
CALCULATE(
    [profit],
    SAMEPERIODLASTYEAR('date table'[Date])
)

6. sales py = 
CALCULATE(
    [sales],
    SAMEPERIODLASTYEAR('date table'[Date])
)

7. vs PY - % returned orders = 
[% Returned orders] - [% Returned orders py]

8. vs PY - profit = 
DIVIDE(
    [profit] - [profit py],
    [profit py]
)

9. vs PY - Sales = 
DIVIDE(
    [sales] - [sales py],
    [sales py]
)

##  Dataset Info

- **Name**: Sample Superstore Dataset
  
- **Source**: Tableau public sample (adapted for Power BI)
  
- **Format**: CSV
   
- **Size**: ~10,000 rows
   
- **Fields**: Order Date, Region, Category, Sub-Category, Ship Mode, Sales, Profit, Quantity, etc.


  ## 🖼️ Visuals

![Superstore Sales Dashboard](Screenshot%202025-07-29%20160659.png)


## ⚙️ Tools Used

- 📊 Power BI (Data modeling + Visualization)
- 🐼 Excel/CSV (Raw data prep)
- 🧠 Data analysis using DAX



