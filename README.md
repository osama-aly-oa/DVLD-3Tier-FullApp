# 🚗 Driving License Management System (DVLD)

**A full-stack Windows Forms application built on .NET Framework and ADO.NET** for the **Driving & Vehicle License Department (DVLD)**.  
This system streamlines the issuance, renewal, replacement, and management of driver and vehicle licenses, with integrated eligibility checks, test scheduling, and centralized applicant records.

---

## 📋 Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Database Design](#database-design)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [Future Enhancements](#future-enhancements)
- [License](#license)

---

## 📝 Overview
The **DVLD** system is designed to automate and manage the complete lifecycle of driving and vehicle licenses.  
It supports:
- First-time license issuance
- Renewals and replacements
- International license management
- Test scheduling and results tracking
- Centralized applicant and user management
- Requests, fees, and fines handling

The application ensures compliance with eligibility rules such as **minimum age requirements**, **unique national ID verification**, and **test prerequisites**.

---

## ✨ Key Features

### License Services
- **Issuance**: First-time, renewal, replacement (lost/damaged), and international licenses.
- **Eligibility Checks**: Age, prior license ownership, and pending requests.
- **Test Management**: Vision, theory, and practical tests with scheduling, results, and retakes.
- **Fines & Penalties**: License suspension and release after fine payment.

### Applicant & User Management
- Centralized applicant records linked by **unique national ID**.
- CRUD operations for system users with role-based permissions.
- Prevents duplicate applicant entries.

### Requests & Payments
- Tracks all service requests with status (New, Cancelled, Completed).
- Calculates and records service fees.
- Links payments to requests and applicants.

---

## 🏗 Architecture
**3-Tier Architecture** for maintainability and scalability:
1. **Presentation Layer** – Windows Forms UI
2. **Business Logic Layer (BLL)** – Core rules, validations, and workflows
3. **Data Access Layer (DAL)** – ADO.NET-based SQL Server integration

---

## 🛠 Tech Stack
| Layer              | Technology |
|--------------------|------------|
| UI / Frontend      | Windows Forms (.NET Framework) |
| Business Logic     | C# |
| Data Access        | ADO.NET |
| Database           | SQL Server |
| Version Control    | Git / GitHub |

---

## 🗄 Database Design
Relational schema with key entities:
- **People** – Applicant details (National ID, name, DOB, contact info, photo)
- **Requests** – Service requests with type, status, and fees
- **Licenses** – License details, category, validity, and status
- **Tests** – Vision, theory, and practical test records
- **Payments** – Linked to requests and services
- **Users** – System accounts with roles and permissions

---

## ⚙ Installation & Setup

### Prerequisites
- Windows OS
- Visual Studio (with .NET Framework support)
- SQL Server (Express or higher)
- Git

### Steps
1. **Clone the repository**
   ```bash
   git clone https://github.com/osama-aly-oa/DVLD-3Tier-FullApp.git

2. **Open the solution in Visual Studio**  
   The solution contains:
   - `DVLD` – Windows Forms UI (startup project)  
   - `DVLD_Buisness` – Business Logic Layer (BLL)  
   - `DVLD_DataAccess` – Data Access Layer (DAL)  

3. **Restore NuGet packages**  
   - In Visual Studio, go to `Tools → NuGet Package Manager → Manage NuGet Packages for Solution` and restore any missing packages.

4. **Restore the database**
   - Open SQL Server Management Studio (SSMS).  
   - Right‑click **Databases** → **Restore Database**.  
   - Select **Device** and browse to the `.bak` file in DVLD_DB folder.  
   - Restore the database (e.g., name it `DVLD_DB`).

5. **Update the connection string**  
   - Open `App.config` in the Presentation Layer project.  
   - Update the `connectionString` to match your SQL Server instance and restored database name:

   ```xml
   <connectionStrings>
       <add name="DVLD_DB"
            connectionString="Data Source=YOUR_SERVER_NAME;Initial Catalog=DVLD;Integrated Security=True" 
            providerName="System.Data.SqlClient" />
   </connectionStrings>
  - OR use the original connection code
    
## 🚀 Usage

1. **Login** with valid system credentials.
2. **Manage Applicants** – Add or search by National ID.
3. **Create Requests** – Select service type, verify eligibility, and process payment.
4. **Schedule Tests** – Assign dates and record results.
5. **Issue Licenses** – Upon successful test completion and fee payment.
6. **Manage Users & People** – Create, add, edit, or delete accounts.


