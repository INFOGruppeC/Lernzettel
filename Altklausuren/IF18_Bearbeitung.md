# Abiturprüfung 2018

## Aufgabe a)

- Hat Beziehung ( an den Pfeilen zu erkennen) 
=> Jedes Grundstück hat eine Liste an Einbrüchen und jeder

Es ist sinnvoll die Einbrücher in einer Liste zu speichern, da es sich bei einer Liste um eine dynmaische Datenstruktur handelt und man die Anzahl von Verbrechen nicht im vorhinein kennt. Des weiteren lässt sich im Gegensatz zu anderen dynamsischen Datenstrukturen wie der Queue oder dem Stack problemlos durch eine Liste durchiterieren


## Aufgabe b)

```java
public List<Grundstueck> ermittleGrundstueckeMitEinbruechen(Zeitstempel pTatzeit, int pMaxMinutenDifferenz) {
    return liste; // Liste mit Grundstücken, bei denen mindestens ein Mal eingebrochen wurde
}
```

## Aufgabe c)


## Aufgabe d)
Es ist korrekt, dass der Speicherbedarf optimiert wird, wenn der Gefährdungsindex nicht in jedem Grundstück gespeichert wird.

**Jedoch** werden **wesentlich häufiger** Einbrüche und ihr Gefährdungsindex abgefragt, als dass neue Einbrüche eingefügt werden.

Von der Anzahl der auszuführenden Operationen her ist es also wesentlich effizienter den Gefahrenindex nur beim Einfügen eines neuen Einbruchs zu berechnen und nicht bei jedem Aufruf des Gefährdungsindizes, auch wenn dann ein weiteres Attribut gespeichert werden muss.

Daher sollte die aktuelle Methode beibehalten und nicht der Vorschlag des Entwicklers umgesetzt werden.