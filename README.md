# Customer Shopping Behavior Analysis

## Project Overview

This project analyzes customer shopping patterns to provide actionable business insights. It explores relationships between demographics (age, gender), purchasing habits (categories, amount spent), and loyalty factors (subscription status, previous purchases).

## Files

1. `customersbehaviour1.sql`
   - Database schema and analytical SQL queries.
   - Table creation for customers (19 columns): `customer_id`, `age`, `purchase_amount`, `subscription_status`, `review_rating`, etc.
   - Data transformation: converts `previous_purchases` to integer and cleans payload.
   - Analytical queries:
     - Revenue by gender and age.
     - Discount usage vs average spend.
     - Top products by review rating and discount behavior.
     - Shipping and subscription spending comparisons.
     - Customer segmentation: New / Returning / Loyal.

2. `Customer Behaviour.pbix`
   - Power BI report with interactive dashboards.
   - Data model with relationships and DAX measures.
   - Visuals for segments, revenue KPIs, category leaders.
   - CY26SU02 theme + custom icon assets for consistency.

3. `data/` (if present)
   - Contains CSV exports and cleaned dataset files used for model building.

4. External resource:
   - Google Colab notebook: `Customer Behavior Notebook` (Python/Pandas preprocessing pipeline).
   - https://colab.research.google.com/drive/1MkhSkZ8bFgiP42uBXbsLBmow0Ol3aA1u

## Key Insights

- Revenue Contribution: male vs female and age group performance.
- Loyalty Trends: repeat buyers (more than 5 previous purchases) and subscription likelihood.
- Category Leaders: top 3 products per category.

## How to Use

### SQL

1. Update the `COPY` path in `customersbehaviour1.sql` to your local file location.
2. Connect to PostgreSQL:
   ```powershell
   psql -h localhost -U youruser -d yourdb
   ```
3. Run the script:
   ```sql
   \i 'C:\path\to\customersbehaviour1.sql'
   ```

### Power BI

1. Open `Customer Behaviour.pbix` in Power BI Desktop.
2. Refresh data sources if needed.
3. Explore slicers for demographics, product categories, shipping type, and loyalty segments.

### Data Preparation

- Refer to the Google Colab notebook for data cleaning and preprocessing steps.
- Use the cleaned CSV output as input to the SQL `COPY` command.

## Notes

- Ensure database user has permission to read CSV files in the filesystem.
- Adjust `SERIAL`/`IDENTITY` definitions and foreign keys if using non-PostgreSQL dialects.
