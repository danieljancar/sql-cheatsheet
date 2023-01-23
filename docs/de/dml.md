# Datenmanipulierungssprache
> DML ist eine Computerprogrammiersprache zum Abrufen, Bearbeiten und Aktualisieren von Daten in einer relationalen Datenbank. Beispiele für DML-Anweisungen sind SELECT, INSERT, UPDATE und DELETE. Diese Anweisungen ermöglichen es Benutzern, die Datenbank nach bestimmten Informationen abzufragen, neue Daten zur Datenbank hinzuzufügen, vorhandene Daten zu ändern und unerwünschte Daten zu löschen. DML wird normalerweise in Verbindung mit DDL-Anweisungen (Data Definition Language) verwendet, die zum Erstellen und Ändern der Struktur einer Datenbank verwendet werden, z. B. zum Erstellen von Tabellen und zum Herstellen von Beziehungen zwischen ihnen.
## INSERT
Die INSERT-Anweisung wird verwendet, um neue Daten in eine Tabelle in der Datenbank einzufügen. Es ermöglicht dem Benutzer, die Spalten und Werte der neuen einzufügenden Daten anzugeben.
> Mit diesem Befehl werden neue Daten in eine Tabelle eingefügt
```SQL
    INSERT INTO Tabellenname (Spalte1, Spalte2, ...)
    WERTE (Wert1, Wert2, ...);
```
> Dieser Befehl wird verwendet, um mehrere neue Daten in eine Tabelle einzufügen
```SQL
    INSERT INTO table_name VALUES
    (Spalte1-Wert1, Spalte1-Wert2),
    (Spalte2-Wert1, Spalte2-Wert2);
```
## UPDATE
Die UPDATE-Anweisung wird verwendet, um vorhandene Daten in einer Tabelle zu ändern. Es ermöglicht dem Benutzer anzugeben, welche Spalten und Werte aktualisiert werden sollen, und die Bedingung, um auszuwählen, welche Zeilen aktualisiert werden sollen.
> Dieser Befehl wird verwendet, um vorhandene Daten in einer Tabelle zu aktualisieren
```SQL
    UPDATE Tabellenname
    SET Spalte1 = Wert1, Spalte2 = Wert2, ...
    WHERE some_column = some_value;
```
## DELETE
Die DELETE-Anweisung wird verwendet, um Daten aus einer Tabelle zu löschen. Es ermöglicht dem Benutzer, die Bedingung anzugeben, um auszuwählen, welche Zeilen gelöscht werden sollen.
> Mit diesem Befehl werden Daten aus einer Tabelle gelöscht
```SQL
    DELETE FROM Tabellenname
    WHERE some_column = some_value;
```
## CASCADE
Die CASCADE-Option wird verwendet, um anzugeben, dass beim Löschen einer referenzierten Zeile in einer übergeordneten Tabelle alle entsprechenden Zeilen in einer untergeordneten Tabelle ebenfalls gelöscht werden.
> Dieser Befehl wird verwendet, um anzugeben, dass beim Aktualisieren einer referenzierten Zeile in einer übergeordneten Tabelle alle entsprechenden Zeilen in einer untergeordneten Tabelle ebenfalls aktualisiert werden
```SQL
    ALTER TABLE aTable WITH CHECK ADD CONSTRAINT FK_a_table FOREIGN KEY
    (fk_id) REFERENZEN bTable(id) ON UPDATE CASCADE;
```
> Dieser Befehl wird verwendet, um anzugeben, dass beim Löschen einer referenzierten Zeile in einer übergeordneten Tabelle alle entsprechenden Zeilen in einer untergeordneten Tabelle ebenfalls gelöscht werden
```SQL
    ALTER TABLE aTable WITH CHECK ADD CONSTRAINT FK_a_table FOREIGN KEY
    (fk_id) REFERENZEN bTable(id) ON DELETE CASCADE;
```
> Sie können sie auch kombinieren
```SQL
    ALTER TABLE aTable WITH CHECK ADD CONSTRAINT FK_a_table FOREIGN KEY
    (fk_id) REFERENZEN bTable(id) ON UPDATE CASCADE ON DELETE CASCADE;
```
## MERGE
Die MERGE-Anweisung wird verwendet, um Daten basierend auf einer Bedingung entweder zu aktualisieren oder in eine Tabelle einzufügen. Es ermöglicht dem Benutzer, eine Quelltabelle, die Bedingungen für das Aktualisieren und Einfügen sowie die zu verwendenden Spalten und Werte anzugeben.
> Dieser Befehl wird verwendet, um Daten basierend auf einer Bedingung entweder zu aktualisieren oder in eine Tabelle einzufügen
```SQL
    MERGE INTO Tabellenname
    USING (SELECT Spalte1, Spalte2, ... FROM source_table) Quelle
    EIN (Tabellenname.id = Quelle.id)
    BEI ÜBEREINSTIMMUNG DANN UPDATE SET Spalte1 = Quelle.Spalte1, ...
    WENN NICHT ÜBEREINSTIMMT, DANN EINFÜGEN (Spalte1, Spalte2, ...)
    WERTE (Quelle.Spalte1, Quelle.Spalte2, ...);
```