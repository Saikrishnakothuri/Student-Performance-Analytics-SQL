# Student-Performance-Analytics-SQL
This repository contains SQL scripts for setting up, managing, and analyzing an expanded student database. The project demonstrates fundamental to intermediate SQL concepts, including database schema design, data definition (DDL), data manipulation (DML), complex querying, view creation, and schema modification. Crucially, this version also highlights performance optimization techniques through strategic indexing and efficient query writing.

This project is ideal for showcasing proficiency in:

# Relational Database Design: 
Understanding entities, relationships, and data integrity.

# SQL Fundamentals:
Mastery of CREATE, INSERT, SELECT, UPDATE, ALTER, DROP statements.

# DQL (Data Query Language):
Proficient use of SELECT statements for data retrieval and analysis.

# Advanced SQL Queries:
Utilizing JOIN operations (INNER, LEFT, RIGHT), GROUP BY, HAVING, CASE statements, and subqueries.

# Data Analysis:
Extracting meaningful insights such as average marks, total scores, and student categorization.

# Database Performance Optimization:
Implementing indexes to improve query execution speed and understanding the impact of query structure.

# Handling Larger Datasets:
Demonstrating the ability to manage and query a dataset of over 200 student records.

# Database Schema
# The database is composed of three interconnected tables:

# STUDENTS Stores student biographical information.

Name (VARCHAR(100), NOT NULL)

Student_ID (INT, Primary Key)

Student_Age (INT) - Note: This column is later used to derive a Grade and then dropped for schema evolution demonstration.

Grade (VARCHAR(10)) - Added dynamically based on Student_Age.

# Subjects: Contains details about available subjects.

SubjectID (INT, Primary Key)

Subject_Name (VARCHAR(100))

# Marks: Records the scores obtained by students in various subjects.

Student_ID (INT, Foreign Key referencing STUDENTS.Student_ID)

SubjectID (INT, Foreign Key referencing Subjects.SubjectID)

Marks (INT)

The database is populated with an initial set of students and subjects, and then significantly expanded with over 200 additional student records from the Telugu region, each with corresponding marks across all subjects. This expanded dataset provides a more realistic scenario for demonstrating SQL capabilities.


# Key Features
Comprehensive Table Management: Scripts for creating, populating, and modifying database tables.

Diverse Data Types: Usage of VARCHAR, INT for different data representations.

Primary and Foreign Key Constraints: Ensuring data integrity and establishing relationships between tables.

Data Retrieval & Filtering: Demonstrates various SELECT statements with WHERE and DISTINCT clauses.

Aggregate Functions: Calculation of AVG() and SUM() for data summarization.

Grouping and Ordering: Using GROUP BY and ORDER BY to organize results for analysis.

Conditional Logic: Implementation of CASE statements for data categorization (e.g., 'Undergrad'/'Postgrad').

Database Views: Creation and querying of StudentTotalMarks view for simplified data access.

Schema Evolution: Demonstrates ALTER TABLE operations to add and drop columns.

Robust Joins: Examples of INNER JOIN, LEFT JOIN, and RIGHT JOIN to combine data from multiple tables effectively.

# Performance Considerations & Optimizations

This project goes beyond basic SQL by actively addressing performance. It showcases practical strategies to optimize database operations, ensuring efficient data retrieval and processing, even with growing datasets. Key optimizations include:

# Strategic Indexing for Accelerated Queries: 
Implemented CREATE INDEX statements on frequently queried and joined columns (Marks.Student_ID, Marks.SubjectID, Marks.Marks, STUDENTS.Name, STUDENTS.Grade). These indexes dramatically reduce query execution time by enabling rapid data lookup, which is critical for large datasets and complex analytical operations.

# Efficient Query Pattern Design:
Replaced less efficient WHERE IN (SELECT ...) subqueries with optimized JOIN operations. This approach empowers the database optimizer with greater flexibility, leading to more performant execution plans and faster results.

# Targeted Data Retrieval: 
Adopted explicit column selection (SELECT column1, column2) instead of SELECT * in queries where only specific data is required. This minimizes unnecessary data transfer over the network and reduces memory consumption, enhancing overall system efficiency.
