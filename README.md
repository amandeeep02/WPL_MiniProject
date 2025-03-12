# Expense Tracker

## Schema

### *1. tbluser (Users Table)*  
Stores user information.  

| Column Name   | Data Type      | Constraints               | Description                 |
|--------------|---------------|---------------------------|-----------------------------|
| ID           | INT(10)        | PRIMARY KEY, AUTO_INCREMENT | Unique user ID             |
| FullName     | VARCHAR(150)   | NOT NULL                  | User's full name           |
| Email        | VARCHAR(200)   | UNIQUE, NOT NULL          | User's email address       |
| MobileNumber | BIGINT(10)     | NULLABLE                  | User's phone number        |
| Password     | VARCHAR(200)   | NOT NULL                  | Encrypted user password    |
| RegDate      | TIMESTAMP      | DEFAULT CURRENT_TIMESTAMP | Account creation date      |

---

### *2. tblexpense (Expenses Table)*  
Stores user expenses.  

| Column Name    | Data Type      | Constraints               | Description                      |
|---------------|---------------|---------------------------|----------------------------------|
| ID            | INT(10)        | PRIMARY KEY, AUTO_INCREMENT | Unique expense ID              |
| UserId        | INT(10)        | FOREIGN KEY (tbluser.ID)  | Associated user ID              |
| ExpenseDate   | DATE           | NULLABLE                   | Date of expense                 |
| ExpenseItem   | VARCHAR(200)   | NULLABLE                   | Name of expense item            |
| ExpenseCost   | VARCHAR(200)   | NULLABLE                   | Cost of the expense             |
| NoteDate      | TIMESTAMP      | DEFAULT CURRENT_TIMESTAMP | Timestamp of record entry       |

---

### *Indexes & Auto Increment*
- tbluser.ID and tblexpense.ID are *primary keys* with *auto-increment*.
- UserId in tblexpense is a *foreign key* referring to tbluser.ID.

## Figma Design:
https://www.figma.com/design/QW0LXiWrUuJPUkZxWpGE28/ExpenseTracker?node-id=0-1&p=f&t=lk36EAg22YSVPNhb-0
