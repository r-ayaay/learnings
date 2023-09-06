#mysql #sql #docker #cmd 

**Show all tables:**
SHOW TABLES;

**List data from table:**  
SELECT * (or column_1, column_2, …)
FROM _table_name_;

**List data from table (conditional):**
SELECT column_1, column_2
FROM table_name
WHERE
column_name = condition,

**Show columns of a table and display data type:**
SHOW columns FROM table_name
OR
DESCRIBE table_name

**Adding data:**
INSERT INTO table_name
(column_1, column_2,…)
VALUES (value_1, value_2,…);

**Update data:**
UPDATE table_name
SET
column_name = ‘new_value’
WHERE
column_name = condition;

The ALTER TABLE statement is used to add, delete, or modify **columns** in an existing table.
ALTER TABLE _table_name_
ADD _column_name datatype_;

ALTER TABLE _table_name_
DROP COLUMN _column_name_;

ALTER TABLE _table_name_
MODIFY COLUMN _column_name datatype_;
  
*modify is to change data type