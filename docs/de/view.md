# Aufrufe
> Eine Ansicht in einer relationalen Datenbank ist eine virtuelle Tabelle, die auf dem Ergebnis einer SELECT-Anweisung basiert. Es speichert selbst keine Daten, sondern bietet eine Möglichkeit, auf bestimmte Weise auf Daten aus einer oder mehreren Tabellen zuzugreifen. Ansichten können verwendet werden, um komplexe Abfragen zu vereinfachen, den Zugriff auf bestimmte Spalten einer Tabelle einzuschränken oder Daten in einem bestimmten Format darzustellen.
## CREATE VIEW
Die CREATE VIEW-Anweisung wird verwendet, um eine neue virtuelle Tabelle basierend auf dem Ergebnis einer SELECT-Anweisung zu erstellen. Es ermöglicht dem Benutzer, den Namen der Ansicht und die SELECT-Anweisung anzugeben, die die Ansicht definiert.
> Dieser Befehl wird verwendet, um eine virtuelle Tabelle basierend auf dem Ergebnis einer SELECT-Anweisung zu erstellen
```sql
    CREATE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
```
## QUERY VIEW
Die Anweisung SELECT VIEW wird verwendet, um Daten aus einer Ansicht abzufragen. Es ermöglicht dem Benutzer, die abzurufenden Spalten und alle Bedingungen zum Filtern der Daten anzugeben.
> Mit diesem Befehl werden Daten aus einer Ansicht abgefragt
```sql
    SELECT column1, column2, ...
    FROM view_name;
```
## EDIT VIEW / REPLACE VIEW
Die CREATE OR REPLACE VIEW-Anweisung wird verwendet, um die SELECT-Anweisung einer vorhandenen Ansicht zu ändern. Es ermöglicht dem Benutzer, die SELECT-Anweisung, die die Ansicht definiert, zu bearbeiten und zu aktualisieren, ohne die Ansicht löschen und neu erstellen zu müssen.
> Dieser Befehl wird verwendet, um die SELECT-Anweisung einer Ansicht zu ändern
```sql
    CREATE OR REPLACE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
```
## DROP VIEW
Die DROP VIEW-Anweisung wird verwendet, um eine Ansicht zu löschen. Es ermöglicht dem Benutzer, eine virtuelle Tabelle aus der Datenbank zu entfernen.
> Dieser Befehl dient zum Löschen einer Ansicht
```SQL
    DROP VIEW view_name;
```