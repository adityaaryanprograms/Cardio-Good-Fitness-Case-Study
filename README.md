# Cardio Good Fitness Case Study

## Problem Statement
CardioGood Fitness is facing a challenge in understanding the distinct profiles of customers for its different treadmill products. The market research team at AdRight needs to determine if there are significant differences in customer characteristics across these product lines. To achieve this, we can perform a thorough descriptive analysis of data collected on various customer attributes from recent purchases of their products.

## Description
The dataset consists of 180 rows and 9 columns which detail different customer demographics. Several outliers discovered in 'Age', 'Education', 'Income' and 'Miles' columns were replaced with the lower and upper quartiles of the respective columns. The customer data was analyzed to shed light on patterns and insights that differentiate the customer base for each product.

## Outcome
Three different customer profiles were developed for each treadmill option on the basis of insights from the data to help DataCo tailor their marketing strategies and improve customer targeting.

## Key Skills Used
Python, NumPy, Pandas, Pre-processing, Variable Analysis, Transformation, Exploratory Data Analysis, Data Wrangling, Visualization, Analytical Skills



### Step 2: Create the Trigger

Now, create a trigger that will call the `update_total_amount` function before each insert on the `transactions` table.

```sql
CREATE TRIGGER total_amount_trigger
BEFORE INSERT ON transactions
FOR EACH ROW
EXECUTE FUNCTION update_total_amount();
```

This trigger setup ensures that every time a new transaction is added, the `update_total_amount` function is executed. This function then updates the `total_amount` column of the `transactions` table to reflect the sum of all existing transaction amounts, including the newly inserted transaction.

### Note:

- The `total_amount` column must exist in the `transactions` table. If it doesn't, you'll need to add it before creating the trigger and function.
- The trigger and function approach may not be the most efficient for large tables, as recalculating the sum with each insert could be costly. A better approach might involve using a separate summary table or leveraging materialized views, depending on your use case and database performance requirements.
- Ensure your database user has the necessary permissions to create functions and triggers.

Remember, the exact SQL syntax for creating functions, triggers, and updating tables might vary slightly depending on the specific SQL database system you're using (e.g., PostgreSQL, MySQL, SQL Server, etc.).
