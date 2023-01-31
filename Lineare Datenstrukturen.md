# Lineare Datenstrukturen

Modellierung, Implementierung und Anwendung dynamischer und statischer, linearer Datenstrukturen

## Übersicht der linearen Datentypen
| Queue | Stack | List |Array |
|--|--|--|--
| FiFo (first in first out) | FiLo (first in last out) | Jeder kennt den Nachfolger | Durch Index an den Wert
| Beispiel: Schlange im Supermarkt | Beispiel: Stapel an Kartons | Beispiel: Diese komische Wartesituation beim Friseur | Beispiele: Sitzplätze und Namen 

### Array

<img src=".images/java_array.jpg" alt="Java Array Grafik" width="400"/>

|Anwendung |Implementation
|-|-|



### Stack

<img src=".images/java_stack.jpg" alt="Java Stack Grafik" width="400"/>

> Klassischer Stapelspeicher

Ziel | Umsetzung 
|--|--|
|Initialisieren eines neuen Stacks|`Stack neuerStack <ContentType> =new Stack <ContentType>();`
|Abfrage, ob der gegebene Stapel befüllt ist. Ist der gegebene Stack leer, wird der Wahrheitswert `true` zurück gegeben |`neuerStack.isEmpty(); => boolean`
|Setzt ein neues Object der Klasse `ContentType` auf den bereits bestehenden Stack drauf |`neuerStack.push();`
|Löscht das oberste Element des Stapels|`neuerStack.pop();`
|Gibt das oberste Objekt des Stackt zurück|`neuerStack.top()=> ContentType;`


### Queue

<img src=".images/java_queue.jpg" alt="Java Queue Grafik" width="400"/>

Ziel | Umsetzung 
|--|--|
|Initialisieren einer neuen Queue|`Queue neueQueue <ContentType> = new Queue <ContentType>();`
|Abfrage ob die Queue leer ist. Wenn die Queue leer ist, dann wird der Wahrheitswert `true` zurück gegeben. |`neueQueue.isEmpty() => boolean;`
|Eine neues Objekt, stellt sich hinten in der Schlange an|`neueQueue.enqueue();`
|Das forderste Objekt wird aus der List gelöscht und das zweite Objekt wird zum Head|`neueQueue.dequeue();`
|Gibt einen das erste Objekt in der Liste zurück|`neueQueue.front();`




### List

<img src=".images/java_list.jpg" alt="Java List Grafik" width="400"/>

Ziel | Umsetzung 
|--|--|
||`List neueListe <ContentType> = new Liste <ContentType>();`
||`neueListe.isEmpty();`
||`neueListe.hasAccess();`
||`neueListe.next();`
||`neueListe.toFirst();`
||`neueListe.toLast();`
||`neueListe.getContent();`
||`neueListe.setContent();`
||`neueListe.insert();`
||`neueListe.append();`
||`neueListe.concat();`