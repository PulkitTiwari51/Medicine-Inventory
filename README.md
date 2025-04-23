# 💊 Medicine Inventory Management System

A **Java-based desktop application** designed to manage the inventory of medicines. This system allows both **customers** and **sellers** to interact with a centralized **MySQL database** for ordering, stock updates, and transaction logging. Built with **Java Swing**, the app supports user authentication, role-based access, and real-time inventory control.

---

## 📚 Table of Contents

- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Database Schema](#database-schema)
- [Directory Structure](#directory-structure)
- [Getting Started](#getting-started)
- [Sample Use Cases](#sample-use-cases)
- [Future Improvements](#future-improvements)
- [Conclusion](#conclusion)

---

## 🔍 Overview

This project simulates a medicine inventory system supporting two roles:

- **Seller**: Add or update medicine stock.
- **Customer**: Browse and order medicines.

The system ensures all actions are logged and reflected in the backend database using **JDBC**.

---

## 🛠 Tech Stack

| Component   | Technology                      |
|-------------|----------------------------------|
| Frontend    | Java Swing (GUI)                |
| Backend     | Java (JDK 17+)                  |
| Database    | MySQL                           |
| Connectivity| JDBC (Java Database Connectivity) |
| IDE         | VS Code / IntelliJ              |

---

## ✨ Features

- 🧑‍⚕️ Role-based access: Customer & Seller
- 🔒 Secure Sign Up / Sign In / Forget Password
- 📦 Stock management for sellers
- 🛒 Order placement for customers
- 🔄 Real-time stock updates
- 📝 Transaction logs for every order or supply

---

## 🧬 Database Schema

- **Database Name**: `medicine_inventory`

### Tables:

1. **detail**
   - Stores user credentials and profile

   ```sql
   CREATE TABLE detail (
       name VARCHAR(100) NOT NULL,
       user_id VARCHAR(50) PRIMARY KEY,
       password VARCHAR(100) NOT NULL,
       role VARCHAR(20) NOT NULL,
       age VARCHAR(10) NOT NULL
   );

2. **stock**
   - Tracks medicine inventory per seller

   ```sql
   CREATE TABLE stock (
    user_id VARCHAR(50) NOT NULL,
    med_name VARCHAR(100) NOT NULL,
    quantity INT NOT NULL
);

3. **transaction**
   - Records all order transactions

   ```sql
   CREATE TABLE transaction (
    user_id VARCHAR(50) NOT NULL,
    med_name VARCHAR(100) NOT NULL,
    quantity INT NOT NULL
);

  ```dir
   ###📁 Directory Structure
    Project_Root/
   ├── lib/
   │   └── mysql-connector-java-x.x.x.jar
   ├── src/
   │   └── medicine/
   │       ├── customer.java
   │       ├── forget.java
   │       ├── seller.java
   │       ├── sign_in.java
   │       └── sign_up.java
```
###🚀 Getting Started
✅ Prerequisites
JDK 17 or higher

MySQL Server

MySQL JDBC Connector

###🧪 Sample Use Cases
✅ Successful Sign Up: "SIGNED UP SUCCESSFULLY"

❌ Invalid Username Format: "Username must be like Yash123..."

✅ Correct Login: Dashboard shown based on role

❌ Incorrect Login: "Invalid Username or Name."

➕ Seller Adds Stock: Stock & transaction updated

🛒 Customer Orders: Stock updated, confirmation shown

⚠️ Order > Stock: "Only X available. Please enter a valid quantity."

🔑 Forgot Password: Password retrieved if matched
---
##🧾 Conclusion
This project is a complete implementation of an inventory control system for medicine sellers and buyers. It demonstrates the use of Java, Swing GUI, MySQL, and JDBC in a practical desktop application.


