# Ecommerce_marker_BI_Report
This dashboard presents critical metrics related to the e-commerce market. The data was sourced from Maven Analytics and used to create a visualization for an imaginary e-commerce platform called Maven Market.

Executive Dashboard Key features:

    Total Performance Metrics: Displays Total Profit ($1.05M), Transactions (270K), Quantity Sold (833K), and a low Return Rate (0.99%).
    Revenue Trend: A line graph shows revenue growth from January 1997 to July 1999, with current Monthly Revenue at $120.16K, a 5.68% increase.
    Top Sellers: Highlights “Hermanos” as the leading brand and “Tall Tale Fresh Lime…” as the top-selling product.
    Profit and Returns: Identifies “Hermanos Green Pepper” as the most profitable and “Dollar Monthly Sports…” as the most returned product.
    
Product details page key features: This page provides a detailed breakdown of product performance against business targets, aiding in strategic decision-making.

    Product Selection: Features a dropdown menu to choose products, including options like AD Rony Sunglasses and American Chicken Hot Dogs.
    Performance Targets: Shows bar graphs comparing Monthly Orders, Profit, and Revenue against set targets.
    Weekly Analysis: Presents line graphs for Weekly Profit, with values ranging up to $30K, and Weekly Returns, indicating a smoother trend.
    This page provides a detailed breakdown of product performance against business targets, aiding in strategic decision-making.

Customer Detail page key features: This dashboard page helps in understanding customer demographics and their contribution to revenue.

    Unique Customers: Tracks a total of 10.28K unique customers.
    Membership Distribution: Breakdown of orders by membership type, with Bronze being the most common at 56.1%.
    Occupation Segmentation: Orders categorized by customer occupation, with Professional at 32.6% being the highest.
    Revenue Trends: A graph showing the Average Revenue per Customer increasing over time from Jan '97 to Oct '98.
    Customer Insights: A list of the Top 100 Customers by revenue and a bar chart of Total Customers by Country, with the USA leading.

DAX queries used in creating Measures:

    Total Revenue = SUMX(Transaction_data, Transaction_data[quantity] * RELATED(Products[product_retail_price]))
    Weekend_transactions = CALCULATE([Total Transactions], 'Calendar'[Weekend] = "Y")
    YTD Revenue = CALCULATE([Total Revenue], DATESYTD('Calendar'[date]))
    Total Cost = SUMX(Transaction_data, Transaction_data[quantity] * RELATED(Products[product_cost]))
    Last Month Transactions = CALCULATE([Total Transactions], DATEADD('Calendar'[date],-1,MONTH))
    Last Month Profit = CALCULATE([Total Profit], DATEADD('Calendar'[date],-1,MONTH))
    60-Day Revenue = CALCULATE([Total Revenue], DATESINPERIOD('Calendar'[date],MAX('Calendar'[date]),-60,DAY))
    
