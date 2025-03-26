# Retail Management Database Schema

## Overview
This SQL schema defines a database for a retail management system. It includes tables to manage stores, employees, customers, products, inventory, orders, payments, promotions, and more. The schema uses PostgreSQL syntax and enforces data integrity through primary keys, foreign keys, and constraints.

## Table Descriptions
Below is a summary of each table and its purpose:

- **Store**: Represents physical store locations with details like address, email, and minimum stock levels.
- **Supplier**: Stores supplier information for product sourcing.
- **Customer**: Contains customer personal details such as name, gender, birth date, and email.
- **Storage**: Manages storage units within stores, including location and stock thresholds.
- **Employee**: Tracks employee details, roles (Manager, Seller, Stockkeeper), and hierarchical supervision.
- **Payment_Methods**: Lookup table for payment options (Cash, Credit, Debit, Online).
- **Categories**: Lookup table for product categories.
- **Users**: Manages user accounts linked to customers, including login credentials and roles.
- **Sessions**: Tracks user sessions with expiration times.
- **Addresses**: Stores customer shipping addresses with a default flag.
- **Product**: Contains product details like name, size, price, and supplier, with description and active status.
- **Store_Inventory**: Tracks product quantities in each store.
- **Reserved_Stock**: Manages reserved stock for orders with expiration timestamps.
- **Promotions**: Defines promotional offers with codes, discounts, and usage limits.
- **Customer_Order**: Records customer purchases, linking to employees, payment methods, and promotions.
- **Order_Details**: Details items in each order, including pricing and discounts.
- **Return**: Handles product returns with refund amounts and reasons.
- **Supply_Order**: Tracks orders placed with suppliers for restocking.
- **Price_History**: Logs historical price changes for products.
- **Cart**: Manages customer shopping carts.
- **Wishlist**: Stores customer wishlists for products.
- **Phone_Numbers_Employees**: Associates phone numbers with employees.
- **Phone_Numbers_Customers**: Associates phone numbers with customers.
- **Phone_Numbers_Supplier**: Associates phone numbers with suppliers.
- **Image**: Links product images to products via URLs.
- **Product_Categories**: Junction table linking products to categories.
- **Notification**: Sends messages to customers, stores, products, or employees.
- **Audit_Log**: Logs actions performed by users or employees for auditing.
- **Reviews**: Stores customer reviews and ratings for products.
- **Shipping**: Tracks shipping details for customer orders.

## Indexes
Indexes are included at the end of the schema to optimize query performance on frequently accessed columns, such as customer IDs in orders, product IDs in inventory, and user emails.

## Customizing IDs
By default, tables use `SERIAL` for auto-incrementing primary keys. If you prefer to manually assign IDs:
- Replace `SERIAL` with `INTEGER` (or another appropriate type) in the column definition.
- Remove the `SERIAL PRIMARY KEY` shorthand and explicitly define the column as `Column_Name INTEGER PRIMARY KEY`.
- Example:
  ```sql
  -- From:
  "Store_ID" SERIAL PRIMARY KEY
  -- To:
  "Store_ID" INTEGER PRIMARY KEY
