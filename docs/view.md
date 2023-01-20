# Views
> A view in a relational database is a virtual table that is based on the result of a SELECT statement. It does not store data itself, but rather it provides a way to access data from one or more tables in a specific way. Views can be used to simplify complex queries, to restrict access to certain columns of a table, or to present data in a specific format.
## CREATE VIEW
The CREATE VIEW statement is used to create a new virtual table based on the result of a SELECT statement. It allows the user to specify the name of the view and the SELECT statement that defines the view.
> This command is used to create a virtual table based on the result of a SELECT statement
```sql
    CREATE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
```
## QUERY VIEW
The SELECT VIEW statement is used to query data from a view. It allows the user to specify the columns to retrieve and any conditions to filter the data.
> This command is used to query data from a view
```sql
    SELECT column1, column2, ...
    FROM view_name;
```
## EDIT VIEW / REPLACE VIEW
The CREATE OR REPLACE VIEW statement is used to modify the SELECT statement of an existing view. It allows the user to edit the SELECT statement that defines the view and update it without having to delete and recreate the view.
> This command is used to modify the SELECT statement of a view
```sql
    CREATE OR REPLACE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
```
## DROP VIEW
The DROP VIEW statement is used to delete a view. It allows the user to remove a virtual table from the database.
> This command is used to delete a view
```sql
    DROP VIEW view_name;
```