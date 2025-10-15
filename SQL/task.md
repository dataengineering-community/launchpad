# LaunchMart Loyalty Analytics
## Business Scenario:
LaunchMart is a growing African e-commerce company that recently launched a loyalty program to increase customer retention. Customers earn points when they place orders and extra bonus points during promotions. The Data Team has been asked to analyze customer behavior, revenue performance, and loyalty engagement.

You are hired as a Data Engineer to write SQL queries that help the business team understand customer behavior.

## Questions
1. Count the total number of customers who joined in 2023.
2. For each customer return customer_id, full_name, total_revenue (sum of total_amount from orders). Sort descending.
3. Return the top 5 customers by total_revenue with their rank.
4. Produce a table with year, month, monthly_revenue for all months in 2023 ordered chronologically.
5. Find customers with no orders in the last 60 days relative to 2023-12-31 (i.e., consider last active date up to 2023-12-31). Return customer_id, full_name, last_order_date.
6. Calculate average order value (AOV) for each customer: return customer_id, full_name, aov (average total_amount of their orders). Exclude customers with no orders.
7. For all customers who have at least one order, compute customer_id, full_name, total_revenue, spend_rank where spend_rank is a dense rank, highest spender = rank 1.
8. List customers who placed more than 1 order and show customer_id, full_name, order_count, first_order_date, last_order_date.
9. Compute total loyalty points per customer. Include customers with 0 points.
10. Assign loyalty tiers based on total points:
    - Bronze: < 100
    - Silver: 100–499
    - Gold: >= 500
    
    Output: tier, tier_count, tier_total_points
11. Identify customers who spent more than ₦50,000 in total but have less than 200 loyalty points. Return customer_id, full_name, total_spend, total_points.
12. Flag customers as churn_risk if they have no orders in the last 90 days (relative to 2023-12-31) AND are in the Bronze tier. Return customer_id, full_name, last_order_date, total_points.

## Rules:
- Use readable SQL formatting and comments.
- Prefer CTEs for multi-step logic.