# Hospital Management Database System

A comprehensive MySQL database solution designed for managing hospital operations, patient admissions, billing tracking, and medical staff data. This project demonstrates advanced SQL concepts including Schema Design, Views, Common Table Expressions (CTEs), Window Functions, and Stored Procedures.

## 📊 Database Schema Overview
The database consists of the following interconnected tables:
- **departments:** Tracks hospital departments and floor locations.
- **doctors:** Stores doctor profiles, specializations, and consultation fees.
- **patients:** Contains patient demographics and contact details.
- **admissions:** Records details of patient admissions, diagnoses, assigned doctors, and wards (including ICU).
- **billing:** Manages detailed financial data (room charges, doctor fees, lab, and medicine expenses) along with payment status.
- **feedback:** Stores patient ratings and comments regarding their treatment.

---

## 🚀 Advanced Features Implemented

### 1. Database View (`vw_admission_summary`)
A unified view that pulls complete insights for every admission, calculating the patient's exact age at admission and the total length of stay automatically.

### 2. Analytical Queries
- **Readmission Analysis (CTEs):** Identifies critical cases where a patient was readmitted to the hospital within 30 days of discharge.
- **Financial Analytics (Window Functions):** Calculates monthly revenue trends along with a running total to track hospital growth over time.

### 3. Automated Reporting Stored Procedure
Includes the `GenerateMonthlyReport(year, month)` stored procedure which generates a detailed executive summary for any specific month, including:
- Total admissions, total revenue, and average bill amount.
- Payment status breakdown (Paid vs. Pending amounts).
- Department-wise performance and revenue generation.
- Top performing doctors based on the volume of patients treated.

---

## 🛠️ How to Setup and Run

1. Make sure you have **MySQL Server** and **MySQL Workbench** (or any SQL client) installed.
2. Clone or download this repository.
3. Open the `hospital.sql` script in your SQL client.
4. Execute the entire script to create the database, tables, insert sample data, and compile the stored procedures.
5. To test the automated monthly reports, run the following commands in your SQL editor:
   ```sql
   CALL GenerateMonthlyReport(2023, 1); -- For January 2023 Report
   CALL GenerateMonthlyReport(2023, 5); -- For May 2023 Report
