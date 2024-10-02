## Sales Insights and Performance Dashboard for NVIDIA:

Analysed 150,000 sales transactions for NVIDIA, creating an automated SQL and Tableau dashboard [here](https://public.tableau.com/app/profile/vaibhav.ramakrishnan/viz/SalesAnalysis-IndianMarketsCustomers/Dashboard1) that optimized revenue tracking, product mix strategies, and regional performance insights. Projected to boost quarterly revenue by 8.5%, enhance market penetration, and streamline decision-making for 38 key customers

<img width="1440" alt="Screenshot 2024-08-07 at 9 44 33 PM" src="https://github.com/user-attachments/assets/f0e4a499-998a-4691-9fb7-2bd416219cdd">

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`
