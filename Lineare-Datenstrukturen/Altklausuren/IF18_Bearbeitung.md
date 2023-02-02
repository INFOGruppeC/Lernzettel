# Abiturprüfung 2018

## Aufgabe a)

- Hat Beziehung ( an den Pfeilen zu erkennen) 
=> Jedes Grundstück hat eine Liste an Einbrüchen und jeder

Es ist sinnvoll die Einbrücher in einer Liste zu speichern, da es sich bei einer Liste um eine dynmaische Datenstruktur handelt und man die Anzahl von Verbrechen nicht im vorhinein kennt. Des weiteren lässt sich im Gegensatz zu anderen dynamsischen Datenstrukturen wie der Queue oder dem Stack problemlos durch eine Liste durchiterieren


## Aufgabe b)

Die Funktion erstellt eine neue, leere Liste. Dann iteriert sie durch die Liste `alleGrundstuecke` und entnimmt nacheinander jedes Element aus dieser. Aus dem entnommenen Objekt wird mittels der eigenen Funktion `gibEinbrueche()` eine Liste mit allen Einbrüchen abgerufen. Wenn diese List nicht leer ist, wird nachgesehen, ob einer der Einbrüche aus der Liste innerhalb der übergebenen Tatzeit liegt. Wenn ja, dann wird das Grundstücks-Objekt der zu Beginn neu erstellten Liste angehangen.

```java
public List<Grundstueck> ermittleGrundstueckeMitEinbruechen(Zeitstempel pTatzeit, int pMaxMinutenDifferenz) {
    List<Grundstuecke> grundstueckeMitEinbruechen = new List<>();
    alleGrundstuecke.toFirst();
    while (!alleGrundstuecke.hasAccess()) {
        Grundstueck aktuell = alleGrundstuecke.getContent();
        List<Einbruch> einbrueche = aktuell.gibEinbrueche();
        if (einbrueche.toFirst().hasAccess()) {
            while (einbrueche.hasAccess()) {
                Einbruch aktueller = einbrueche.getContent();
                if (aktueller.gibTatzeit() >= pTatzeit-pMaxMinutenDifferenz && aktueller.gibTatzeit() <= pTatzeit+pMaxMinutenDifferenz) {
                    grundstueckeMitEinbruechen.append(aktuell);
                    break;
                }
            }

        }
        alleGrundstuecker.next();
    }
    return grundstueckeMitEinbruechen; // Liste mit Grundstücken, bei denen mindestens ein Mal im angegebenen Zeitraum eingebrochen wurde
}
```

## Aufgabe c)

Die Methode nimmt als Parameter pZahl und gibt die eine Liste mit den pZahl Grundstücken mit dem größten Gefahrenindex zurück. 

## Aufgabe d)
Es ist korrekt, dass der Speicherbedarf optimiert wird, wenn der Gefährdungsindex nicht in jedem Grundstück gespeichert wird.

**Jedoch** werden **wesentlich häufiger** Einbrüche und ihr Gefährdungsindex abgefragt, als dass neue Einbrüche eingefügt werden.

Von der Anzahl der auszuführenden Operationen her ist es also wesentlich effizienter den Gefahrenindex nur beim Einfügen eines neuen Einbruchs zu berechnen und nicht bei jedem Aufruf des Gefährdungsindizes, auch wenn dann ein weiteres Attribut gespeichert werden muss.

Daher sollte die aktuelle Methode beibehalten und nicht der Vorschlag des Entwicklers umgesetzt werden.