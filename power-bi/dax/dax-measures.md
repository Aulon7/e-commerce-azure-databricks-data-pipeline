# DAX Measures for E-commerce Power BI Model

### Average Discount Percentage

- Calculates the average discount percentage applied across order items.

_**Average Discount Percentage = AVERAGE(fact_order_items[discount_pct])**_

### Number of Orders

- Groups transactions by customer, date, channel, and coupon to count the total number of distinct orders.

_**Number of Orders = COUNTROWS(SUMMARIZE('fact_order_items', 'fact_order_items'[customer_id], 'fact_order_items'[date_id], 'fact_order_items'[channel], 'fact_order_items'[coupon_code]))**_

### Total Quantity Sold

- Calculates the total sum of all units sold across all order items.

_**Total Quantity Sold = SUM('fact_order_items'[quantity])**_

### Total Tax Collected

- Calculates the total amount of tax collected from all transactions.

_**Total Tax Collected = SUM('fact_order_items'[tax_amount])**_

### Total Unique Customers

- Provides a count of distinct customers who have placed at least one order.

_**Total Unique Customers = DISTINCTCOUNT(fact_order_items[customer_id])**_

### Total Unique Products

- Provides a count of distinct product IDs sold within the specified period.

_**Total Unique Products = DISTINCTCOUNT(fact_order_items[product_id])**_