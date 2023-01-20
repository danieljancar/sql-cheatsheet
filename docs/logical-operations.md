# Logical Operations
## AND
> logical AND link
```sql
    SELECT * FROM table1 WHERE age < 18 AND plz = 5000;
```
## OR
> logical other link
```sql
    SELECT * FROM table1 WHERE age < 18 OR age > 65;
```
## NOT
> not same (!=)
```sql
    SELECT * FROM tabelle WHERE NOT id = 1;MAX()
```
## BETWEEN
> BETWEEN checks whether the checked value is between two values.
```sql
    SELECT id, column2, column3 FROM table1 WHERE id BETWEEN 1 AND 10;

    SELECT id, column2, column3 FROM table1 
    WHERE eintritt BETWEEN '2020-01-01' AND '2020-12-31'; 

    -- comparison operators can always be used instead of BETWEEN
    -- and these are linked with AND
    SELECT id, column2, column3 FROM table1 
    WHERE eintritt >= '2020-01-01' AND eintritt <= '2020-12-31';
```
## IN
> The IN operator can be used to determine whether a value matches a value from a list. In the list, for example, you can list certain numbers that are to be compared with a column:
```sql
    SELECT id, column2, column3 FROM table1 WHERE id IN (1, 2, 3);
```
## LIKE
> Für komplexere Text-Abfragen bietet sich LIKE an. LIKE sucht nach einem Muster in einem String und wird deshalb auch als Mustervergleich bezeichnet. Dabei gibt es verschiedene Platzhalter:
```sql
    -- % -> Any numbers of characters 
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '%peter%';
    -- _ -> one characters 
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '_peter';
    -- [] -> placeholder for a-p
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '[a-p]peter';
    -- [^] -> placeholder for one character between a-p
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '[^a-p]peter';
```
## NULL
> If you ask is an item Null or not you have to use IS
```sql
    SELECT * FROM table1 WHERE column2 IS NULL;
    -- or NOT
    SELECT * FROM table1en WHERE column2 IS NOT NULL;
```