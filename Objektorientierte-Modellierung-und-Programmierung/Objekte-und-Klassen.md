# Objekte und Klassen

## Definition von Klassen

Eine Klasse ist eine abstrakte Vorstellung eines Objektes. Sie beschreibt die Eigenschaften und Verhalten eines Objektes. Eine Klasse ist eine Sammlung von Objekten, die alle die gleichen Eigenschaften und Verhalten haben.

### Deklaration einer Klasse

```java
public class Person {
    // Attribute
    private String name;
    private int age;
    private boolean isMale;

    // Konstruktor
    public Person() {
        this.name = "Max Mustermann";
        this.age = 42;
        this.isMale = true;
    }

    // Methoden
    public String getName() {
        return this.name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return this.age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public boolean isMale() {
        return this.isMale;
    }

    public void setMale(boolean isMale) {
        this.isMale = isMale;
    }
}
```

## Definition von Objekten

Ein Objekt ist eine konkrete Instanz einer Klasse. Es ist eine konkrete Realisierung eines abstrakten Konzepts. Ein Objekt ist eine Instanz einer Klasse. Es hat eine eindeutige Identität und kann durch eine Variable referenziert werden.

### Erzeugung eines Objektes

```java
Person person = new Person();
```


## Attribute

Attribute sind die Eigenschaften eines Objektes. Sie beschreiben die Daten, die ein Objekt speichert. Attribute können vom Typ `int`, `double`, `boolean`, `String` oder `char` sein. Außerdem können sie auch vom Typ einer anderen Klasse sein. In diesem Fall handelt es sich um ein Bezugsobjekt.

### Deklaration von Attributen

```java
public class Person {
    private String name;
    private int age;
    private boolean isMale;
}
```

### Initialisierung von Attributen

```java
public class Person {
    private String name = "Max Mustermann";
    private int age = 42;
    private boolean isMale = true;
}
```
Initialisierung bei der Deklaration.

```java
public class Person {
    private String name;
    private int age;
    private boolean isMale;

    public Person() {
        this.name = "Max Mustermann";
        this.age = 42;
        this.isMale = true;
    }
}
```
Initialisierung im Konstruktor.

```java
    name = "Max Mustermann";
    age = 42;
    isMale = true;
```
Initialisierung nach der Deklaration.

### Zugriff auf Attribute

```java
public void printName() {
    System.out.println(this.name);
    // oder
    System.out.println(name);
}
```

## Methoden

Methoden sind die Verhalten eines Objektes. Sie beschreiben die Aktionen, die ein Objekt ausführen kann. Methoden können Parameter haben. Diese Parameter können vom Typ `int`, `double`, `boolean`, `String` oder `char` sein. Außerdem können sie auch vom Typ einer anderen Klasse sein. In diesem Fall handelt es sich um ein Bezugsobjekt.

### Deklaration von Methoden

```java
public void printName() {
    System.out.println(this.name);
}
```

### Aufruf von Methoden

```java
Person person = new Person();
person.printName();
```

## Konstruktoren

Konstruktoren sind Methoden, die beim Erstellen eines Objektes ausgeführt werden. Sie initialisieren die Attribute des Objektes. Konstruktoren haben den selben Namen wie die Klasse. Sie haben keinen Rückgabetyp. Außerdem können sie Parameter haben. Diese Parameter können vom Typ `int`, `double`, `boolean`, `String` oder `char` sein. Außerdem können sie auch vom Typ einer anderen Klasse sein. In diesem Fall handelt es sich um ein Bezugsobjekt.

### Deklaration von Konstruktoren

```java
public class Person {
    private String name;
    private int age;
    private boolean isMale;

    // Das ist ein Konstruktor
    public Person() {
        this.name = "Max Mustermann";
        this.age = 42;
        this.isMale = true;
    }
}
```

## Bezugobjekte

Bezugobjekte sind Objekte, die als Attribute einer Klasse deklariert werden. Sie sind eine Referenz auf ein anderes Objekt. Bezugobjekte können auch als Parameter einer Methode übergeben werden.

### Deklaration von Bezugobjekten

```java
public class Person {
    private String name;
    private int age;
    private boolean isMale;
    // Bezugobjekt
    private Person bestFriend;
}
```

### Initialisierung von Bezugobjekten

```java
public class Person {
    private String name;
    private int age;
    private boolean isMale;
    // Bezugobjekt
    private Person bestFriend;

    public Person() {
        // Initialisierung des Bezugobjektes
        this.bestFriend = new Person();
    }
}
```