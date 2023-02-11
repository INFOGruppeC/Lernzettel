# Vererbung

## Definition

Vererbung ist ein Mechanismus, mit dem Klassen aufeinander aufbauen können. Eine Klasse kann von einer anderen Klasse erben. Die Klasse, die erbt, wird als Subklasse bezeichnet. Die Klasse, von der geerbt wird, wird als Superklasse bezeichnet.

## Vererbungshierarchie

Eine Vererbungshierarchie ist eine Hierarchie von Klassen, die durch Vererbung miteinander verbunden sind. Die Vererbungshierarchie ist eine Baumstruktur. Die Wurzel der Baumstruktur ist die Superklasse. Die Blätter der Baumstruktur sind die Subklassen.

### Beispiel

Die Klassen `Cat` und `Dog` erben von der Klasse `Animal`. Die Klasse `Animal` ist die Superklasse. Die Klassen `Cat` und `Dog` sind die Subklassen. Die Vererbungshierarchie ist folgende:

```
Object
├── Animal
│   ├── Cat
│   └── Dog
└── Person
    ├── Student
    └── Teacher
```

> **Hinweis**
> Bei der Vererbungshierarchie in Java ist die Klasse `Object` immer die Superklasse von allen Klassen. Sie ist die Wurzel der Baumstruktur. Sie muss nicht explizit in der Vererbungshierarchie dargestellt sein.

## Implementierung von Vererbung

### Deklaration einer Subklasse

```java
public class Cat extends Animal {
}
```

Die Klasse `Cat` erbt von der Klasse `Animal`. Die Klasse `Cat` ist eine Subklasse. Die Klasse `Animal` ist eine Superklasse.

### Vererbung von Attributen

```java
public class Animal {
    private String name;
}
```

```java
public class Cat extends Animal {
}
```

Die Klasse `Cat` erbt das Attribut `name` von der Klasse `Animal`.

Es kann nun verwendet werden:

```java
public class Cat extends Animal {
    public void printName() {
        System.out.println(name);
    }
}
```