# Data Security
> Datensicherheit bezieht sich auf den Schutz digitaler Informationen und Systeme vor unbefugtem Zugriff, Verwendung, Offenlegung, Störung, Veränderung oder Zerstörung. Es umfasst eine Vielzahl von Maßnahmen und Technologien, die zum Schutz sensibler und vertraulicher Informationen eingesetzt werden.
## AUTHENTICATION
Authentifizierung ist der Prozess der Überprüfung der Identität eines Benutzers. Im Kontext der Datensicherheit wird es verwendet, um sicherzustellen, dass nur autorisierte Benutzer auf bestimmte Datenbanken oder Tabellen zugreifen können. Die CREATE USER-Anweisung wird verwendet, um einen neuen Benutzer mit einem angegebenen Kennwort zu erstellen, und die GRANT-Anweisung wird verwendet, um diesem Benutzer Zugriff auf eine bestimmte Datenbank oder Tabelle zu gewähren.
> Dieser Befehl wird verwendet, um einen neuen Benutzer mit einem bestimmten Passwort zu erstellen
```sql
    CREATE USER user_name IDENTIFIED BY 'password';
```
> Dieser Befehl wird verwendet, um einem Benutzer Zugriff auf eine bestimmte Datenbank oder Tabelle zu gewähren
```sql
    GRANT SELECT, INSERT, UPDATE, DELETE ON table_name TO user_name;
```
## AUTHORIZATION
Autorisierung ist der Prozess des Gewährens oder Widerrufens des Zugriffs auf bestimmte Ressourcen basierend auf der Rolle oder Berechtigungsebene eines Benutzers. Die REVOKE-Anweisung wird verwendet, um den Zugriff eines Benutzers auf eine bestimmte Datenbank oder Tabelle zu widerrufen.
> Dieser Befehl wird verwendet, um den Zugriff eines Benutzers auf eine bestimmte Datenbank oder Tabelle zu widerrufen
```sql
    REVOKE SELECT, INSERT, UPDATE, DELETE ON table_name FROM user_name;
```
## ROW LEVEL SECURITY
Sicherheit auf Zeilenebene ist eine Funktion, mit der Sie den Zugriff auf bestimmte Zeilen in einer Tabelle basierend auf der Rolle oder Berechtigungsebene eines Benutzers einschränken können. Die CREATE POLICY-Anweisung wird verwendet, um eine Richtlinie zu erstellen, die den Zugriff auf bestimmte Zeilen in einer Tabelle basierend auf der Rolle eines Benutzers einschränkt.
> Dieser Befehl wird verwendet, um eine Richtlinie zu erstellen, die den Zugriff auf bestimmte Zeilen in einer Tabelle basierend auf der Rolle eines Benutzers einschränkt
```sql
    CREATE POLICY policy_name ON table_name
    FOR SELECT
    WITH CHECK (condition)
```
## DYNAMIC DATA MASKING
Die dynamische Datenmaskierung ist eine Funktion, mit der Sie vertrauliche Daten in einer Tabelle maskieren können. Die ALTER TABLE-Anweisung wird verwendet, um einer bestimmten Spalte in einer Tabelle eine Maskierungsfunktion hinzuzufügen.
> Dieser Befehl wird verwendet, um sensible Daten in einer Tabelle zu maskieren
```sql
    ALTER TABLE table_name
    ADD MASKED WITH (FUNCTION = 'masking_function')
    FOR COLUMN sensitive_column;
```
## ENCRYPTION
Verschlüsselung ist der Prozess der Umwandlung von Klartext in ein unlesbares Format, um ihn vor unbefugtem Zugriff zu schützen. Die ALTER TABLE-Anweisung wird verwendet, um einer bestimmten Spalte in einer Tabelle Verschlüsselung hinzuzufügen.
> Dieser Befehl wird verwendet, um eine bestimmte Spalte in einer Tabelle zu verschlüsseln
```sql
    ALTER TABLE table_name
    ALTER COLUMN sensitive_column
    ADD ENCRYPTION (TYPE = Deterministic, ALGORITHM = 'AEAD_AES_256_CBC_HMAC_SHA_256');
```