# Daily Expense Tracker - User Guide

## Overview
The **Daily Expense Tracker** is a web application that helps users track and manage their daily expenses. This guide explains how to use the system and navigate through its features.

## Getting Started
### System Requirements
- Web browser (Chrome, Firefox, Safari, Edge)
- XAMPP server installed
- Active internet connection

### Initial Setup
1. Ensure XAMPP is running (Apache and MySQL services)
2. Access the application via `localhost/wpl-mini-project`

## User Flow
### 1. Authentication
#### Registration
- Click **"Register"** on the login page
- Fill in required details:
  - Full Name
  - Email address
  - Mobile number (10 digits)
  - Password
  - Repeat password
- Submit the registration form

#### Login
- Enter registered email and password
- Click **"Login"**
- Use **"Forgot Password"** if needed

### 2. Dashboard Navigation
After login, users can view:
- **Today's expenses**
- **Yesterday's expenses**
- **Last 7 days' expenses**
- **Last 30 days' expenses**
- **Current year expenses**
- **Total expenses**

### 3. Managing Expenses
#### Adding Expenses
- Navigate to **"Add Expense"**
- Enter expense details:
  - Date of expense
  - Item description
  - Cost of item
- Click **"Add"** to save

#### Viewing Expenses
- Go to **"Manage Expense"**
- View the list of all expenses with:
  - Serial number
  - Expense item
  - Cost
  - Date
  - Delete option

#### Expense Reports
Access different report views:
- **Daywise expenses**
- **Monthwise expenses**
- **Yearwise expenses**

### 4. Profile Management
- View profile details
- Update personal information
- Change password
- Logout

## Key Features
### Dashboard Statistics
- **Today's Expense**
- **Yesterday's Expense**
- **Weekly Expense (Last 7 days)**
- **Monthly Expense (Last 30 days)**
- **Yearly Expense**
- **Total Expenses**

### Security Features
- Password encryption
- Session management
- Input validation
- Secure authentication

## Navigation Structure
```
├── Dashboard
├── Expenses
│   ├── Add Expense
│   └── Manage Expense
├── Reports
│   ├── Daywise
│   ├── Monthwise
│   └── Yearwise
└── Profile
    ├── View Profile
    ├── Change Password
    └── Logout
```

**Note:** Keep your login credentials secure and remember to log out after each session.

