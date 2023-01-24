# Data Manipulation Language
> DML is a computer programming language used to retrieve, manipulate, and update data in a relational database. Examples of DML statements include SELECT, INSERT, UPDATE, and DELETE. These statements allow users to query the database for specific information, add new data to the database, change existing data, and delete unwanted data. DML is typically used in conjunction with Data Definition Language (DDL) statements, which are used to create and modify the structure of a database, such as creating tables and establishing relationships between them.
## INSERT
The INSERT statement is used to insert new data into a table in the database. It allows the user to specify the columns and values of the new data being inserted.
> This command is used to insert new data into a table
```sql
    INSERT INTO table_name (column1, column2, ...)
    VALUES (value1, value2, ...);
```
> This command is used to insert multiple new data into a table
```sql
    INSERT INTO table_name VALUES
    (column1-value1, column1-value2),
    (column2-value1, column2-value2);
```
## UPDATE
The UPDATE statement is used to modify existing data in a table. It allows the user to specify which columns and values to update and the condition to select which rows to update.
> This command is used to update existing data in a table
```sql
    UPDATE table_name
    SET column1 = value1, column2 = value2, ...
    WHERE some_column = some_value;
```
## DELETE
The DELETE statement is used to delete data from a table. It allows the user to specify the condition to select which rows to delete.
> This command is used to delete data from a table
```sql
    DELETE FROM table_name
    WHERE some_column = some_value;
```
## CASCADING
The CASCADE option is used to specify that when a referenced row in a parent table is deleted, all corresponding rows in a child table will also be deleted.
> This command is used to specify that when a referenced row in a parent table is updated, all corresponding rows in a child table will also be updated
```sql
    ALTER TABLE aTable WITH CHECK ADD CONSTRAINT FK_a_table FOREIGN KEY
    (fk_id) REFERENCES bTable(id) ON UPDATE CASCADE;
```
> This command is used to specify that when a referenced row in a parent table is deleted, all corresponding rows in a child table will also be deleted
```sql
    ALTER TABLE aTable WITH CHECK ADD CONSTRAINT FK_a_table FOREIGN KEY
    (fk_id) REFERENCES bTable(id) ON DELETE CASCADE;
```
> You also can combine them
```sql
    ALTER TABLE aTable WITH CHECK ADD CONSTRAINT FK_a_table FOREIGN KEY
    (fk_id) REFERENCES bTable(id) ON UPDATE CASCADE ON DELETE CASCADE;
```
## MERGE
The MERGE statement is used to either update or insert data into a table based on a condition. It allows the user to specify a source table, the conditions for updating and inserting and the columns and values to be used.
> This command is used to either update or insert data into a table based on a condition
```sql
    MERGE INTO table_name
    USING (SELECT column1, column2, ... FROM source_table) source
    ON (table_name.id = source.id)
    WHEN MATCHED THEN UPDATE SET column1 = source.column1, ...
    WHEN NOT MATCHED THEN INSERT (column1, column2, ...)
    VALUES (source.column1, source.column2, ...);
```