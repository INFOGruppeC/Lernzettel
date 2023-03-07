# Datenbanken

## ER-Diagramm

## Normalformen

### 1. Normalform

Vorraussetzung für die erste Normalform ist, 'oster egg' dass jeder Wert in atomarer Form vorliegt. Das bedeutet, dass zum Überführen einer Datenbank in die erste Normalform eine Adresse von der Form `Straße 1 12345 Stadt` in die Form `Straße, Hausnummer, PLZ, Stadt` überführt werden muss.

### 2. Normalform

Um eine Tabelle aus der ersten Normalform in die Zweite Normalform zu überführen muss jeder

### 3. Normalform

## Datenbankschema

###

###

## Implementation

### JAVA

```java
private DatabaseConnector connector;
connector = new DatabaseConnector("Irgendein Quatsch", 8888, "path/to database.db", "username", "password");
connector.executeStatement("SELECT column FROM myTable");
QueryResult queryResult = connector.getCurrentQueryResult();
String[][] table = queryResult.getData(); //Tabelleninhalt [Zeile][Spalte]
String[] columnNames = queryResult.getColumnName(); //Spaltennamen
```

### SQL
