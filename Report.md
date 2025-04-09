# Daily Expense Tracker - User Guide

## Project Overview
The Daily Expense Tracker is a web-based application that helps users track and manage their daily expenses. This comprehensive system allows users to record, categorize, and analyze their spending habits through an intuitive interface.

## Tech Stack

### Frontend
- **HTML5/CSS3**: For structure and styling
- **Bootstrap**: For responsive design and UI components
- **JavaScript**: For client-side validation and interactive elements
- **jQuery 1.11.1**: For DOM manipulation and AJAX functionality
- **Chart.js**: For data visualization and expense reports
- **EasyPieChart**: For dashboard visualizations
- **Bootstrap Datepicker**: For date selection interface

### Backend
- **PHP**: Primary server-side language
- **MySQL**: Database for storing user and expense information
- **XAMPP**: Local development environment (Apache, MySQL, PHP)

### Architecture
- **MVC-like pattern**: Separation of data, presentation, and logic
- **Session-based authentication**: For secure user management
- **Responsive design**: Mobile-friendly interface

## Database Structure

### Tables
1. **tbluser**
   - ID (Primary Key)
   - FullName
   - MobileNumber
   - Email
   - Password (md5 hashed)

2. **tblexpense**
   - ID (Primary Key)
   - UserId (Foreign Key)
   - ExpenseDate
   - ExpenseItem
   - ExpenseCost

## Getting Started

### System Requirements
- Web browser (Chrome, Firefox, Safari, Edge)
- XAMPP server installed
- Active internet connection

### Installation
1. Clone the repository to XAMPP's htdocs folder
2. Import the database file into MySQL
3. Access the application via `localhost/wpl-mini-project`

## User Flow

### 1. Authentication
#### Registration
1. Access the system through the main URL
2. Click "Register" button on the login page
3. Fill in the registration form with:
   - Full Name
   - Email address
   - Mobile number (10 digits)
   - Password
   - Password confirmation
4. Submit registration form
5. Receive confirmation message

#### Login
1. Enter registered email and password
2. Click "Login" button
3. System validates credentials and redirects to dashboard
4. "Forgot Password" option is available if needed

### 2. Dashboard
After successful login, users can view:
- Today's expenses summary
- Yesterday's expenses
- Last 7 days' expenses
- Last 30 days' expenses
- Current year expenses
- Total lifetime expenses

Each metric is displayed with an easy-to-read pie chart visualization.

### 3. Expense Management

#### Adding Expenses
1. Navigate to "Add Expense" from the sidebar
2. Enter:
   - Date of expense
   - Item description
   - Cost of item
3. Click "Add" to save the expense
4. Receive confirmation message

#### Managing Expenses
1. Navigate to "Manage Expense" from the sidebar
2. View all expenses in a tabular format:
   - Serial number
   - Expense item
   - Expense cost
   - Expense date
   - Delete option
3. Delete unwanted expenses

### 4. Expense Reports
Access different report types:
- **Daywise Expense Report**: Filter expenses by specific date range
- **Monthwise Expense Report**: View expenses grouped by month
- **Yearwise Expense Report**: View expenses grouped by year

### 5. User Profile
- View profile information
- Update personal details
- Change password
- Logout securely

## Security Features
- Password encryption using MD5 hashing
- Session management to prevent unauthorized access
- Input validation to prevent malicious data entry
- Error reporting and handling mechanisms

## Key Code Components

### Authentication System
```php
// User login verification
$query=mysqli_query($con,"select ID from tbluser where Email='$email' && Password='$password'");
$ret=mysqli_fetch_array($query);
if($ret>0){
  $_SESSION['detsuid']=$ret['ID'];
  header('location:dashboard.php');
}
```

### Expense Tracking
```php
// Adding new expense
$query=mysqli_query($con, "insert into tblexpense(UserId,ExpenseDate,ExpenseItem,ExpenseCost) 
                          value('$userid','$dateexpense','$item','$costitem')");
```

### Dashboard Analytics
```php
// Calculating today's expenses
$tdate=date('Y-m-d');
$query=mysqli_query($con,"select sum(ExpenseCost) as todaysexpense 
                          from tblexpense 
                          where (ExpenseDate)='$tdate' && (UserId='$userid');");
$result=mysqli_fetch_array($query);
$sum_today_expense=$result['todaysexpense'];
```

## Limitations and Future Enhancements
- Currently lacks expense categorization
- No export functionality for reports
- No multi-currency support
- Could implement budgeting features
- Could add data visualization improvements
- Mobile application potential

## Conclusion
The Daily Expense Tracker provides a comprehensive solution for personal finance management. Its intuitive interface, robust reporting features, and secure authentication system make it a valuable tool for users looking to gain control over their spending habits.

Similar code found with 1 license type

