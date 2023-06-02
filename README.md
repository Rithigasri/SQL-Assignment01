# SQL ASSIGNMENT 01: IMPLEMENT USAGE OF KEYWORDS- CASE,CROSS JOIN,FULL OUTER JOIN

## QUESTION 1: USING CASE EXPRESSION
### PROGRAM:
```
--create
CREATE TABLE EMPLOYEE (
  empId INTEGER PRIMARY KEY,
  firstname TEXT NOT NULL,
  lastname TEXT NOT NULL,
  salary INTEGER NOT NULL
);
--insert
INSERT INTO EMPLOYEE VALUES (0001, 'Harry', 'potter',1000);
INSERT INTO EMPLOYEE VALUES (0002, 'Dave', 'John',3500);
INSERT INTO EMPLOYEE VALUES (0003, 'Ava', 'Grayson',7000);
INSERT INTO EMPLOYEE VALUES (0004, 'Eda', 'Srikar',1200);
INSERT INTO EMPLOYEE VALUES (0005, 'Robert', 'Brown',2500);
INSERT INTO EMPLOYEE VALUES (0006, 'Will', 'John',9000);

SELECT empId,firstname,lastname,salary,
CASE
WHEN salary<3000 THEN "Low"
WHEN salary>3000 AND salary<5000 THEN "Average"
ELSE "High"
END AS result
FROM EMPLOYEE;
```
### OUTPUT:
![image](https://github.com/Rithigasri/SQL-Assignment01/assets/93427256/22bbed32-08e6-4ac6-9e84-b29e00968327)

## QUESTION 2: CROSS JOIN KEYWORD
### PROGRAM:
```
CREATE TABLE sales_organization 
(
	sales_org_id INT PRIMARY KEY,
	sales_org VARCHAR (255)
);
CREATE TABLE sales_channel 
(
	channel_id INT PRIMARY KEY,
	channel_name VARCHAR (255)
);
INSERT INTO sales_organization (sales_org_id, sales_org)
VALUES
(1, 'Domestic'),
(2, 'Export');
INSERT INTO sales_channel (channel_id, channel_name)
VALUES
(1, 'Wholesale'),
(2, 'Retail'),
(3, 'eCommerce'),
(4, 'TV Shopping');
SELECT
sales_org,
channel_name
FROM
sales_organization
CROSS JOIN sales_channel;
```
### OUTPUT:
![image](https://github.com/Rithigasri/SQL-Assignment01/assets/93427256/6d76d3c5-57c4-4912-8205-9c63183de8d6)
## QUESTION 3: FULL OUTER JOIN
### PROGRAM:
```
CREATE TABLE fruits (
fruit_id INTEGER PRIMARY KEY,
fruit_name VARCHAR (255) NOT NULL,
basket_id INTEGER
);
CREATE TABLE baskets (
basket_id INTEGER PRIMARY KEY,
basket_name VARCHAR (255) NOT NULL
);
INSERT INTO baskets (basket_id, basket_name)
VALUES
(1, 'A'),
(2, 'B'),
(3, 'C');
INSERT INTO fruits (fruit_id,fruit_name,basket_id)
VALUES
(1, 'Apple', 1),
(2, 'Orange', 1),
(3, 'Banana', 2),
(4, 'Strawberry', NULL);
SELECT
basket_name,
fruit_name
FROM
fruits
FULL OUTER JOIN baskets ON baskets.basket_id = fruits.basket_id;
```
### OUTPUT:
![image](https://github.com/Rithigasri/SQL-Assignment01/assets/93427256/eaceee71-e2b5-427c-a15d-760c47d15e7a)

