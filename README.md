🍽️ Restaurant Orders Analysis with MySQL
This project explores customer behavior and menu performance using a relational database that includes order details and menu items. The objective is to provide insights into how well the new menu is being received and identify top-selling items.

#📁 Files Included

| File | Description |
|------|-------------|
| `create_restaurant_db.sql` | SQL script to create database and tables |
| `menu_items.csv` | List of items on the new menu |
| `order_details.csv` | Customer order data |
| `restaurant_db_data_dictionary.csv` | Schema/data dictionary reference |
| `sql 1.sql` | Exploration of `menu_items` table |
| `sql 2.sql` | Exploration of `order_details` table |
| `sql 3.sql` | Analysis combining both tables |

🎯 Project Goals

1. Explore the `menu_items` table 
   Understand what dishes are offered on the new menu.

2. Explore the `order_details` table
   Analyze what kind of order data has been collected (e.g., quantity, date, etc.).

3. Combine both tables
   Investigate how customers are responding to the new menu — e.g., which items are most/least ordered.

🛠️ Tools Used

- MySQL
- SQL (joins, aggregates, filtering)
- CSV data import
- DB Browser / MySQL Workbench


🔍 Sample SQL Query

```sql
View the details of the top 5 highest spend orders. What insights can you gather from the results?
SELECT order_id, category, COUNT(item_id) AS num_items
 FROM order_details od LEFT JOIN menu_items mi
	  ON od.item_id = mi.menu_item_id
WHERE order_id IN (440, 2075, 1957, 330, 2675)
GROUP BY order_id, category;
