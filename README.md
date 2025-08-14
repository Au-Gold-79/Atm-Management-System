---
# 🏦 ATM Management System (Python + MySQL)

### A simple yet powerful command-line ATM simulator built with Python and MySQL.
### Perform secure banking operations like withdrawals, deposits, balance checks, and PIN updates — all while enforcing real-world rules for savings, credit, and current accounts.


---

## 🚀 Features

### 🔐 Secure Login

Account number & PIN verification before any operation.


### 💳 Multiple Account Types

Savings – Enforces minimum ₹5000 balance & ₹10,000 withdrawal limit.

Credit – Checks against available credit limit.

Current – Simple balance-based transactions.


### 💼 Banking Operations

Check account balance

Withdraw money

Deposit money

Update PIN

Update mobile number

View mini statement (last 10 transactions)


### 📝 Transaction Logging

Every deposit & withdrawal recorded with a unique transaction ID.




---

## 🛠 Tech Stack

Language: Python 3.x

Database: MySQL

Libraries:

mysql.connector – Database connectivity

random – Transaction ID generation




---

## 📂 Database Structure

atm_user Table

Column	Type	Description

accountnumber	INT	Unique account number
accountholder	VARCHAR	Account holder's name
accounttype	VARCHAR	Type of account (savings/credit/current)
balance	FLOAT	Current balance
pin	INT	3-digit security PIN
mobno	BIGINT	Mobile number
creditlimit	FLOAT	Credit limit (for credit accounts)


atm_transaction Table

Column	Type	Description

accountnumber	INT	Linked account number
type	VARCHAR	'Credit' or 'Debit'
amount	FLOAT	Transaction amount
t_id	BIGINT	Unique transaction ID



---

## ⚙️ Setup Instructions

1. Install Python & MySQL
Make sure Python 3.x and MySQL are installed on your system.


2. Install Required Python Modules

pip install mysql-connector-python


3. Create the MySQL Database

CREATE DATABASE atm;
USE atm;

CREATE TABLE atm_user (
    accountnumber INT PRIMARY KEY,
    accountholder VARCHAR(100),
    accounttype VARCHAR(20),
    balance FLOAT,
    pin INT,
    mobno BIGINT,
    creditlimit FLOAT
);

CREATE TABLE atm_transaction (
    accountnumber INT,
    type VARCHAR(10),
    amount FLOAT,
    t_id BIGINT
);


4. Add Test Data

INSERT INTO atm_user VALUES
(123456, 'John Doe', 'savings', 15000, 123, 9876543210, 0),
(234567, 'Jane Smith', 'credit', 5000, 456, 9876501234, 10000),
(345678, 'Mark Lee', 'current', 20000, 789, 9123456780, 0);


5. Update Database Credentials
In atm_management.py, edit the init_db() function:

def init_db():
    return my.connect(
        host="localhost",
        user="root",
        password="root",  # Change if different
        database="atm"
    )


6. Run the Program

python atm_management.py




---

## 🖥 Usage

Launch the program and enter your account number and PIN.

Choose from the menu to perform operations:

1: Check Balance

2: Withdraw Money

3: Deposit Money

4: Update PIN

5: Update Mobile Number

6: View Mini Statement

7: Exit




---

## 📌 Notes

Savings accounts must maintain a minimum ₹5000 balance.

Maximum withdrawal limit for savings accounts: ₹10,000 at a time.

Credit account withdrawals cannot exceed available credit limit.

PIN must be a 3-digit number.

Mobile numbers must be 10 digits.



---

## 📜 License

This project is open-source and available under the MIT License.


---
