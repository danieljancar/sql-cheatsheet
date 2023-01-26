# Data Definition Language
> DDL is a subset of SQL (Structured Query Language) that is used to define the structure of a relational database. DDL statements are used to create, modify, and delete database objects such as tables, views, indexes, and constraints.
## Informations
The Informations Chapter is used to give out specified Informations about SQL.
> This command is used to give out your own name in a specific table.
```sql       
    SELECT 'your_name' AS 'Your Name'
```
## EXEC
The EXEC command is used to change the names in SQL
> This command is used to change the name in a specific column or table.
```sql       
    EXEC sp_rename 'schema_name', 'descripton', 'COLUMN';
```
> This command is used to show the informations in a specific table.
```sql       
    EXEC sp_columns table_name
```
## CREATE
The CREATE command is used to create a new table with specified columns and data types. The table name, column names, and data types must be defined within the command.
> This command is used to create a new table with specified columns and data types
```sql       
    CREATE TABLE table_name (
    column1 data_type constraint,
    column2 data_type constraint,
    );
```
> Create a Table with a Schema
```SQL
    CREATE TABLE schema.table_name (
        id INT NOT NULL IDENTITY(1,1),
        column1 CHAR(4),
        column2 INT,
        column3 VARCHAR(50)
    );
```
## Schema
> Creating a Schema in a Database
```SQL
    USE m106;
    GO
    CREATE SCHEMA schema106;
```
## ALTER
The ALTER command is used to make changes to an existing table, such as adding a new column, modifying an existing column, or deleting a column.
> This command is used to add a new column to an existing table
```sql
    ALTER TABLE table_name
    ADD column_name data_type constraint;
```
> This command is used to modify an existing column in a table
```sql
    ALTER TABLE table_name
    MODIFY column_name data_type constraint;
```

> This command is used to delete a column from an existing table
```sql
    ALTER TABLE table_name
    DROP COLUMN column_name;
```

## Rename
The rename command is used to rename tables and columns
> This renames a table
```sql
 EXEC sp_rename 'existing_table_name', 'new_table_name'; 
```
> This renames a column
```sql
 EXEC sp_rename 'existing_table_name.existing_column_name', 'new_table_name.new_column_name'; 
```

## DROP
The DROP command is used to delete an existing table, its structure, and all its data permanently from the database. It can also be used to delete other database objects such as views, indexes, and sequences. Once a table is dropped, all the data stored in it will be lost and cannot be recovered. It is important to use this command with caution as it cannot be undone.
> This command is used to delete an existing table and all its data
```sql
    DROP TABLE table_name;
```
## TRUNCATE
The TRUNCATE command is used to delete all data from an existing table, but it keeps the table structure and its associated objects such as indexes, triggers, and constraints. Unlike the DROP command, TRUNCATE does not generate any undo logs, making it faster and more efficient for large tables with many rows. However, it also does not fire any DELETE triggers, and the data deleted cannot be recovered. It is important to use this command with caution as it cannot be undone.
> This command is used to delete all data from an existing table, but keeps the table structure
```sql
    TRUNCATE TABLE table_name;
```
## SQL KEYS
In SQL, keys are used to establish and enforce relationships between tables in a database. There are two main types of keys: primary keys and foreign keys.
**Primary Key**
A primary key is a unique identifier for each row in a table. It is used to enforce the integrity of the data and to ensure that there are no duplicate values in the table. Only one primary key can be defined for a table, and it cannot contain null values. The primary key is defined using the PRIMARY KEY constraint.
> This command is used to specify a column or set of columns as the primary key for a table
```sql
    PRIMARY KEY (column1, column2, ...)
```
**Foreign Key**
A foreign key is a column or set of columns in a table that is used to establish a link between the data in two tables. The foreign key references a primary key in another table, creating a link between the two tables. This link is used to enforce referential integrity, which ensures that data in the related tables is consistent and that there are no orphaned records. The foreign key is defined using the FOREIGN KEY constraint.
> This command is used to specify a foreign key constraint on a column in a table
```sql
    FOREIGN KEY (column) REFERENCES referenced_table(referenced_column)
```
**CHECK**
In summary, primary keys are used to uniquely identify each record in a table and foreign keys are used to create links between tables, ensuring data integrity and consistency.
If you want to define a simple validation or business rule on a table, CHECK is suitable. 
> This constraint forces a value to belong to a specific range.
```SQL
    ALTER TABLE tabelle1 ADD CHECK (feld2 > 100);
```
