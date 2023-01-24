# Transaktionen
> In SQL ist eine Transaktion eine Folge von einer oder mehreren Datenbankoperationen, die als einzelne logische Arbeitseinheit ausgeführt werden. Diese Operationen können das Einfügen, Aktualisieren oder Löschen von Daten umfassen und sich über mehrere Tabellen und/oder Zeilen erstrecken. Durch Transaktionen wird sichergestellt, dass die Datenbank auch bei Fehlern oder Systemausfällen in einem konsistenten Zustand bleibt. Sie bieten auch eine Möglichkeit, Änderungen bei Bedarf rückgängig zu machen oder rückgängig zu machen. Transaktionen werden normalerweise mit den Anweisungen BEGIN, COMMIT und ROLLBACK verwaltet.

## Merkmale von Transaktionen
Die Anweisungen werden nach dem ACID-Prinzip ausgeführt:

- Atomarität (Atomicity): „Alles oder nichts“ wird ausgeführt und gespeichert, nur ein Teil ist nicht möglich.
- Konsistenz (Consistency): Vor und nach der Transaktion sind die Daten konsistent, das heißt widerspruchsfrei und korrekt.
- Isolation (Isolation): Änderungen werden erst gespeichert und sind für andere Benutzer sichtbar, wenn die Transaktion abgeschlossen ist. Während der Transaktion sind die betroffenen Daten für andere gesperrt.
- Dauerhaftigkeit (Durability): Die Änderungen bleiben nach der Transaktion dauerhaft in der Datenbank gespeichert.

Transaktionen sollten aufgrund der Sperren so kurz wie möglich sein und daher möglichst wenig SQL-Code enthalten. Es besteht die Möglichkeit des Zurücksetzens (Rollback), wenn ein Fehler auftritt oder die Transaktion unterbrochen wird. Dies ist ein implizites Zurücksetzen auf den Zustand vor der Transaktion.

Für den Undo-Vorgang wird ein Logbuch geführt, auch Transaktionslog genannt. Es ist logisch aufgebaut, besteht aus Anweisungen und nicht aus Zuständen.

## Transaktionscode-Beispiel
> Diese Transaktion führt die Befehle virtuell aus und führt sie nur in der "echten" Datenbank aus, sobald der TRY fehlerfrei ausgeführt wird. Wenn TRY fehlschlägt, geht es zu CATCH und ROLLBACK der Transaktion.
```sql¨
BEGIN TRANSACTION 

    BEGIN TRY
        UPDATE example set name = 'Max' where exampleId = 1 
        DELETE from example where example = 7
    END TRY 

    BEGIN CATCH
        ROLLBACK TRANSACTION
    END CATCH

COMMIT TRANSACTION
```