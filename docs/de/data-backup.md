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
## Backup Datenbank
> Diese Kommands erstellen ein Backup deiner Datenbank.
```sql
    BACKUP DATABASE [DB_name]
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\Backup\WideWorldImporters.bak' 
    WITH NOFORMAT, NOINIT, NAME = N'WideWorldImporters vollständige Datenbanksicherung', SKIP, STATS = 10
    GO
```

## Komplettes Backup mit Powershell (lokal)
> Erstellt ein Backup deiner Datenbank mit Powershell.
```sql
    $credential = Get-Credential

    Backup-SqlDatabase -ServerInstance Computer[\Instance] -Database <myDatabase> -BackupAction Database -Credential $credential
```
## Backup auf ein Festplattengerät
> This backs up your database to a disk device
```sql
    USE SQLTestDB;
    GO
    BACKUP DATABASE SQLTestDB
    TO DISK = 'c:\tmp\SQLTestDB.bak'
    WITH FORMAT,
        MEDIANAME = 'SQLServerBackups',
        NAME = 'Full Backup of SQLTestDB';
    GO
```
## Ein verschlüsseltes Backup erstellen
> This creates a encrypted backup of a database
```sql
    -- Create the master key
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe';  

    -- If the master key already exists, open it in the same session that you create the certificate (see next step)
    OPEN MASTER KEY DECRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe'

    -- Create the certificate encrypted by the master key
    CREATE CERTIFICATE MyCertificate
    WITH SUBJECT = 'Backup Cert', EXPIRY_DATE = '20201031';  
```

Mehr Informationen [hier](https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases?view=sql-server-ver16).