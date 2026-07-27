# Multi-Domain SQL Database Portfolio

##  Overview
This repository showcases relational database schemas designed and implemented in **Microsoft SQL Server**. The database (`StudentDB`) encompasses three distinct business domains: Academic Operations, HR & Employee Management, and E-Commerce Order Processing.

---

## 🗄️ Domain Schemas

### 1. Academic & Student Management
Models student enrollment and academic department mappings.
* **`Student`**: Tracks student personal details, registration numbers, residence, and assigned department (`dept_ID`).
* **`Departmen`**: Stores academic department names and locations.

### 2. HR & Employee Management
Models organizational hierarchies, departments, and payroll structure.
* **`Department`**: Contains organizational department records and office locations.
* **`Employee`**: Tracks individual employees, salary details, and foreign key linkages to `Department`.
* **`Employees`**: Supplementary table storing employee demographics (Age, Department, Salary).

### 3. E-Commerce & Order Tracking
Models customer purchases and order management.
* **`Customer`**: Stores customer profiles and unique email credentials.
* **`Orders`**: Records transactional orders, amounts, purchase dates, and foreign key links to `Customer`.

---

## 🔒 Relational Integrity & Constraints
* **Primary Keys:** Enforced across all entities (`CustomerID`, `dept_ID`, `EmployeeID`, `OrderID`, `id`).
* **Foreign Keys:**
  * `Orders(CustomerID)` $\rightarrow$ `Customer(CustomerID)`
  * `Employee(dept_id)` $\rightarrow$ `Department(dept_ID)`
  * `Student(dept_ID)` $\rightarrow$ `Departmen(dept_ID)`
* **Uniqueness Constraints:** Guarantees unique values for customer emails and student registration numbers (`reg_nos`).

---

## 🛠️ How to Deploy & Use

1. Open **Microsoft SQL Server Management Studio (SSMS)**.
2. Open the `.sql` script file from this repository.
3. Click **Execute** (or press `F5`).
4. The script will automatically generate the `StudentDB` database along with all tables, constraints, and relational mappings.
