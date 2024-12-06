# Data Modeling

Data modelling is an important step in Data migration

The process of designing a database schema is called d**ata modeling.**

what is a database schema?

A database schema is a visual representation of the way that the data is organised with in the database, A relational database.

### Start Schema

One fact table which is the Central table, is surrounded by one or more dimension table

In this **star schema:**

- The Order table is the central fact table
- Customer, Product, and Date are dimension tables
- The fact table connects to each dimension table, forming a star-like structure

### **Snowflake Schema**

Similar to star schema, but one dimension table can't be connected directly through the facts table but only through another dimension table

Here's an example of a snowflake schema for orders:

- Fact Table: Orders (containing order details and foreign keys)
- First-level Dimension Tables:
    - Customer (connected directly to Orders)
    - Product (connected directly to Orders)
- Second-level Dimension Tables:
    - City (connected to Customer)
    - Category (connected to Product)

In this snowflake schema:

- The Orders table is the central fact table
- Customer and Product are first-level dimension tables directly connected to Orders
- City is a second-level dimension table connected to the Customer
- Category is a second-level dimension table connected to Product

This structure "snowflakes" out from the central fact table, hence the name.

Steps to design a schema

- Select the Organizational process
- Identify the gran - the lowest level of data that can’t be split again
- Identify the dimensions
- Identify the facts