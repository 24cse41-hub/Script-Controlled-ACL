# Script-Controlled-ACL
A Script-Controlled ACL restricts access to records by using a custom script. The script checks specific field values and user conditions before granting access. Users can access the record only when the ACL script evaluates to true.
## Project Overview
* **Objective:** Implements record-level data security in ServiceNow using a Script-Controlled Access Control List (ACL).
* **Core Rule:** Restricts standard users to interacting strictly with **EEE branch** records, while **Administrators** maintain unrestricted global access.

## Key Components

### 1. Data Structure
* **Custom Table:** Institution Details (`u_institution_details`).
* **Key Fields:** Student Roll Number, Student/Faculty Name (References), and Branch (Choices: ECE, EEE, CSE).

### 2. User & Role Management
* **Test Profile:** `EEE User` created for security context testing.
* **Custom Roles Assigned:**
  * `bb1`: Grants **Read** access.
  * `bb2`: Grants **Create** access.
  * `bb3`: Grants **Write** (Edit) access.
  * `bb4`: Grants **Delete** access.

### 3. Access Control Lists (ACLs)
* **Read ACL:** Uses a server-side advanced script combined with a data condition (`Branch is EEE`) to dynamically validate permissions.
* **Functional ACLs:** Separate configurations applied for **Create**, **Write**, and **Delete** operations tied directly to roles `bb2`, `bb3`, and `bb4`.

## Expected Outcomes
* **Role-Based Users:** Can view, create, modify, and delete data restricted to the EEE branch.
* **Standard Users:** Blocked from viewing or altering any table records if missing custom roles.
* **Admin Users:** Retain full administrative override to manage all data across all branches.

## Project Resources
* **Drive Link:** [https://drive.google.com/drive/folders/1E57r5MwQtXIG_y6E1GreGTEDaUg7U3Bc?usp=drive_link]
  



