# Data Backup
> Data backup is the process of creating a copy of important data and storing it in a separate location for safekeeping. The purpose of data backup is to ensure that the data can be restored in case of a data loss event, such as a hardware failure, software corruption, cyber attack or natural disaster.

## Restore Database 
> This command is used to restore a database (f.x a .bak file)
```sql
USE [master]
RESTORE DATABASE [dbname] 
FROM  DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\Backup\dbname.bak' 
WITH  FILE = 1,  
MOVE N'dbname' TO N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\DATA\dbname.mdf',  
MOVE N'dbname_log' TO N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\DATA\dbname_log.ldf',  NOUNLOAD,  STATS = 5
```