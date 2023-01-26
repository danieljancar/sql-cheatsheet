# Data Backup
> Data backup is the process of creating a copy of important data and storing it in a separate location for safekeeping. The purpose of data backup is to ensure that the data can be restored in case of a data loss event, such as a hardware failure, software corruption, cyber attack or natural disaster.

## Restore Database 
> This command is used to restore a database (f.x a .bak file)
```sql
    use master
    RESTORE DATABASE db_name FROM DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL15.SQLEXPRESS\MSSQL\Backup\db_name.bak'
```
## Backup Database
> This creates a backup of your database.
```sql
    BACKUP DATABASE [DB_name]
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\Backup\WideWorldImporters.bak' 
    WITH NOFORMAT, NOINIT, NAME = N'WideWorldImporters vollständige Datenbanksicherung', SKIP, STATS = 10
    GO
```
## Full Backup with Powershell (local)
> This command in Powershell creates a backup of a database.
```sql
    $credential = Get-Credential

    Backup-SqlDatabase -ServerInstance Computer[\Instance] -Database <myDatabase> -BackupAction Database -Credential $credential
```
## Backup to a Disk Device
> This backs up your database to a disk device.
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
## Backup Encrypted Database
> This creates a encrypted backup of a database.
```sql
    -- Create the master key
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe';  

    -- If the master key already exists, open it in the same session that you create the certificate (see next step)
    OPEN MASTER KEY DECRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe'

    -- Create the certificate encrypted by the master key
    CREATE CERTIFICATE MyCertificate
    WITH SUBJECT = 'Backup Cert', EXPIRY_DATE = '20201031';  
```

Find additional information [here](https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases?view=sql-server-ver16).