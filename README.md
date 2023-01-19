# SQL-Cheatsheet
Welcome to the SQL Cheatsheet repository! <br>
This cheatsheet is a comprehensive collection of commonly-used SQL queries and commands, organized by topic (e.g. DDL, DML, etc.). Our goal is to make it easy for developers, data analysts, and database administrators to quickly find and use the SQL commands they need.

To contribute to the cheatsheet, please follow these guidelines:
- Make sure your contributions align with the theme and scope of the cheatsheet.
- You can submit a pull request with your changes. Please make sure that your pull request follows the same formatting and style as the rest of the cheatsheet.
- The pull request will be reviewed by the maintainers of the repository, who will check if the changes align with the scope of the cheatsheet and that it is formatted correctly.
- Once the pull request is approved, it will be merged into the cheatsheet.

Thank you for your contributions to this community-driven project!

# Table of Content


## About SQL
### Main Features
- SQL is a declarative, set- and table-oriented language
- SQL lacks features of a programming language
- No undo feature!
- Not case-sensitive
- Recommendation: use uppercase for keywords, lowercase for table and column names
- Arbitrary use of spaces, line breaks, and tabs is allowed.

### Language Areas
SQL is the standard language and interface for:
- Defining (DDL)
- Managing access (DCL)
- Manipulating (DML)
- Querying (DQL) relational databases.

![language areas](images/language_areas.png)

([Back to top](#sql-cheatsheet))
## Data Definition Language (DDL)
> Description
### CREATE
> This command is used to create a new table with specified columns and data types
```sql       
    CREATE TABLE table_name (
    column1 data_type constraint,
    column2 data_type constraint,
    );
```
### ALTER
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

### DROP
> This command is used to delete an existing table and all its data
```sql
    DROP TABLE table_name;
```
### TRUNCATE
> This command is used to delete all data from an existing table, but keeps the table structure
```sql
    TRUNCATE TABLE table_name;
```
### SQL KEYS
> This command is used to specify a column or set of columns as the primary key for a table
```sql
    PRIMARY KEY (column1, column2, ...)
```
> This command is used to specify a foreign key constraint on a column in a table
```sql
    FOREIGN KEY (column) REFERENCES referenced_table(referenced_column)
```

([Back to top](#sql-cheatsheet))
## Data Manipulation Language (DML)
> Description
### INSERT
> This command is used to insert new data into a table
```sql
    INSERT INTO table_name (column1, column2, ...)
    VALUES (value1, value2, ...);
```
### UPDATE
> This command is used to update existing data in a table
```sql
    UPDATE table_name
    SET column1 = value1, column2 = value2, ...
    WHERE some_column = some_value;
```
### DELETE
> This command is used to delete data from a table
```sql
    DELETE FROM table_name
    WHERE some_column = some_value;
```
### CASCADING
> This command is used to specify that when a referenced row in a parent table is deleted, all corresponding rows in a child table will also be deleted
```sql
    CREATE TABLE table1 (
        id INT PRIM
    );
```
### MERGE
> This command is used to either update or insert data into a table based on a condition
```sql
    MERGE INTO table_name
    USING (SELECT column1, column2, ... FROM source_table) source
    ON (table_name.id = source.id)
    WHEN MATCHED THEN UPDATE SET column1 = source.column1, ...
    WHEN NOT MATCHED THEN INSERT (column1, column2, ...)
    VALUES (source.column1, source.column2, ...);
```

([Back to top](#sql-cheatsheet))
## Data Query Language (DQL)
> Description
### SELECT
> Description
```

```
### WHERE
> Description
```

```
### CASE
> Description
```

```
### JOIN
> Description
```

```
### GROUP
> Description
```

```
### SUBQUERIES
> Description
```

```
### SET OPERATIONS
> Description
```

```

([Back to top](#sql-cheatsheet))
## Views
> Description
### CREATE
> This command is used to create a virtual table based on the result of a SELECT statement
```sql
    CREATE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
```
### QUERY
> This command is used to query data from a view
```sql
    SELECT column1, column2, ...
    FROM view_name;
```
### EDIT
> This command is used to modify the SELECT statement of a view
```sql
    CREATE OR REPLACE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
```
### DELETE
> This command is used to delete a view
```sql
    DROP VIEW view_name;
```

([Back to top](#sql-cheatsheet))
## Data Security
> Description
### AUTHENTICATION
> This command is used to create a new user with a specified password
```sql
    CREATE USER user_name IDENTIFIED BY 'password';
```
> This command is used to grant a user access to a specific database or table
```sql
    GRANT SELECT, INSERT, UPDATE, DELETE ON table_name TO user_name;
```
### AUTHORIZATION
> This command is used to revoke a user's access to a specific database or table
```sql
    REVOKE SELECT, INSERT, UPDATE, DELETE ON table_name FROM user_name;
```
### ROW LEVEL SECURITY
> This command is used to create a policy that restricts access to specific rows in a table based on a user's role
```sql
    CREATE POLICY policy_name ON table_name
    FOR SELECT
    WITH CHECK (condition)
```
### DYNAMIC DATA MASKING
> This command is used to mask sensitive data in a table
```sql
    ALTER TABLE table_name
    ADD MASKED WITH (FUNCTION = 'masking_function')
    FOR COLUMN sensitive_column;
```
### ENCRYPTION
> This command is used to encrypt a specific column in a table
```sql
    ALTER TABLE table_name
    ALTER COLUMN sensitive_column
    ADD ENCRYPTION (TYPE = Deterministic, ALGORITHM = 'AEAD_AES_256_CBC_HMAC_SHA_256');
```
## Data Backup
> Description

([Back to top](#sql-cheatsheet))
