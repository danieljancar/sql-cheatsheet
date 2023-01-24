# Datensicherheit
> Datensicherheit bezieht sich auf den Schutz digitaler Informationen und Systeme vor unbefugtem Zugriff, Verwendung, Offenlegung, Störung, Veränderung oder Zerstörung. Es umfasst eine Vielzahl von Maßnahmen und Technologien, die zum Schutz sensibler und vertraulicher Informationen eingesetzt werden.
## AUTHENTIFIZIERUNG
Authentifizierung ist der Prozess der Überprüfung der Identität eines Benutzers. Im Kontext der Datensicherheit wird es verwendet, um sicherzustellen, dass nur autorisierte Benutzer auf bestimmte Datenbanken oder Tabellen zugreifen können. Die CREATE USER-Anweisung wird verwendet, um einen neuen Benutzer mit einem angegebenen Kennwort zu erstellen, und die GRANT-Anweisung wird verwendet, um diesem Benutzer Zugriff auf eine bestimmte Datenbank oder Tabelle zu gewähren.
> Dieser Befehl wird verwendet, um einen neuen Benutzer mit einem festgelegten Passwort zu erstellen
> Normalerweise müssen Sie die Master-Datenbank verwenden, um etwas mit Benutzern zu tun ```use master```
```SQL
    USE master;
    CREATE LOGIN login_name
    WITH PASSWORD = 'passwort', CHECK_POLICY = OFF;
```
> Melden Sie sich für einen bestimmten Benutzer an
```SQL
    USE myDatabase;
    CREATE USER user_name FOR LOGIN login_name;
```
> Dieser Befehl wird verwendet, um einem Benutzer Zugriff auf eine bestimmte Datenbank oder Tabelle zu gewähren
```SQL
    GRANT SELECT, INSERT, UPDATE, DELETE ON table_name TO user_name;
```
## AUTORISIERUNG
Autorisierung ist der Prozess des Gewährens oder Widerrufens des Zugriffs auf bestimmte Ressourcen basierend auf der Rolle oder Berechtigungsebene eines Benutzers. Die REVOKE-Anweisung wird verwendet, um den Zugriff eines Benutzers auf eine bestimmte Datenbank oder Tabelle zu widerrufen.
> Weisen Sie dem Login eine Serverrolle zu
```sql
    USE master;
    ALTER SERVER ROLE role_name ADD MEMBER login_name;
```
> Dem Login eine Serverrolle entziehen
```SQL
    ALTER SERVER ROLE role_name DROP MEMBER login_name;
```
> Weisen Sie dem Benutzer eine Datenbankrolle zu
```SQL
    USE mydatabase;
    ALTER ROLE role_name ADD MEMBER user_name;
```
> Dem Benutzer eine Rolle entziehen
```SQL
    ALTER ROLE Rollenname DROP MEMBER Benutzername;
```
> Dieser Befehl wird verwendet, um den Zugriff eines Benutzers auf eine bestimmte Datenbank oder Tabelle zu widerrufen
```SQL
    REVOKE SELECT, INSERT, UPDATE, DELETE ON table_name FROM user_name;
```
## SICHERHEIT AUF ZEILENEBENE
Sicherheit auf Zeilenebene ist eine Funktion, mit der Sie den Zugriff auf bestimmte Zeilen in einer Tabelle basierend auf der Rolle oder Berechtigungsebene eines Benutzers einschränken können. Die CREATE POLICY-Anweisung wird verwendet, um eine Richtlinie zu erstellen, die den Zugriff auf bestimmte Zeilen in einer Tabelle basierend auf der Rolle eines Benutzers einschränkt.
> Dieser Befehl wird verwendet, um eine Richtlinie zu erstellen, die den Zugriff auf bestimmte Zeilen in einer Tabelle basierend auf der Rolle eines Benutzers einschränkt
```sql
    CREATE POLICY policy_name ON table_name
    FOR SELECT
    WITH CHECK (condition)
```
## DYNAMISCHE DATENMASKEN
Die dynamische Datenmaskierung ist eine Funktion, mit der Sie vertrauliche Daten in einer Tabelle maskieren können. Die ALTER TABLE-Anweisung wird verwendet, um einer bestimmten Spalte in einer Tabelle eine Maskierungsfunktion hinzuzufügen.
> Dieser Befehl wird verwendet, um sensible Daten in einer Tabelle zu maskieren
```sql
    ALTER TABLE table_name
    ADD MASKED WITH (FUNCTION = 'masking_function')
    FOR COLUMN sensitive_column;
```
## VERSCHLÜSSELUNG
Verschlüsselung ist der Prozess der Umwandlung von Klartext in ein unlesbares Format, um ihn vor unbefugtem Zugriff zu schützen. Die ALTER TABLE-Anweisung wird verwendet, um einer bestimmten Spalte in einer Tabelle Verschlüsselung hinzuzufügen.
> Dieser Befehl wird verwendet, um eine bestimmte Spalte in einer Tabelle zu verschlüsseln
```sql
    ALTER TABLE table_name
    ALTER COLUMN sensitive_column
    ADD ENCRYPTION (TYPE = Deterministic, ALGORITHM = 'AEAD_AES_256_CBC_HMAC_SHA_256');
```