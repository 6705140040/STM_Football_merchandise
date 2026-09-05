# 🗄 Database Design – STM Football Merchandise Shop

## 1. ER Diagram Description
Entities: Customers, Products, Orders, OrderDetails, Inventory.  
Relationships:  
- One Customer → Many Orders.  
- One Order → Many OrderDetails.  
- One Product → Many OrderDetails.  
- One Product → Inventory.  

---

## 2. Tables

### Customers
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| customer_id   | INT         | Primary Key, Auto Increment |
| name          | VARCHAR(100)| NOT NULL                    |
| email         | VARCHAR(150)| UNIQUE, NOT NULL            |
| password_hash | VARCHAR(255)| NOT NULL                    |

---

### Products
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| product_id    | INT         | Primary Key, Auto Increment |
| name          | VARCHAR(100)| NOT NULL                    |
| category      | VARCHAR(50) | NOT NULL                    |
| price         | DECIMAL(10,2)| NOT NULL                   |
| stock_level   | INT         | NOT NULL                    |

---

### Orders
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| order_id      | INT         | Primary Key, Auto Increment |
| customer_id   | INT         | Foreign Key → Customers(customer_id) |
| order_date    | DATETIME    | NOT NULL                    |
| total_amount  | DECIMAL(10,2)| NOT NULL                   |

---

### OrderDetails
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| detail_id     | INT         | Primary Key, Auto Increment |
| order_id      | INT         | Foreign Key → Orders(order_id) |
| product_id    | INT         | Foreign Key → Products(product_id) |
| quantity      | INT         | NOT NULL                    |
| subtotal      | DECIMAL(10,2)| NOT NULL                   |

---

### Inventory
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| item_id       | INT         | Primary Key, Auto Increment |
| product_id    | INT         | Foreign Key → Products(product_id) |
| stock_level   | INT         | NOT NULL                    |
| restock_date  | DATETIME    |                             |

---

## 3. Keys and Relationships
- **Primary Keys:** customer_id, product_id, order_id, detail_id, item_id  
- **Foreign Keys:**  
  - Orders.customer_id → Customers.customer_id  
  - OrderDetails.order_id → Orders.order_id  
  - OrderDetails.product_id → Products.product_id  
  - Inventory.product_id → Products.product_id  

---

## 4. Notes
- Passwords must be stored as hashed values.  
- Cascading deletes should be considered: deleting an order removes its order details.  
- Indexes should be added on `email` (Customers) and `name` (Products) for faster queries.  

---

## 5. Approval
This database design serves as the foundation for implementation.  
Approved by: ______________________  
Date: ______________________
