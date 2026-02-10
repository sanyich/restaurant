# Restaurant Database Documentation

## Overview
This document provides comprehensive documentation about the database system used in the Restaurant application. It details the structure, tables, and usage instructions to help developers and users understand how to interact with the database.

## Database Structure
The database is designed to manage various aspects of a restaurant, including menu items, orders, customer information, and staff management.

### Tables

1. **Customers**  
   - **customer_id** (INT, Primary Key): Unique identifier for each customer  
   - **name** (VARCHAR): The name of the customer  
   - **email** (VARCHAR): The email address of the customer  
   - **phone** (VARCHAR): The phone number of the customer  
   - **created_at** (DATETIME): The timestamp when the customer record was created  

2. **Menu_Items**  
   - **item_id** (INT, Primary Key): Unique identifier for each menu item  
   - **name** (VARCHAR): The name of the menu item  
   - **description** (TEXT): A brief description of the menu item  
   - **price** (DECIMAL): The price of the menu item  
   - **available** (BOOLEAN): Availability status of the item  

3. **Orders**  
   - **order_id** (INT, Primary Key): Unique identifier for each order  
   - **customer_id** (INT, Foreign Key): Identifier for the customer who made the order  
   - **ordered_at** (DATETIME): The timestamp of when the order was placed  
   - **total_amount** (DECIMAL): Total amount for the order  

4. **Order_Items**  
   - **order_item_id** (INT, Primary Key): Unique identifier for each order item  
   - **order_id** (INT, Foreign Key): Identifier for the order  
   - **item_id** (INT, Foreign Key): Identifier for the menu item  
   - **quantity** (INT): Quantity of the item ordered  

5. **Staff**  
   - **staff_id** (INT, Primary Key): Unique identifier for each staff member  
   - **name** (VARCHAR): The name of the staff member  
   - **position** (VARCHAR): The position or role of the staff member  
   - **hired_at** (DATETIME): The date and time the staff member was hired  

## Usage Instructions

### Database Connection
- Ensure that you have the appropriate database drivers installed.
- Configure the database connection parameters (host, username, password, database name) in the application configuration file.

### Common Queries
- To retrieve all menu items:  
  ```sql  
  SELECT * FROM Menu_Items;  
  ```  
- To place an order:  
  ```sql  
  INSERT INTO Orders (customer_id, ordered_at, total_amount) VALUES (?, ?, ?);  
  ```  
- To add items to an order:  
  ```sql  
  INSERT INTO Order_Items (order_id, item_id, quantity) VALUES (?, ?, ?);  
  ```  

### Conclusion
This documentation is meant to serve as a guide for interacting with the Restaurant database. Please refer to the individual table definitions for specific field constraints and relationships. For further details, contact the database administrator.
