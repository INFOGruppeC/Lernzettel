# Automaten und Sprachen


## Definition Automaten:
Sind entweder deterministisch (DEA) oder nichtdeterministisch (NEA) Der gesamte Automat ist dabei endlichEr besteht aus Zuständen, Zustandsübergängen, einen Startzustand (oder mehrere beim NEA), Eingaben und EndzuständeJeder Automat hat eine Zustandsübergangsfunktion (Tabelle/Automat)


Tabelle: Zeilen sind Zustände; Spalten die möglcihen Eingaben; Felder

der Zustand, zu dem der Automat bei entsprechender Eingabe wechselt

## NEA vs DEA 

## Akzeptor:
`A` = (Ʃ, Q, F, S, σ)</br>
`Ʃ` = {Eingabealphabet}</br>
`Q` = {Zustandsmenge}</br>
`F` = {Akzeptierte Zustände}</br>
`S` = Startzustand </br>
`σ` = Zustandsübergänge (graphischer Automat/Tabelle) 

## Transduktor (Mealy):
`A` = (Ʃ, Q, Ω, S, σ)</br>
`Ω` = {Ausgabealphabet}

## Kellerautomat:
`K` = (Ʃ, Q, F, S, Γ, K, σ)</br>
`Γ` = {Kelleralphabet}</br>
`K` = Kellervorbelegungszeichen</br>

`ɛ` als Eingabe: keine Eingabe</br>
`ɛ` als Kelleroperation: nichts schreiben (= löschen)</br>
`#` = Kellerboden Jeder Blick in den Keller löscht das oberste Zeichen

Kelleroperationen wie beim Stack: Push, Pop und Nop

## NEA zu DEA:
Tablelle erstellen, Spaleten mit allen möglichen Eingaben beschriften

In die erste Zeile kommen alle Startzustände des NEAs (z.B. s0, s1) </br>
Die Felder werden dann mit allen Zuständen befüllt, in die der NEA mit entsprechender Eingabe wechseln würde. </br>
In die nächsten Spalten kommen dann alle möglichen Zustandskombinationen, die in den ersten Feldern eingetragen wurden.</br>
Schritt 3 + 4 werden wiederholt, bis alle Kombinationen untersucht wurden</br>

Die Tabelle beschreibt dann den passenden DEA und könnte als Automat visualisiert werden. 

## Definition Sprachen:
Eine Sprache ist eine Menge von Wörtern bestehend aus Zeichen eines AlphabetsFormale Sprachen können nach Regeln aufgebaut sein, müssen aber nichtSie können durch Automaten, Grammatiken oder regulären –––Ausdrücken beschrieben werdenDer Betrag der Sprache ist die Anzahl aller Wörter innerhalb der SpracheSprachen können aus unendlich vielen Wörtern bestehenEine Sprache kann (links-, rechts-) regulär, kontextfrei, kontextsensitiv und rekursiv aufzählbar sein 

### Regulärer Ausdruck:
L = { a^nb^n | n E IN, n > 0 } <br/>
Grammatik:G = (N, T, S, P) <br/>
N = {Nichtterminale (in Großbuchstaben)}<br/>
T = {Terminale} <br/>
S = StartnichtterminalP ={<br>
  Projektion, <br/>
  z.B.A -> aA | ɛ <br/>
} <br/>
L(A) -> Sprache eines Automaten


## Ablaufdiagramm Nea und DEA
