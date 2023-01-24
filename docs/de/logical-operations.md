# Logische Operationen
## AND
> logische AND-Verknüpfung
```SQL
    SELECT * FROM table1 WHERE alter < 18 AND plz = 5000;
```
## OR
> logischer OR-Verknüpfung
```SQL
    SELECT * FROM table1 WHERE alter < 18 OR alter > 65;
```
## NOT
> nicht gleich (!=)
```SQL
    SELECT * FROM tabelle WHERE NOT id = 1;MAX()
```
## BETWEEN
> BETWEEN prüft, ob der geprüfte Wert zwischen zwei Werten liegt.
```SQL
    SELECT id, column2, column3 FROM table1 WHERE id BETWEEN 1 AND 10;

    SELECT id, column2, column3 FROM table1 
    WHERE eintritt BETWEEN '2020-01-01' AND '2020-12-31'; 

    -- Vergleichsoperatoren können immer anstelle von BETWEEN verwendet werden
    -- und diese werden mit UND verknüpft
    SELECT id, column2, column3 FROM table1 
    WHERE eintritt >= '2020-01-01' AND eintritt <= '2020-12-31';
```
## IN
> Mit dem IN-Operator kann festgestellt werden, ob ein Wert mit einem Wert aus einer Liste übereinstimmt. In der Liste können Sie beispielsweise bestimmte Zahlen auflisten, die mit einer Spalte verglichen werden sollen:
```SQL
    SELECT id, column2, column3 FROM table1 WHERE id IN (1, 2, 3);
```
## LIKE
> LIKE ist ideal für komplexere Textabfragen. LIKE sucht nach einem Muster in einem String und wird daher auch als Mustervergleich bezeichnet. Es gibt verschiedene Platzhalter:
```SQL
    -- % -> Beliebig viele Zeichen
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '%peter%';
    -- _ -> ein Zeichen
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '_peter';
    -- [] -> Platzhalter für a-p
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '[a-p]peter';
    -- [^] -> Platzhalter für ein Zeichen zwischen a-p
    SELECT id, column2, column3 FROM table1 WHERE column2 LIKE '[^a-p]peter';
```
## NULL
> Wenn Sie fragen, ob ein Item Null ist oder nicht, müssen Sie IS verwenden
```SQL
    SELECT * FROM table1 WHERE Spalte2 IS NULL;
    -- oder nicht
    SELECT * FROM table1en WHERE Spalte2 NICHT IS NULL;
```