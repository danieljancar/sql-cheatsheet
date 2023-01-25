# Functions
## IDENTITY
> IDENTITY
```sql
    CREATE TABLE table_name(
    column1 int IDENTITY(1,1),
    --or
    column1 int IDENTITY,
    )
```
## SUM()
> The SUM() function calculates the sum of a set of values.
```sql
    SUM()
``` 
## MIN()
> The MIN() function returns the minimum value in a set of values.
```sql
    MIN()
```
## MAX()
> The MAX() function returns the maximum value in a set of values.
```sql
    MAX()
```
## COUNT()
> The COUNT() function returns the number of records returned by a select query.
```sql
    COUNT()
```
## AVG()
> The AVG() function returns the average value of an expression.
```sql
    AVG()
```
## STDEV()
> standard deviation
```sql
    STDEV()
```
## VAR()
> variance
```sql
    VAR()
```
## ROUND()
> The ROUND() function rounds a number to a specified number of decimal places.
```sql
    ROUND()
```
## FLOOR()
> The FLOOR() function returns the largest integer value that is smaller than or equal to a number.
```sql
    FLOOR()
```
## ABS()
> The ABS() function returns the absolute value of a number.
```sql
    ABS()
```
## RAND()
> Return a random decimal number (no seed value - so it returns a completely random number >= 0 and <1):
```sql
    RAND()
```
## EXP()
> The EXP() function returns e raised to the power of a specified number.
```sql
    EXP()
```
## PI()
> The PI() function returns the value of PI.
```sql
    PI()
```
## SIN()
> The SIN() function returns the sine of a number.
```sql
    SIN()
```
## COS()
> The COS() function returns the cosine of a number.
```sql
    COS()
```
## SQUARE()
> The SQUARE() function returns the square of a number.
```sql
    SQUARE()
```
## SQRT()
> The SQRT() function returns the square root of a number.
```sql
    SQRT()
```
## TAN()
> The TAN() function returns the tangent of a number.
```sql
    TAN()
```
## LOG()
> The LOG() function returns the natural logarithm of a specified number, or the logarithm of the number to the specified base.
```sql
    LOG()
```
## DATEADD()
> Add one year to a date, then return the date:
```sql
    SELECT DATEADD(year, 1, '2017/08/25') AS DateAdd;
```
## DATEDIFF()
>  Return the difference between two date values, in years:
```sql
    SELECT DATEDIFF(year, '2017/08/25', '2011/08/25') AS DateDiff;
```
## DATENAME()
>  Return a specified part of a date:
```sql
     SELECT DATENAME(year, '2017/08/25') AS DatePartString;
```
## MONTH()
>  Return the month part of a date:
```sql
    SELECT MONTH('2017/08/25') AS Month; 
```
## YEAR()
>  Return the year part of a date:
```sql
    SELECT YEAR('2017/08/25') AS YEAR; 
```
## DAY()
>  Return the day part of a date:
```sql
    SELECT DAY('2017/08/25') AS DAY; 
```
## GETDATE()
>  Return the current database system date and time:
```sql
    SELECT GETDATE(); 
```
## GETUTCDATE()
>  Return the current UTC date and time:
```sql
     SELECT GETUTCDATE();
```
## SYSDATETIME()
>  Return the date and time of the SQL Server:
```sql
     SELECT SYSDATETIME() AS SysDateTime;
```