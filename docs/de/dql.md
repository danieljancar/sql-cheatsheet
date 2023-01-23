# Datenabfragesprache
> Data Query Language (DQL) wird verwendet, um Daten aus einer relationalen Datenbank abzurufen. DQL-Anweisungen werden verwendet, um Daten aus einer oder mehreren Tabellen innerhalb einer Datenbank auszuwählen und abzurufen. Beispiele für DQL-Anweisungen sind SELECT, GET und READ. Diese Anweisungen ermöglichen es Benutzern, die Datenbank nach bestimmten Informationen abzufragen und die Daten in einem strukturierten Format abzurufen. DQL-Anweisungen werden normalerweise von Endbenutzern verwendet, um auf Daten aus der Datenbank zuzugreifen und sie abzurufen, und werden nicht verwendet, um Änderungen an der Datenbankstruktur oder den Daten vorzunehmen. DQL-Anweisungen werden vom Datenbankverwaltungssystem (DBMS) ausgeführt und die Ergebnisse werden dem Benutzer in Form einer Tabelle oder eines anderen strukturierten Formats zurückgegeben.
## SELECT
Die SELECT-Anweisung wird verwendet, um Daten aus einer oder mehreren Tabellen in einer Datenbank abzufragen.
> Mit diesem Befehl selektieren Sie alle Spalten einer Tabelle
```SQL
    SELECT * FROM Tabellenname;
```
> Dieser Befehl wird verwendet, um bestimmte Spalten aus einer Tabelle auszuwählen
```SQL
    SELECT Spalte1, Spalte2, ... FROM Tabellenname;
```
## AS
Die AS-Anweisung hat die Möglichkeit, Spalten oder Tabellen für die Abfrage umzubenennen und somit mit Ersatznamen zu versehen. Beachten Sie, dass die Aliase für die gesamte Abfrage gelten, was bedeutet, dass Sie sie dann in der gesamten Abfrage konsistent verwenden müssen.
> Dieser Befehl wird verwendet, um Spalten einer Abfrage umzubenennen.
```SQL
    SELECT Spalte1 Gesamt AS Tabelle1;
```
## DISTINCT
Die DISTINCT-Anweisung wird verwendet, um sicherzustellen, dass identische Werte nur einmal in einer Tabelle vorkommen.
> Dieser Befehl wird verwendet, um Werte nur einmal anzuzeigen.
```SQL
    SELECT DISTINCT table_name FROM column_name;
```
## ORDER BY
Die Anweisung ORDER BY dient zum Sortieren von Datentypen, z. B. alle numerischen Datentypen oder Datumswerte. Textfelder können auch sortiert werden.
> Dieser Befehl wird verwendet, um Datenwerte einer bestimmten Tabelle zu sortieren.
```SQL
    SELECT Spaltenname1, Spaltenname2 FROM Tabellenname ORDER BY Spaltenname2;
```
> Dieser Befehl wird verwendet, um mehrere Datenwerte einer bestimmten Tabelle zu sortieren.
```SQL
    SELECT Spaltenname1, Spaltenname2 FROM Tabellenname ORDER BY Spaltenname1, Spaltenname2;
```
## TOP
Die TOP-Anweisung wird verwendet, um nur eine bestimmte Anzahl von Werten in einer Tabelle anzuzeigen.
> Dieser Befehl wird verwendet, um nur 10 Werte in einer Tabelle anzuzeigen und sie zu sortieren.
```SQL
    SELECT TOP 10 spaltenname AS 'neuertabellenname' FROM tabellenname ORDER BY spaltenname DESC
```
## CONCAT
Die CONCAT-Anweisung wird verwendet, um mehrere Datentabellen in einer Datenbank zu kombinieren.
> Dieser Befehl wird verwendet, um alle Spalten einer Tabelle zu einem Datum zusammenzufassen.
```SQL
    SELECT Spalte1, CONCAT (Spalte2, Spalte3) AS newtable_name FROM table_name;
```
## WHERE
Die WHERE-Klausel wird verwendet, um Daten basierend auf einer bestimmten Bedingung zu filtern.
> Dieser Befehl wird verwendet, um alle Spalten einer Tabelle auszuwählen, bei denen eine bestimmte Spalte gleich einem bestimmten Wert ist.
```SQL
    SELECT * FROM Tabellenname
    WHERE Spaltenname = Wert;
```
## CASE
Die CASE-Anweisung wird verwendet, um eine Reihe von Bedingungen auszuwerten und basierend auf dem Ergebnis einen bestimmten Wert zurückzugeben.
> Dieser Befehl wird verwendet, um eine Spalte auszuwählen und basierend auf dem Wert einer anderen Spalte eine neue Spalte zuzuweisen
```SQL
    SELECT-Spalte1,
    CASE-Spalte2
    WHERE Wert1 THEN 'neuer_Wert1'
    WHERE Wert2 THEN 'neuer_Wert2'
    ELSE 'neuer_wert3'
    END AS neue_Spalte
    FROM Tabellenname;
```
## INNER JOIN
Sie können eine INNER JOIN-Operation in jeder FROM-Klausel verwenden. Dies ist die häufigste Art der Verknüpfung. Inner Joins kombinieren Datensätze aus zwei Tabellen, wenn übereinstimmende Werte in einem Feld vorhanden sind, das beiden Tabellen gemeinsam ist. Sie können INNER JOIN mit den Tabellen „Departments“ und „Employees“ verwenden, um alle Mitarbeiter in jeder Abteilung auszuwählen. Der EIN-Zustand wird verwendet, um die FOREIGN KEYS zu vergleichen.
> Mit dem INNER JOIN können Sie zwei Tabellen miteinander darstellen.
```SQL
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable INNER JOIN btable ON atable.column2 = btable.column2;
```
## LEFT  JOIN
Der LEFT JOIN in SQL gibt grundsätzlich alle Datensätze aus der linken Tabelle und die übereinstimmenden Datensätze aus den rechten Tabellen zurück. Angenommen, wir haben zwei Tabellen, Tabelle A und Tabelle B. Wenn LEFT JOIN auf diese beiden Tabellen angewendet wird, werden alle Datensätze aus Tabelle A und nur die übereinstimmenden Datensätze aus Tabelle B angezeigt. Der EIN-Zustand wird verwendet, um die FOREIGN KEYS zu vergleichen.
> Mit dem LEFT JOIN können Sie zwei Tabellen miteinander darstellen.
```SQL
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable LEFT JOIN btable ON atable.column2 = btable.column2;
```
## RIGHT JOIN
Der RIGHT JOIN in SQL gibt grundsätzlich alle Datensätze aus der richtigen Tabelle und die übereinstimmenden Datensätze aus den richtigen Tabellen zurück. Angenommen, wir haben zwei Tabellen, Tabelle B und Tabelle B. Wenn RIGHT JOIN auf diese beiden Tabellen angewendet wird, werden alle Datensätze aus Tabelle A und nur die übereinstimmenden Datensätze aus Tabelle A angezeigt. Der EIN-Zustand wird verwendet, um die FOREIGN KEYS zu vergleichen.
> Mit dem RIGHT JOIN können Sie zwei Tabellen miteinander darstellen.
```SQL
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable RIGHT JOIN btable ON atable.column2 = btable.column2;
```
## FULL JOIN
Der FULL JOIN ist der RIGHT JOIN und der LEFT JOIN gemischt, sodass alle Datensätze angezeigt werden.
> Mit dem FULL JOIN können Sie zwei Tabellen miteinander darstellen.
```SQL
    SELECT atable.column1, btable.column1, atable.column2, btable.column2
    FROM atable FULL JOIN btable ON atable.column2 = btable.column2;
```
## SELF JOIN
Ein Self-Join ist ein Join, der verwendet werden kann, um eine Tabelle mit sich selbst zu verknüpfen. Es handelt sich also um eine unäre Relation. Bei einem Self-Join wird jede Zeile der Tabelle mit sich selbst und allen anderen Zeilen derselben Tabelle verknüpft. Daher wird ein Self-Join hauptsächlich verwendet, um die Zeilen derselben Tabelle in der Datenbank zu kombinieren und zu vergleichen.
> Mit dem SELF JOIN können Sie zwei Tabellen miteinander darstellen.
```SQL
    SELECT atable.column1, atable.column2, atable.column3, btable.column1 AS 'table1_name' AS 'table2_name'
    FROM table1 JOIN table2 ON atable.column1 = btable.column1;
```
## CROSS JOIN
CROSS JOIN ist zu verwenden, um viele Daten zu generieren.
> Mit dem CROSS JOIN können Sie zwei Tabellen miteinander darstellen und alle Daten werden gemischt.
```SQL
    SELECT * FROM btable CROSS JOIN atable;
    -- oder
    SELECT Spalte1, Spalte2, Spalte3 FROM btable, atable;
```
## GROUP BY
Die GROUP BY-Klausel wird verwendet, um Zeilen aus einer Tabelle basierend auf einer oder mehreren Spalten zu gruppieren.
> Dieser Befehl wird verwendet, um eine Spalte und die Anzahl ihrer distinkten Werte, gruppiert nach einer anderen Spalte, auszuwählen
```SQL
    SELECT Spalte1, COUNT(DISTINCT Spalte2)
    FROM Tabellenname
    GROUP BY Spalte1;
```
## HAVING
> Das Schlüsselwort HAVING kann nur in Kombination mit GROUP BY verwendet werden und dient dazu, die Ergebnisse von Aggregatfunktionen einzuschränken oder zu filtern.
```SQL
    SELECT table1 FROM-Spalte
    GROUP BY Tabelle1
    HAVING COUNT(*) > 100;
```
> HAVING wird nur verwendet, um die Aggregation zu filtern. Wenn Sie Datensätze vor dem Gruppieren filtern möchten, müssen Sie eine WHERE-Klausel entsprechend setzen. In der folgenden Abfrage fügen wir der obigen Aussage die Bedingung hinzu, dass die Personen älter als 18 Jahre sein müssen:
```SQL
    SELECT COUNT(id), table1 FROM column1
    WHERE ändern > 18
    GROUP BY Tabelle1
    HAVING COUNT(id) > 100;
```
## SUBQUERY
Die Unterabfrage ist eine Abfrage, die in einer anderen Abfrage verschachtelt ist. Es wird verwendet, um Daten aus einer Tabelle basierend auf den Ergebnissen einer anderen Tabelle abzurufen.
> Dieser Befehl wird verwendet, um alle Spalten aus einer Tabelle auszuwählen, bei denen eine bestimmte Spalte mit einem Wert übereinstimmt, der von einer Unterabfrage zurückgegeben wird
```SQL
    WÄHLEN Sie * AUS Tabelle1
    WHERE Spalte1 = (SELECT Spalte2 AUS Tabelle2)
```
## UNION
SET-Operationen werden verwendet, um das Ergebnis von zwei oder mehr SELECT-Anweisungen zu einem einzigen Ergebnis zu kombinieren.
> Dieser Befehl wird verwendet, um alle unterschiedlichen Werte aus zwei oder mehr Tabellen auszuwählen, die mit UNION kombiniert werden
```SQL
    SELECT column1 FROM table1
    UNION
    SELECT column1 FROM table2;
```
> Mit diesem Befehl werden alle Werte aus zwei oder mehr Tabellen selektiert, die mit UNION ALL kombiniert werden
```SQL
    SELECT column1 FROM table1
    UNION ALL
    SELECT column1 FROM table2;
```
## INTERSECT
> Mit diesem Befehl werden alle Werte ausgewählt, die sowohl in der ersten als auch in der zweiten Tabelle enthalten sind
```SQL
    SELECT column1 FROM table1
    INTERSECT
    SELECT column1 FROM table2;
```
## EXCEPT
> Dieser Befehl wird verwendet, um alle Werte auszuwählen, die für die erste Tabelle eindeutig sind und nicht in der zweiten Tabelle enthalten sind
```SQL
    SELECT column1 FROM table1
    EXCEPT
    SELECT column1 FROM table2;
```