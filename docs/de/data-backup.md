# Daten Backup
> Datensicherung ist der Vorgang, bei dem eine Kopie wichtiger Daten erstellt und zur sicheren Aufbewahrung an einem separaten Ort gespeichert wird. Der Zweck der Datensicherung besteht darin, sicherzustellen, dass die Daten im Falle eines Datenverlustereignisses wie Hardwareausfall, Softwarebeschädigung, Cyberangriff oder Naturkatastrophe wiederhergestellt werden können.

## Datenbank Wiederherstellen
> Dieser Befehl wird verwendet, um eine Datenbank wiederherzustellen (z. B. eine .bak-Datei)
```sql
USE [master]
RESTORE DATABASE [dbname] 
FROM  DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\Backup\dbname.bak' 
WITH  FILE = 1,  
MOVE N'dbname' TO N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\DATA\dbname.mdf',  
MOVE N'dbname_log' TO N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\DATA\dbname_log.ldf',  NOUNLOAD,  STATS = 5
```