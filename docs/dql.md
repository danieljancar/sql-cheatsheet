# Data Query Language
> Data Query Language (DQL) is used to retrieve data from a relational database. DQL statements are used to select and retrieve data from one or more tables within a database. Examples of DQL statements include SELECT, GET and READ. These statements allow users to query the database for specific information and retrieve the data in a structured format. DQL statements are typically used by end-users to access and retrieve data from the database and are not used to make changes to the database structure or data. DQL statements are executed by the database management system (DBMS) and the results are returned to the user in the form of a table or other structured format.
## SELECT
The SELECT statement is used to query data from one or more tables in a database.
> This command is used to select all columns from a table
```sql
    SELECT * FROM table_name;
```
> This command is used to select specific columns from a table
```sql
    SELECT column1, column2, ... FROM table_name;
```
## AS 
The AS statement has the possibility to rename columns or tables for the query and thus to provide them with substitute names. Note that the aliases apply to the entire query, which means that you then have to use them consistently throughout the query.
> This command is used to rename columns of a query.
```sql
    SELECT column1 FROM table1 AS 'Total';
    -- or
    SELECT column1 Total FROM table1;
```
## DISTINCT 
The DISTINCT statement is used to ensure that identical values ​​appear only once in a table.
> This command is used to show values just once.
```sql
    SELECT DISTINCT table_name FROM column_name;
```
## ORDER BY 
The ORDER BY statement is used to sort data types, for example, all numeric data types or date values. Text fields can also be sorted.
> This command is used to sort data values of a specific table.
```sql
    SELECT column_name1, column_name2 FROM table_name ORDER BY column_name2;
```
> This command is used to sort multiple data values of a specific table.
```sql
    SELECT column_name1, column_name2 FROM table_name ORDER BY column_name1, column_name2;
```
## TOP 
The TOP statement is used to only show a specific amount of values in a table.
> This command is used to only show 10 value in a table and sort them.
```sql
    SELECT TOP 10 column_name AS 'newtable_name' FROM table_name ORDER BY column_name DESC
```
## CONCAT 
The CONCAT statement is used to combine multiple data tables in a database.
> This command is used to combine all columns from a table into one data.
```sql
    SELECT column1, CONCAT(column2, column3) AS newtable_name FROM table_name;
```
## WHERE
The WHERE clause is used to filter data based on a specific condition.
> This command is used to select all columns from a table where a specific column is equal to a certain value.
```sql
    SELECT * FROM table_name
    WHERE column_name = value;
```
## CASE
The CASE statement is used to evaluate a set of conditions and return a specific value based on the result.
> This command is used to select a column and assign a new column based on the value of another column
```sql
    SELECT column1,
    CASE column2
    WHEN value1 THEN 'new_value1'
    WHEN value2 THEN 'new_value2'
    ELSE 'new_value3'
    END AS new_column
    FROM table_name;
```
## INNER JOIN
You can use an INNER JOIN operation in any FROM clause. This is the most common type of join. Inner joins combine records from two tables whenever there are matching values in a field common to both tables. You can use INNER JOIN with the Departments and Employees tables to select all the employees in each department. The ON state is used to compare the FOREIGN KEYS.
> With the INNER JOIN you can display two tables with each other.
```sql
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable INNER JOIN btable ON atable.column2 = btable.column2;
```
## LEFT JOIN
The LEFT JOIN in SQL basically returns all records from the left table and the matched records from the right tables. For example, let's say, we have two tables, Table A and Table B. When LEFT JOIN is applied on these two tables, all records from Table A and only the matched records from Table B will be displayed. The ON state is used to compare the FOREIGN KEYS.
> With the LEFT JOIN you can display two tables with each other.
```sql
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable LEFT JOIN btable ON atable.column2 = btable.column2;
```

## RIGHT JOIN
The RIGHT JOIN in SQL basically returns all records from the right table and the matched records from the right tables. For example, let's say, we have two tables, Table B and Table B. When RIGHT JOIN is applied on these two tables, all records from Table A and only the matched records from Table A will be displayed. The ON state is used to compare the FOREIGN KEYS.
> With the RIGHT JOIN you can display two tables with each other.
```sql
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable RIGHT JOIN btable ON atable.column2 = btable.column2;
```
## FULL JOIN
The FULL JOIN is the RIGHT JOIN and the LEFT JOIN mixed so all records are show.
> With the FULL JOIN you can display two tables with each other.
```sql
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable FULL JOIN btable ON atable.column2 = btable.column2;
```

## SELF JOIN
A self-join is a join that can be used to join a table with itself. Hence, it is a unary relation. In a self-join, each row of the table is joined with itself and all the other rows of the same table. Thus, a self-join is mainly used to combine and compare the rows of the same table in the database.
> With the SELF JOIN you can display two tables with each other.
```sql
    SELECT atable.column1, atable.column2, atable.column3,  btable.column1 AS 'table1_name' AS 'table2_name'
    FROM table1 JOIN table2 ON atable.column1 = btable.column1;
```

## CROSS JOIN
CROSS JOIN is to use to generate a lot of data.
> With the CROSS JOIN you can display two tables with each other and all data are mixed.
```sql
    SELECT * FROM btable CROSS JOIN atable;
    -- or
    SELECT column1, column2, column3 FROM btable, atable;
```
## GROUP BY
The GROUP BY clause is used to group rows from a table based on one or more columns.
> This command is used to select a column and the count of its distinct values, grouped by another column
```sql
    SELECT column1, COUNT(DISTINCT column2)
    FROM table_name
    GROUP BY column1;
```
## HAVING
> The HAVING keyword can only be used in combination with GROUP BY and is used to restrict or filter the results of aggregate functions.
```sql
    SELECT table1 FROM column 
    GROUP BY table1
    HAVING COUNT(*) > 100;
```
> HAVING is only used to filter the aggregation. If you want to filter records before grouping, you have to set a WHERE clause accordingly. In the following query, we add the condition that the persons must be older than 18 to the above statement:
```sql
    SELECT count(id), table1 FROM column1 
    WHERE alter > 18
    GROUP BY table1 
    HAVING count(id) > 100;
```
## SUBQUERIES
The subquery is a query nested within another query. It is used to retrieve data from one table based on the results of another table.
> This command is used to select all columns from a table where a specific column matches a value returned by a subquery
```sql
    SELECT * FROM table1
    WHERE column1 = (SELECT column2 FROM table2)
```
## UNION
SET operations are used to combine the result of two or more SELECT statements into a single result.
> This command is used to select all distinct values from two or more tables that are combined using UNION
```sql
    SELECT column1 FROM table1
    UNION
    SELECT column1 FROM table2;
```
> This command is used to select all values from two or more tables that are combined using UNION ALL
```sql
    SELECT column1 FROM table1
    UNION ALL
    SELECT column1 FROM table2;
```
## INTERSECT
> This command is used to select all values that are in both the first and second table
```sql
    SELECT column1 FROM table1
    INTERSECT
    SELECT column1 FROM table2;
```
## EXCEPT
> This command is used to select all values that are unique to the first table and are not in the second table
```sql
    SELECT column1 FROM table1
    EXCEPT
    SELECT column1 FROM table2;
```