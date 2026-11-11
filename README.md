# Week-7-Assignment-Database-Design-and-Normalization
Overview

This repository contains the SQL solution for the Week 7 Database Design and Normalization assignment. The objective of this assignment is to demonstrate how to structure relational databases efficiently by applying normalization rules—specifically transforming unnormalized data into First Normal Form (1NF) and Second Normal Form (2NF).

Objectives Achieved

1NF Transformation: Replaced non-atomic values (comma-separated lists in single cells) with individual atomic records.

2NF Transformation: Identified partial dependencies on composite keys and decoupled order details into dedicated tables using Primary Key and Foreign Key constraints.

Data Integrity: Ensured referential integrity and reduced overall data redundancy.

Solutions Breakdown

Question 1: First Normal Form (1NF)

Problem: The original ProductDetail table stored multiple products inside a single cell in the Products column.

Solution: Designed the ProductDetail_1NF table where each row contains exactly one product per order.

Question 2: Second Normal Form (2NF)

Problem: The OrderDetails table had a composite key (OrderID, Product), but CustomerName depended only on OrderID (a partial dependency).

Solution:

Split the dataset into two normalized tables:

Orders: Stores order-level information (OrderID, CustomerName).

OrderItems: Stores itemized order information (OrderID, Product, Quantity) with a composite Primary Key and a Foreign Key linking back to Orders.

Files Included

answer.sql: Contains all CREATE TABLE and INSERT INTO statements for both 1NF and 2NF tasks, fully documented with comments.

README.md: Project documentation and execution instructions.

How to Run

Clone the Repository:

git clone <your-repository-url>
cd <your-repository-folder>


Execute in MySQL / Database Client:

Open MySQL Workbench or your preferred SQL editor.

Open the answer.sql file.

Execute the queries sequentially to create the normalized tables and populate them with data.

Verify Results:

SELECT * FROM ProductDetail_1NF;
SELECT * FROM Orders;
SELECT * FROM OrderItems;
