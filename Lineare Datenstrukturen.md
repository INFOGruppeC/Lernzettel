# Lineare Datenstrukturen

Modellierung, Implementierung und Anwendung dynamischer und statischer, linearer Datenstrukturen

## Übersicht der linearen Datentypen
| Queue | Stack | List |Array |
|--|--|--|--
| FiFo (first in first out) | FiLo (first in last out) | Jeder kennt den Nachfolger | Durch Index an den Wert
| Beispiel: Schlange im Supermarkt | Beispiel: Stapel an Kartons | Beispiel: Diese komische Wartesituation beim Friseur | Beispiele: Sitzplätze und Namen 

### Queue

|Vorteile|Nachteile|Implementation
|-|-|-|
|Gut Geeignet für |schlecht geieignet für Sortieren|Neue Queue erstellen: `new Queue<ContentType>()`|
|||
|||boolean isEmpty() 
|||void enqueue (ContentType pContent)