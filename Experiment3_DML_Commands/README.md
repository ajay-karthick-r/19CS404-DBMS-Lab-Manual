# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
```--
Write a SQL statement to double the availability of the product with product_id 1.

products table

---------------
product_id
product_name
category_id
availability
```
```sql
update products set availability=availability*2 where product_id=1;
```

**Output:**
<img width="1213" height="241" alt="Screenshot 2026-08-30 182023" src="https://github.com/user-attachments/assets/aaeb8945-0b40-4ad0-a19c-6bd62b0cea70" />


**Question 2**
```---
Write a SQL statement to Change the supplier name to 'A1 Suppliers' where the supplier ID is 8 in the suppliers table.

Table info

suppliers(supplier_id,supplier_name,contact_person,phone_number,email,address)
```
```sql
update suppliers set supplier_name='A1 Suppliers' where supplier_id=8;
```

**Output:**
<img width="1210" height="426" alt="Screenshot 2026-08-30 182205" src="https://github.com/user-attachments/assets/d2dceaef-285d-473a-b757-9ed00f799e54" />


**Question 3**
```---
 Update the total selling price to quantity sold multiplied by updated selling price per unit where product id is 10 in the sales table.

SALES TABLE
name               type
-----------------  ---------------
sale_id            INT
sale_date          DATE
product_id         INT
quantity           INT
sell_price         DECIMAL(10,2)
total_sell_price   DECIMAL(10,2)
```
```sql
update SALES set total_sell_price=quantity*sell_price where product_id=10;
```

**Output:**
<img width="1225" height="517" alt="Screenshot 2026-08-30 182315" src="https://github.com/user-attachments/assets/a0429193-c9cf-438c-a148-b2c789824ffc" />


**Question 4**
---
<img width="1228" height="301" alt="Screenshot 2026-08-30 182350" src="https://github.com/user-attachments/assets/a8ec6e05-7d7a-4547-85f3-5f3af791d3ea" />


```sql
delete from Customer where GRADE%2 =1;
```

**Output:**
<img width="1216" height="436" alt="image" src="https://github.com/user-attachments/assets/66fa1432-b647-4f25-ac34-7d9f83895edf" />


**Question 5**
```---
Write a SQL query to Delete All Doctors with a NULL Last Name

Sample table: Doctors

attributes : doctor_id, first_name, last_name, specialization
```
```sql
Delete from Doctors where last_name is null;
```

**Output:**
<img width="1196" height="712" alt="Screenshot 2026-08-30 182627" src="https://github.com/user-attachments/assets/3386db85-3b42-47f1-b55d-1e6c9e0e73f1" />


**Question 6**
---
<img width="1183" height="181" alt="Screenshot 2026-08-30 182752" src="https://github.com/user-attachments/assets/07dfc867-0893-4f25-9e0c-2dc45d26746a" />

```sql
select * from EmployeeInfo where EmpFname not in("Sanjay","Sonia");
```

**Output:**

<img width="1213" height="277" alt="Screenshot 2026-08-30 192146" src="https://github.com/user-attachments/assets/ba9d4ac3-c770-49a2-b207-6ce908a96e7f" />


**Question 7**
---
<img width="917" height="297" alt="Screenshot 2026-08-30 192221" src="https://github.com/user-attachments/assets/97d169fd-34bd-4984-a22c-9acd855ea256" />



```sql
select id,value1, case when cast(value1 as integer)%2=0 then 'Even' else 'Odd' end as parity from Calculations  ;
```

**Output:**
<img width="812" height="495" alt="Screenshot 2026-08-30 192411" src="https://github.com/user-attachments/assets/0525fcd2-12ed-44d6-9b04-47132e3f818a" />


**Question 8**
---
<img width="1217" height="380" alt="Screenshot 2026-08-30 192517" src="https://github.com/user-attachments/assets/ef7862ab-3b61-4e6b-aecd-34e4f89ea35d" />

```sql
select * from orders where not (ord_date='2012-08-17'or(customer_id>3005 and purch_amt<1000));
```

**Output:**
<img width="1178" height="787" alt="Screenshot 2026-08-30 192610" src="https://github.com/user-attachments/assets/8b09944d-161c-4d0a-8b04-f07586a888b4" />


**Question 9**
```---
Write a SQL query to calculate the discounted price for each product. Return product_id, original_price, discount_percentage, and discounted_price.

Sample table: Products

product_id | original_price | discount_percentage
------------+----------------+---------------------
101 | 50.00 | 0.10
102 | 75.00 | 0.15
103 | 100.00 | 0.20
```

```sql
select product_id,original_price,discount_percentage,original_price*(1-discount_percentage) as discounted_price from Products;
```

**Output:**
<img width="1237" height="457" alt="Screenshot 2026-08-30 193405" src="https://github.com/user-attachments/assets/9768e36f-87fb-43f9-a842-08d994365522" />


**Question 10**
---
Write a SQL query to retrieve the year, month, and day from the hiredate column in the emp table.

```sql
select substr(hiredate,1,4) as Year,
substr(hiredate,6,2) as Month ,
substr (hiredate,9,2) as Day from emp;
```

**Output:**
<img width="837" height="367" alt="Screenshot 2026-08-30 193603" src="https://github.com/user-attachments/assets/cf19dda7-79dc-4ff3-9a80-2a49bf02a8df" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
