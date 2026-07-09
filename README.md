# Sales Summary using SQL and Python

**Internship Task 7** — Get a basic sales summary from a database using Python, SQL, pandas, and matplotlib.

## Objective

Use SQL inside Python to pull simple sales insights (total quantity sold, total revenue per product), and visualize the results using a basic bar chart.

## Tools Used

- Python 3
- MySQL (database)
- `mysql-connector-python` (Python ↔ MySQL connection)
- `pandas` (loading SQL results into DataFrames)
- `matplotlib` (visualization)
- Google Colab (development environment)

## Dataset

A single `sales` table inside a `sales_db` database, with the following schema:

| Column     | Type          | Description                  |
|------------|---------------|-------------------------------|
| id         | INT (PK, AI)  | Unique row identifier         |
| product    | VARCHAR(50)   | Product name                  |
| quantity   | INT           | Units sold                    |
| price      | DECIMAL(10,2) | Price per unit                |
| sale_date  | DATE          | Date of sale                  |

Sample data (10 rows) was manually inserted using SQL `INSERT` statements, covering four products: Widget, Gadget, Gizmo, and Doohickey.

## What the Script Does

1. Connects to a MySQL database using `mysql-connector-python`
2. Creates the `sales_db` database and `sales` table (if they don't already exist)
3. Inserts sample sales records
4. Runs two SQL queries:
   - **Per-product summary**: total quantity sold and total revenue, grouped by product
   - **Overall totals**: total units sold and total revenue across all sales
5. Loads both query results into pandas DataFrames
6. Prints a readable summary to the console
7. Plots total revenue per product as a bar chart and saves it as `sales_chart.png`

## Sample Output

```
=== Sales Summary by Product ===
    product  total_qty  revenue
0    Gadget         15    187.5
1     Gizmo          9    180.0
2 Doohickey         21    168.0
3    Widget         21    105.0

=== Overall Totals ===
Total units sold: 66
Total revenue: $640.50
```

## How to Run

1. Install dependencies:
   ```bash
   pip install mysql-connector-python pandas matplotlib
   ```
2. Make sure a MySQL server is running and accessible.
3. Update the connection credentials (`host`, `user`, `password`) in the script to match your setup.
4. Run the script or notebook — it will create the database/table, insert sample data, print the summary, and save the chart.

## What I Learned

- How to connect Python to a MySQL database using `mysql-connector-python`
- Writing basic SQL: `CREATE TABLE`, `INSERT`, and aggregate queries with `GROUP BY`, `SUM()`
- Loading SQL query results directly into pandas DataFrames with `pd.read_sql_query`
- Creating a simple, readable data visualization with matplotlib
- Debugging real-world connection issues (authentication, service management) when setting up a database in a cloud environment like Google Colab
