# Datenbanken

## ER-Diagramm

## Normalformen

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


