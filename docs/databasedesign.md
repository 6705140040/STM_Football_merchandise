# 🗄 Database Design – STM Internet Cafe Management System

## 1. ER Diagram Description
The system consists of four main entities: **Users**, **Sessions**, **Billing**, and **Inventory**.  
- A **User** can manage multiple **Sessions**.  
- Each **Session** generates a **Billing** record.  
- **Inventory** tracks café items sold during sessions.  

Relationships:  
- One-to-Many: User → Sessions  
- One-to-One: Session → Billing  
- One-to-Many: Inventory → Billing (items sold)

---

## 2. Tables and Columns

### 2.1 Users Table
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| user_id       | INT         | Primary Key, Auto Increment |
| name          | VARCHAR(100)| NOT NULL                    |
| email         | VARCHAR(150)| UNIQUE, NOT NULL            |
| password_hash | VARCHAR(255)| NOT NULL                    |
| role          | VARCHAR(50) | e.g., "Admin", "Staff"      |

---

### 2.2 Sessions Table
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| session_id    | INT         | Primary Key, Auto Increment |
| user_id       | INT         | Foreign Key → Users(user_id)|
| start_time    | DATETIME    | NOT NULL                    |
| end_time      | DATETIME    |                             |
| duration      | INT         | Calculated in minutes       |

---

### 2.3 Billing Table
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| bill_id       | INT         | Primary Key, Auto Increment |
| session_id    | INT         | Foreign Key → Sessions(session_id) |
| total_amount  | DECIMAL(10,2)| NOT NULL                   |
| discount      | DECIMAL(10,2)| DEFAULT 0                  |
| payment_date  | DATETIME    | NOT NULL                    |

---

### 2.4 Inventory Table
| Column Name   | Data Type   | Constraints                  |
|---------------|-------------|------------------------------|
| item_id       | INT         | Primary Key, Auto Increment |
| name          | VARCHAR(100)| NOT NULL                    |
| category      | VARCHAR(50) | e.g., "Snack", "Drink"      |
| price         | DECIMAL(10,2)| NOT NULL                   |
| stock_level   | INT         | NOT NULL                    |

---

## 3. Keys and Relationships
- **Primary Keys:**  
  - `user_id` in Users  
  - `session_id` in Sessions  
  - `bill_id` in Billing  
  - `item_id` in Inventory  

- **Foreign Keys:**  
  - `user_id` in Sessions → Users(user_id)  
  - `session_id` in Billing → Sessions(session_id)  

---

## 4. Notes
- Passwords must be stored as hashed values.  
- Cascading deletes should be considered: deleting a session removes its billing record.  
- Indexes should be added on `email` (Users) and `name` (Inventory) for faster queries.  

---

## 5. Approval
This database design serves as the foundation for implementation.  
Approved by: ______________________  
Date: ______________________
