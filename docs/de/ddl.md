# Datendefinitionssprache
> DDL ist eine Teilmenge von SQL (Structured Query Language), die verwendet wird, um die Struktur einer relationalen Datenbank zu definieren. DDL-Anweisungen werden zum Erstellen, Ändern und Löschen von Datenbankobjekten wie Tabellen, Ansichten, Indizes und Einschränkungen verwendet.
## Informationen
Das Informationskapitel dient dazu, bestimmte Informationen über SQL herauszugeben.
> Dieser Befehl wird verwendet, um den eigenen Namen in einer bestimmten Tabelle auszugeben.
```SQL
    SELECT „Ihr_Name“ AS „Mein Name“
```
## EXEC
Der EXEC-Befehl wird verwendet, um die Namen in SQL zu ändern
> Dieser Befehl wird verwendet, um den Namen in einer bestimmten Spalte oder Tabelle zu ändern.
```SQL
    EXEC sp_rename 'schema_name', 'descripton', 'COLUMN';
```
> Dieser Befehl wird verwendet, um die Informationen in einer bestimmten Tabelle anzuzeigen.
```SQL
    EXEC sp_columns Tabellenname
```
## CREATE
Der Befehl CREATE wird verwendet, um eine neue Tabelle mit angegebenen Spalten und Datentypen zu erstellen. Der Tabellenname, die Spaltennamen und die Datentypen müssen innerhalb des Befehls definiert werden.
> Dieser Befehl wird verwendet, um eine neue Tabelle mit bestimmten Spalten und Datentypen zu erstellen
```SQL
    CREATE TABLE Tabellenname (
    Spalte1 Datentyp constraint,
    Spalte2 Datentyp constraint,
    );
```
## ALTER
Der Befehl ALTER wird verwendet, um Änderungen an einer vorhandenen Tabelle vorzunehmen, z. B. eine neue Spalte hinzuzufügen, eine vorhandene Spalte zu ändern oder eine Spalte zu löschen.
> Dieser Befehl wird verwendet, um einer bestehenden Tabelle eine neue Spalte hinzuzufügen
```SQL
    ALTER TABLE table_name
    ADD column_name data_type constraint;
```
> Dieser Befehl wird verwendet, um eine vorhandene Spalte in einer Tabelle zu ändern
```SQL
    ALTER TABLE table_name
    MODIFY column_name data_type constraint;
```

> Dieser Befehl wird verwendet, um eine Spalte aus einer bestehenden Tabelle zu löschen
```SQL
    ALLTER TABLE table_name
    DROP COLUMN column_name;
```
## DROP
Der DROP-Befehl wird verwendet, um eine bestehende Tabelle, ihre Struktur und alle ihre Daten dauerhaft aus der Datenbank zu löschen. Es kann auch verwendet werden, um andere Datenbankobjekte wie Ansichten, Indizes und Sequenzen zu löschen. Sobald eine Tabelle gelöscht wird, gehen alle darin gespeicherten Daten verloren und können nicht wiederhergestellt werden. Es ist wichtig, diesen Befehl mit Vorsicht zu verwenden, da er nicht rückgängig gemacht werden kann.
> Dieser Befehl wird verwendet, um eine bestehende Tabelle und alle ihre Daten zu löschen
```SQL
    DROP TABLE Tabellenname;
```
## TRUNCATE
Der TRUNCATE-Befehl wird verwendet, um alle Daten aus einer vorhandenen Tabelle zu löschen, behält jedoch die Tabellenstruktur und die zugehörigen Objekte wie Indizes, Trigger und Einschränkungen bei. Im Gegensatz zum DROP-Befehl generiert TRUNCATE keine Rückgängig-Protokolle, wodurch es für große Tabellen mit vielen Zeilen schneller und effizienter wird. Es löst jedoch auch keine DELETE-Trigger aus, und die gelöschten Daten können nicht wiederhergestellt werden. Es ist wichtig, diesen Befehl mit Vorsicht zu verwenden, da er nicht rückgängig gemacht werden kann.
> Dieser Befehl wird verwendet, um alle Daten aus einer bestehenden Tabelle zu löschen, behält aber die Tabellenstruktur bei
```SQL
    TRUNCATE TABLE Tabellenname;
```
## SQL-SCHLÜSSEL
In SQL werden Schlüssel verwendet, um Beziehungen zwischen Tabellen in einer Datenbank herzustellen und durchzusetzen. Es gibt zwei Haupttypen von Schlüsseln: Primärschlüssel und Fremdschlüssel.
**Primärschlüssel**
Ein Primärschlüssel ist eine eindeutige Kennung für jede Zeile in einer Tabelle. Es wird verwendet, um die Integrität der Daten zu erzwingen und sicherzustellen, dass es keine doppelten Werte in der Tabelle gibt. Für eine Tabelle kann nur ein Primärschlüssel definiert werden, der keine Nullwerte enthalten darf. Der Primärschlüssel wird mit der PRIMARY KEY-Einschränkung definiert.
> Dieser Befehl wird verwendet, um eine Spalte oder einen Satz von Spalten als Primärschlüssel für eine Tabelle anzugeben
```SQL
    PRIMARY KEY (Spalte1, Spalte2, ...)
```
**Foreignschlüssel**
Ein Fremdschlüssel ist eine Spalte oder eine Gruppe von Spalten in einer Tabelle, die verwendet wird, um eine Verknüpfung zwischen den Daten in zwei Tabellen herzustellen. Der Fremdschlüssel referenziert einen Primärschlüssel in einer anderen Tabelle und stellt eine Verknüpfung zwischen den beiden Tabellen her. Dieser Link wird verwendet, um die referenzielle Integrität zu erzwingen, wodurch sichergestellt wird, dass die Daten in den zugehörigen Tabellen konsistent sind und keine verwaisten Datensätze vorhanden sind. Der Fremdschlüssel wird mit der Einschränkung FOREIGN KEY definiert.
> Dieser Befehl wird verwendet, um eine Fremdschlüsseleinschränkung für eine Spalte in einer Tabelle anzugeben
```SQL
    FOREIGN KEY (Spalte) REFERENCES referenced_table(referenced_column)
```
Zusammenfassend werden Primärschlüssel verwendet, um jeden Datensatz in einer Tabelle eindeutig zu identifizieren, und Fremdschlüssel werden verwendet, um Verknüpfungen zwischen Tabellen herzustellen, um die Datenintegrität und -konsistenz sicherzustellen.