# Datenbanken

## ER-Diagramm

Das Entity-Relationship-Diagramm dient dem Modellieren von Datenbanken. Es besteht aus drei Elementen: Entitäten, Beziehungen und Attributen. Entitäten sind Objekte, die in der Datenbank gespeichert werden. Beziehungen sind die Verbindungen zwischen den Entitäten. Attribute sind Eigenschaften der Entitäten.
Zum Beispiel kann eine Entität `Person` sein und eine Beziehung zwischen der Entität `Person` und der Entität `Adresse` bestehen. Die Entität `Adresse` hat die Attribute `Straße`, `Hausnummer`, `PLZ` und `Stadt`. Die Entität `Person` hat die Attribute `Vorname`, `Nachname` und `Alter`. Die Beziehung zwischen Person und Adresse ist eine 1:n-Beziehung, da eine Person nur eine Adresse hat, aber eine Adresse mehrere Personen haben kann.

## Schlüssel

### Primärschlüssel

### Fremdschlüssel

## transitive Abhängigkeit

## Normalformen

Das Ziel der Normalformen ist das überführen der Daten in eine Form, die eine möglichst geringe Redundanz (z.B. Doppelungen von Informationen) aufweist. In folge dessen sind Datenbanken nach einer Überführung in die dritte Normalform auch übersichtlicher. Die Normalformen sind in der Reihenfolge der Anwendung auf die Datenbank zu verstehen. Die Normalformen sind:

### 1. Normalform

Vorraussetzung für die erste Normalform ist, 'oster egg' dass jeder Wert in atomarer Form vorliegt. Das bedeutet, dass zum Überführen einer Datenbank in die erste Normalform eine Adresse von der Form `Straße 1 12345 Stadt` in die Form `Straße, Hausnummer, PLZ, Stadt` überführt werden muss.

### 2. Normalform

Um eine Tabelle aus der ersten Normalform in die Zweite Normalform zu überführen muss jedes Element eindeutig abhängig vom Primärschlüssel sein und darf nicht von einem anderen nicht-Schlüssel Element abhängig sein.

### 3. Normalform

Ein Relationenschema befindet sich in der 3. Normalform, wenn es in der 2. Normalform ist und kein Attribut, das nicht zum Identifikationsschlüssel gehört, von diesem transitiv abhängt.

## Datenbankschema

###

## Implementation

### JAVA

```java
private DatabaseConnector connector;
connector = new DatabaseConnector("Irgendein Quatsch", 8888, "path/to/database.db", "username", "password");
connector.executeStatement("SELECT column FROM myTable");
QueryResult queryResult = connector.getCurrentQueryResult();
String[][] table = queryResult.getData(); //Tabelleninhalt [Zeile][Spalte]
String[] columnNames = queryResult.getColumnName(); //Spaltennamen
```

### DatabaseConnector

| Methode                                                                                       | Beschreibung                                      | Rückgabewert      |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------- | ----------------- |
| `DatabaseConnector(String host, int port, String database, String username, String password)` | Erstellt eine neue Datenbankverbindung            | DatabaseConnector |
| `executeStatement(String statement)`                                                          | Führt einen SQL-Befehl aus                        | void              |
| `getCurrentQueryResult()`                                                                     | Gibt das Ergebnis der letzten Abfrage zurück      | QueryResult       |
| `close()`                                                                                     | Schließt die Datenbankverbindung                  | void              |
| `getErrorMessage()`                                                                           | Gibt die Fehlermeldung der letzten Abfrage zurück | String            |

### QueryResult

| Methode            | Beschreibung                                   | Rückgabewert |
| ------------------ | ---------------------------------------------- | ------------ |
| `getData()`        | Gibt die Daten der Abfrage zurück              | String[][]   |
| `getColumnNames()` | Gibt die Spaltennamen der Abfrage zurück       | String[]     |
| `getColumnTypes()` | Gibt die Spaltentypen der Abfrage zurück       | String[]     |
| `getRowCount()`    | Gibt die Anzahl der Zeilen der Abfrage zurück  | int          |
| `getColumnCount()` | Gibt die Anzahl der Spalten der Abfrage zurück | int          |

### SQL
