# 1527. Patients With a Condition

Table: ```Patients```
```
+--------------+---------+
| Column Name  | Type    |
+--------------+---------+
| patient_id   | int     |
| patient_name | varchar |
| conditions   | varchar |
+--------------+---------+
patient_id is the primary key for this table.
'conditions' contains 0 or more code separated by spaces. 
This table contains information of the patients in the hospital.
```
**SQL Schema**
```
Create table If Not Exists Patients (patient_id int, patient_name varchar(30), conditions varchar(100))
Truncate table Patients
insert into Patients (patient_id, patient_name, conditions) values ('1', 'Daniel', 'YFEV COUGH')
insert into Patients (patient_id, patient_name, conditions) values ('2', 'Alice', '')
insert into Patients (patient_id, patient_name, conditions) values ('3', 'Bob', 'DIAB100 MYOP')
insert into Patients (patient_id, patient_name, conditions) values ('4', 'George', 'ACNE DIAB100')
insert into Patients (patient_id, patient_name, conditions) values ('5', 'Alain', 'DIAB201')
```

Write an SQL query to report the patient_id, patient_name and conditions of the patients who have Type I Diabetes. Type I Diabetes always starts with DIAB1 prefix.

Return the result table in any order.

The query result format is in the following example.

 

**Example 1:**
```
Input: 
Patients table:
+------------+--------------+--------------+
| patient_id | patient_name | conditions   |
+------------+--------------+--------------+
| 1          | Daniel       | YFEV COUGH   |
| 2          | Alice        |              |
| 3          | Bob          | DIAB100 MYOP |
| 4          | George       | ACNE DIAB100 |
| 5          | Alain        | DIAB201      |
+------------+--------------+--------------+
Output: 
+------------+--------------+--------------+
| patient_id | patient_name | conditions   |
+------------+--------------+--------------+
| 3          | Bob          | DIAB100 MYOP |
| 4          | George       | ACNE DIAB100 | 
+------------+--------------+--------------+
Explanation: Bob and George both have a condition that starts with DIAB1.
```
**Solution**
```
# Write your MySQL query statement below
SELECT * FROM Patients
WHERE conditions LIKE '% DIAB1%' OR conditions LIKE 'DIAB1%'
```
