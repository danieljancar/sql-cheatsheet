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

![language areas](images/language_areas.png){: align="center"}  

([Back to top](#sql-cheatsheet))
## Data Definition Language (DDL)
> Description
### CREATE
> Description
``` 
-- This command is used to create a new table with specified columns and data types
        CREATE TABLE table_name (
        column1 data_type constraint,
        column2 data_type constraint,
        );
```
### ALTER
> Description
```
-- This command is used to add a new column to an existing table
        ALTER TABLE table_name
        ADD column_name data_type constraint;

-- This command is used to modify an existing column in a table
        ALTER TABLE table_name
        MODIFY column_name data_type constraint;

-- This command is used to delete a column from an existing table
        ALTER TABLE table_name
        DROP COLUMN column_name;
```
### DROP
> Description
```
-- This command is used to delete an existing table and all its data
        DROP TABLE table_name;
```
### TRUNCATE
> Description
```

```
### SQL KEYS
> Description
```

```

([Back to top](#sql-cheatsheet))
## Data Manipulation Language (DML)
> Description
### INSERT
> Description
```

```
### UPDATE
> Description
```

```
### DELETE
> Description
```

```
### CASCADING
> Description
```

```
### MERGE
> Description
```

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
> Description
```

```
### QUERY
> Description
```

```
### EDIT
> Description
```

```
### DELETE
> Description
```

```

([Back to top](#sql-cheatsheet))
## Data Security
> Description
### AUTHENTICATION
> Description
```

```
### AUTHORIZATION
> Description
```

```
### ROW LEVEL SECURITY
> Description
```

```
### DYNAMIC DATA MASKING
> Description
```

```
### ENCRYPTION
> Description
```

```
## Data Backup
> Description

([Back to top](#sql-cheatsheet))
