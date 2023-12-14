# Student List

## Create a new database
Create a new database for this exercise.
```
CREATE DATABASE exercise_student_list
use exercise_student_list
```
mysql> SHOW DATABASES;
+-----------------------+
| Database              |
+-----------------------+
| article               |
| exercise_student_list |
| information_schema    |
| mydb                  |
| mysql                 |
| new_database          |
| performance_schema    |
| sys                   |
+-----------------------+


## Create the student table
Create a table named **students** with the following columns:  
```
id (integer, primary key)  
name (varchar, maximum length 50)  
age (integer)  
grade (float)  
```

> ANSWER
> mysql> CREATE TABLE students(
    -> id INT,
    -> name VARCHAR(50),
    -> age INT,
    -> grade FLOAT,
    -> PRIMARY KEY(id)
    -> );
> mysql> DESCRIBE students;
+--------+---------------+------+-----+---------+-------+
| Field  | Type          | Null | Key | Default | Extra |
+--------+---------------+------+-----+---------+-------+
| id     | int           | NO   | PRI | NULL    |       |
| name   | varchar(50)   | YES  |     | NULL    |       |
| age    | int           | YES  |     | NULL    |       |
| grade  | float         | YES  |     | NULL    |       |
| adress | varchar(100)  | YES  |     | NULL    |       |
+--------+---------------+------+-----+---------+-------+


## Insert and Modify Data
### 1. Insert Data
Insert these records into the students table with the following data:
```
(1, 'John Doe', 20, 85.5, '123 Main St')
(2, 'Jane Smith', 22, 92.0, '456 Oak Ave')
(3, 'Bob Johnson', 21, 78.5, '789 Pine Rd')
(4, 'Tina Turner', 25, 71.0, '45 Columbia St')
```

> ANSWER
> mysql> INSERT INTO students VALUES (1, 'John Doe', 20, 85.5, '123 Main St'),
    -> (2, 'Jane Smith', 22, 92.0, '456 Oak Ave'),
    -> (3, 'Bob Johnson', 21, 78.5, '789 Pine Rd'),
    -> (4, 'Tina Turner', 25, 71.0, '45 Columbia St');
> mysql> SELECT * FROM students;
+----+-------------+------+-------+----------------+
| id | name        | age  | grade | adress         |
+----+-------------+------+-------+----------------+
|  1 | John Doe    |   20 |    86 | 123 Main St    |
|  2 | Jane Smith  |   22 |    92 | 456 Oak Ave    |
|  3 | Bob Johnson |   21 |    79 | 789 Pine Rd    |
|  4 | Tina Turner |   25 |    71 | 45 Columbia St |
+----+-------------+------+-------+----------------+



### Update Data
Update the grade of 'Jane Smith' to 95.0.

> ANSWER
> mysql> UPDATE students SET grade=95.0 WHERE name='Jane Smith';
> > mysql> SELECT * FROM students;
+----+-------------+------+-------+----------------+
| id | name        | age  | grade | adress         |
+----+-------------+------+-------+----------------+
|  1 | John Doe    |   20 |    86 | 123 Main St    |
|  2 | Jane Smith  |   22 |    95 | 456 Oak Ave    |
|  3 | Bob Johnson |   21 |    79 | 789 Pine Rd    |
|  4 | Tina Turner |   25 |    71 | 45 Columbia St |
+----+-------------+------+-------+----------------+

### Delete Data
Delete the record of the student with id 3 from the students table.

> ANSWER
mysql> DELETE FROM students WHERE id=3;
mysql> SELECT * FROM students;
+----+-------------+------+-------+----------------+
| id | name        | age  | grade | adress         |
+----+-------------+------+-------+----------------+
|  1 | John Doe    |   20 |    86 | 123 Main St    |
|  2 | Jane Smith  |   22 |    95 | 456 Oak Ave    |
|  4 | Tina Turner |   25 |    71 | 45 Columbia St |
+----+-------------+------+-------+----------------+


 

### Select Data
Write a query to retrieve the names and ages of all students.  

> ANSWER
> mysql> SELECT name,age  FROM students;
+-------------+------+
| name        | age  |
+-------------+------+
| John Doe    |   20 |
| Jane Smith  |   22 |
| Tina Turner |   25 |
+-------------+------+ 

### Bonus: Select the best students
Write a query to retrieve the names and grade of all students with a grade higher than 80.

> ANSWER
> mysql> SELECT name,grade FROM students WHERE grade >80;
+------------+-------+
| name       | grade |
+------------+-------+
| John Doe   |    86 |
| Jane Smith |    95 |
+------------+-------+


