# Hotel Management System - Relational Schema



This document represents the logical relational schema derived from the Entity-Relationship diagram.



---



## 1. Tables and Attributes



### **Type**

* `Type_Id` (PK)

* `Type_Name`



### **Hotel**

* `Hotel_Id` (PK)

* `Hotel_Name`

* `Type_Id` (FK) -> References **Type(Type_Id)**



### **Category**

* `Category_Id` (PK)

* `Category_Name`

* `Price`

* `Beds_numbers`



### **Room**

* `Room_Id` (PK)

* `Floor`

* `Hotel_Id` (FK) -> References **Hotel(Hotel_Id)**

* `Category_Id` (FK) -> References **Category(Category_Id)**



### **Employee**

* `Employee_Id` (PK)

* `Employee_Name`

* `Employee_Speciality`

* `Hotel_Id` (FK) -> References **Hotel(Hotel_Id)**

* `Manager_Id` (FK) -> References **Employee(Employee_Id)** *(Self-referencing for "leads" relationship)*



---



## 2. Relational Mapping Rules applied



1. **One-to-Many (1:N):** Migrated the Primary Key from the '1' side to the 'N' side as a Foreign Key.

   - *Example:* `Type_Id` moved to **Hotel**.

   - *Example:* `Hotel_Id` and `Category_Id` moved to **Room**.

2. **Recursive Relationship:** Handled the "leads" relationship on the **Employee** entity by adding a self-referencing Foreign Key (`Manager_Id`).
