# ✈️ Tourism Management System

A Mini Project developed as part of the V Semester B.E. (Computer Science & Engineering) requirement for the "DBMS LABORATORY WITH MINI PROJECT" course (18CSL58) at Sahyadri College of Engineering & Management (SCEM), Mangaluru, for the academic year 2021-22.

---

## 🎯 Project Overview

The **Tourism Management System** is a database application designed to simplify and manage the core operations of a travel agency. The system allows travel agents to efficiently manage customer details, booking procedures, tour packages, and employee records. The primary goal is to shift from manual paperwork to an organized, accessible, and easily maintainable digital database system, significantly reducing the customer's effort in arranging a tour.

### Key Advantages

---

## ⚙️ Features
- ✈️ User registration and login
- 🚌 Book, update, or cancel trips
- 📅 Manage routes and destinations
- 👨‍💼 Admin panel for managing travel data
- 🧾 View booking history and payment details
- 💾 Database operations via JDBC

---

## 🧰 Tech Stack

| Component | Technology Used |
|------------|----------------|
| Frontend | Java Swing / AWT |
| Backend | Java |
| Database | MySQL |
| Connectivity | JDBC |
| IDE | IntelliJ IDEA / Eclipse / NetBeans |
| Version Control | Git & GitHub |

---

## ✨ Key Features & Functionalities

The system provides a comprehensive interface for the **Travel Agent/Administrator** to manage the agency's data.

### Core Modules

* **Agent/Administrator Login:** Secure access point for travel agents.
* **Travel Agent Management:** Display, Insert, Update, and Delete agent details (ID, Name, Username, Password).
* **Customer Management:** Display, Insert, Update, and Delete customer details (ID, Name, Phone, Aadhar No.).
* **Booking Management:** Manage booking records including `booking_id`, `booking_date`, and links to customer and package IDs.
* **Package Management:** Maintain details of all available tour packages (Name, Destination, Price, No. of Days, Vehicle Type).
* **Employee Management:** Track all employees working for the travel agency, including their roles.

### Advanced Database Features

* **Triggers:** Implemented for data validation:
    * Ensuring **Aadhar Number** is exactly 12 digits.
    * Preventing duplicate **Phone Numbers** for different customers.
* **Stored Procedure:** A procedure (`travel_agent1_count()`) is implemented to quickly retrieve the total count of travel agents.
* **Normalization:** All relational schemas (Tables: `TRAVEL_AGENT`, `CUSTOMER`, `BOOKING`, `PACKAGE`, `EMPLOYEE`) are normalized to **3rd Normal Form (3NF)** to ensure data integrity and minimize redundancy.

---

## 🏗️ Design & Structure

### Entity-Relationship (ER) Model

The database is built upon five strong entities:
1.  **TRAVEL\_AGENT**
2.  **CUSTOMER**
3.  **BOOKING**
4.  **PACKAGE**
5.  **EMPLOYEE**

Key relationships are established:
* **1:1 Binary Relationships:** `TRAVEL_AGENT` has `EMPLOYEE`, and `CUSTOMER` has `BOOKING`.
* **1:N Binary Relationships:** `TRAVEL_AGENT` books\_for `CUSTOMER`, `TRAVEL_AGENT` makes `BOOKING`, and `TRAVEL_AGENT` chooses `PACKAGE`.



### Relational Schema

The tables are designed as follows:
```
| Table Name | Attributes (PK - Primary Key, FK - Foreign Key) |
| :--- | :--- |
| **TRAVEL\_AGENT** | $\text{agent\_id (PK)}$, $\text{agent\_name}$, $\text{username}$, $\text{password}$ |
| **CUSTOMER** | $\text{cid (PK)}$, $\text{phone}$, $\text{name}$, $\text{aadhar\_no}$, $\text{agent\_id (FK)}$ |
| **BOOKING** | $\text{booking\_id (PK)}$, $\text{booking\_date}$, $\text{pid (FK)}$, $\text{cid (FK)}$, $\text{agent\_id (FK)}$ |
| **PACKAGE** | $\text{package\_id (PK)}$, $\text{package\_name}$, $\text{package\_dest}$, $\text{package\_price}$, $\text{no\_of\_days}$, $\text{vehicle\_type}$, $\text{agent\_id (FK)}$ |
| **EMPLOYEE** | $\text{eid (PK)}$, $\text{name}$, $\text{role}$, $\text{agent\_id (FK)}$ |
```
---

## 🚀 Setup and Installation

### 1. Prerequisites

Ensure you have the following installed:
* **MySQL Workbench 8.0 CE**
* **Apache NetBeans IDE**
* **Java Development Kit (JDK)**

### 2. Database Setup (MySQL)

1.  Create a new database named `tourism` in MySQL.
2.  Execute the `CREATE TABLE` scripts for the five relations (`travel_agent`, `customer`, `booking`, `package`, `employee`) as detailed in the project report (Chapter 5.1).
3.  Implement the **Triggers** and **Stored Procedure** (Chapter 5.4) to ensure full functionality.

### 3. Application Setup (NetBeans)

1.  Open the project in **Apache NetBeans IDE**.
2.  Ensure the **JDBC Driver** is correctly configured in your NetBeans project libraries to connect to MySQL.
3.  Verify the database connection string in the Java code (Chapter 5.2) matches your local MySQL setup:
    ```java
    Connection con= DriverManager.getConnection("jdbc:mysql://localhost:3306/tourism","root","YOUR_PASSWORD");
    ```
    (Replace `"YOUR_PASSWORD"` with your MySQL root password).

### 4. Run the Application

* Run the main Java application file. The **Travel Agent/Administrator Login Page** will be the starting point.

---

## 👤 Developers

* **Akarsh C Shetty** (4SF19CS015)  
* **Sanjay Shetty** (4SF19CS141)  
