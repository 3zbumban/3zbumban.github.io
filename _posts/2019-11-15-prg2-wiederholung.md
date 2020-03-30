---
layout: post
title: "vorlage"
comments: true
description: "vorlage"
keywords: "vorlage"
---

# prg2

## 00_Organisation

* [java-insel](http://openbook.rheinwerk-verlag.de/javainsel/)
* [git-guide](http://rogerdudler.github.io/git-guide/)

1. Organisation und Java Einführung
2. Klassen und Objekte
3. Objektorientierung in Java
4. JUnit, Javadoc, Annotations
5. (Implementierungs) Vererbung
6. Ausgewählte Klassen und Datentypen
7. Interfaces, abstrakte Klassen
8. Collections
9. Exceptions
10. Dateien, Datenströme

## 01_Java_Einfuehrung

> Java ist ein beispiel einer weitverbreiteten Objektorientierten Programiersprache

* **1990:** Vorläufer "Oak"
  * interaktives Fernsehen, Konsumerelektronik
  * Verlässlich Kompackt, Platformunabhängig
* **1993:** "Oak" wird java
  * Weiterentwicklung für das WWW
  * Vorläufer von Applets
* **1996:** Java JDK 1.0 release
  * Implementierung innerhalb [Netscape Navigator](https://en.wikipedia.org/wiki/Netscape_Navigator)
  (früher webbrowser)
* Städige **erweiterung der Klassenbibliothek**
* **2008:** Android, das u.a. auf Java basiert, erscheint.
* **2009:** Oracle übernimmt Sun

&#8680; [Aktuelle Version](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

### Eigenschaften von Java

* Objektorientiert (Modularität, Wiederverwendbarkeit)
* Automatisches Speichermanagement (**kein** "malloc", "free")
* Plattformunabhängigkeit (erzeugt Bytecode, läuft in JVM)
* Weit Verbreitet (Desktop, Web, Android)

### Java Komponenten

* Programiersprache Java (_Aktuell: Version 13_)
* JRE ("Laufzeitumgebung")
  * zum Programme ausführen
  * Übersetzt Bytecode (.class) in auf der JVM ausführbaren Maschinencode
* JDK
  * Für Programmierer
  * Übersetzt Java-Dateien (.java) in Bytecode (.class)
  * Verschiedene Versionen:

| Java Standard Edetion (SE) | Java Enterprise Edition (EE) | Java Micro Edition (ME) |
|:--------------------------:|:----------------------------:|:-----------------------:|
|      Desktopeinsatz        | Geschäftsanwendungen, Server |      Embedded System    |

### Traditioneller Ansatz

* Compiler übersetzt Hochsprachen in Maschinensprache die auf einer bestimmten Platform
ausführbar ist.

### Javas Ansatz

* Compiler übersetzt Programm in Bytecode
* Interpreter der JVM führt Bytecode aus und übersetzt diesen zur Laufzeit in
Platformabhängigen Maschinencode
* Java Bytecode ist Platformunabhängig

| Vorteil                 | Nachteil                                             |
|:-----------------------:|:----------------------------------------------------:|
| Plattformunabhängigkeit | Leicht höherrer **resourcen Verbrauch der JVM**      |

### Erstes Programm

```java
public class Quadrat { // Klassename = Dateiname
    static int Quadrat(int n) { // int parameter, int rückgabewert
        return n * n;
    }
    public static void main(String[] args) { // main method
        for (int i = 1; i <= 4; i++) {
            int result = quadrat(i);
            String s = "Quadrat von " + i + ": " + result; // mit '+' können strings
                                                          // verbunden werden
            System.out.println(s); // consolen ausgabe
        }
    }
}
```

### IDE (Integrierte Entwicklungsumgebung)

* Erleichtert Arbeit
  * Syntax Highlighting
  * Debugging
  * Refactoring

### Eigenschaften von Java(2)

* C ähnliche syntax
* Kein Präprozessor _(kein #include, #define)_
* Nur Elementare Datentypen und Klassen
* Keine Expleziten zeiger
* Keine Globalen Variablen
* Alles ist teil einer Klasse

### Programierparadikmen

* Funktionale Programmierung :
  * Nur Funktionen und Rekursion; keine Zustände
  * fac(n) = if n = 0 then 1 else n* fac(n‐1) end
* Imperative Programmierung :
  * Variablen, Attribute, Zustände, Steuerfluss
  * k = n; r = 1; while k > 0 { r = r + 1;} …
* Logische Programmierung :
  * Fakten, Prädikate, Invarianten, Deduktionsregeln
* Objektorientierte Programmierung :
  * Verwendet Konzepte der imperativen Programmierung (for‐Schleife)
  * Und der funktionalen  Programmierung
  * Neue Konzepte: Objekte und Klassen

> Note: Jede Klasse kommt in eine datei Klassename.java (Klassenamen Großgeschrieben)

### Kontrollstrukturen und Operatoren

```java
int x = 1;
if (x > 0) a = x;
else a = -x;
```

```java
int a = 1;
switch(a) {
    case 0: System.out.println("null"); break;
    case 1: System.out.println("eins"); break;
    default: System.out.println("default");
}

while (expression) {
    // code
}

for (int i = 0; i < 10; i++) {
    // code
}

do {
    // code
} while (expression);
```

```java
+ // plus
- // minus
* // mal
/ // geteilt
% // modulo

// vergleichsoperatoren
>
<
==
!=
<=

// logische operatoren
!
&&
||

// bitoperatoren
~
^
>>
&
|

// increment decrement zuweisungen
++
--
+=
/=
*=
%=
```

### Primitive Datentypen

| Datentyp  | Bits |
|:---------:|:----:|
| boolean   | 8    |
| char      | 16   |
| byte      | 8    |
| short     | 16   |
| int       | 32   |
| long      | 64   |
| float     | 32   |
| double    | 64   |

Byte _(8b)_ &rarr; Short _(16b)_ &rarr; Int _(32b)_ &rarr; Long _(64b)_ &rarr; Float _(32b)_ &rarr; Double _(64b)_

Char _(16b)_ &rarr; Int _(32b)_

Boolean _(8b)_

### Arrays

* Erahalten länge bei Initialisierung
* Länge nach initialisierung fest

```java
int[] array = new int[5]; // array länge 5
int arrayLength = array.length;

String[][] multiArray = new String[4][4];
multiArray[2][3] = "Otto";

// iterieren
double[] dArray = {1.2, 3.0, 0.8};

// möglichkeit 1: 'itar'
int sum = 0;
for (int i = 0; i < dArray.length; i++) {
    sum = dArray[i];
}

// möglichkeit 2: 'iter'
for (double d : dArray) {
    sum += d;
}
```

### String

```java
String s1 = "Hallo";
String s2 = "Grüßdich";
String s3 = s1 + s2;
String s4 = Integer.parseInt(12);

// ausgabe auf konsole: 'sout'
System.out.println(s3 + " Hallo");
```

### Scanner (Benutzereingabe)

```java
Scanner scanner = new Scanner(System.in);
String s = scanner.next(); // liest String ein
int a = scanner.nextInt(); // liest int ein
```

## 02_Klassen_und_Objekte

> Objektorientireung sorgt für __Konsistenz__ und __veringerung von Redundanzen__

### Klassen

```java
class Klasse { // Name der Klasse == Dateiname
    // Attribute:
    private int id;     // bevorzugt 'private'
    private String name;// das heist nur methoden dieser
                        // Klasse haben zugriff

    // Konstruktor:
    Klasse(int id, String name) {
        this.id = id;
        this.name = name;
    }

    // Methoden:
    public int getId() { // public gibt zugriff von außen
        return this.id;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

```java
class KlasseTest {
    public static void main(String[] args) {
        // erzeugen eines neuen Objekts
        // zugriff nur auf methoden und attribute die "public" sind
        Klasse k1 = new Klasse(1, "name");
        Klasse k1 = new Klasse(2, "name2");

        // methoden aufrufe:
        k1.getId();
        k1.setName("neuer name");
    }
}
```

### Grundprinzipien der Objektorientierung(1)

* Abstraktion
  * nur relevantes von Objekten
* Modularität
  * Aufteilung/Strukturierung in Klassen und Pakete
* Datenkapselung
  * zusammenfassen und verstecken von Daten hinter schnittstellen
* Polymorphie
* Vererbung

### Sichtbarkeit von Atributen, Methoden, Klassen

> Sichtbarkeit sollte so weit wie möglich eingeschränkt werden!

#### '+' public

* zugriff von außem mit '.'-operator

#### '-' private

* kein zugriff von außen
* nur zugriff für methoden der selben Klasse

#### '~' peketsichtbar (keine angabe)

* &hArr; keine sichtbarkeit spezifiziert
* alle Klassen des gleichen Package haben zugriff

#### '#' protected

* zugriff in selber Klasse, in abgeleiteten Klassen und inerhalb des Package

### Überladen von Methoden

> Mehrere Methoden mit sleben namen, unterscheiden sich in **Signatur**

* Signatur = Methodenname + Parameterliste

```java
public class Konto {
    private int kontoNummer;
    private double saldo;

    // Default-Konstruktor
    public Konto() {
    }

    // Wertkonstruktor 1
    public Konto(int kontoNummer) {
    this.kontoNummer = kontoNummer;
    }
    // Wertkonstruktor 2
    public Konto(int kontoNummer, int saldo) {
    this.kontoNummer = kontoNummer;
    this.saldo = saldo;
    }
}
```

> note: this &hArr; selbstreferenz

### final

* **bei Klassen:** kein ableiten `extends` möglich
* verbietet spätere veränderung
* kann nach der deklaration zugewiesen werden

```java
final int i = 5;
final int j;

j = 10
```

### Immutable (Unveränderliche Klassen)

* Immutable &hArr; Zusatand des Objekts nach Instaziierung wird nicht mehr geändert
* Klassen **sollten** so weit wie möglich immutable sein
* &rarr; dadruch keine `clone` methode nötig
* Vorteile: ThreadSicherheit, Sicher gegen null Reference Error, Keine unerwarteten nebenefekkte, 

* Eine klasse immutable machen?:
  * deklariere Klasse final `final class Konto {...}`
    * &rarr; verhindert ableiten
  * deklariere alle Attribute als **private** und **final**
  * **keine** methoden die Attribute verändern _(außer: Konstruktor)_

### statische Methoden

> Deklaration mit **static** Modifizierer

* Existiren unabhängig von Instanz
  * &rarr; Aufruf ohne vorheriges `new` möglich

```java
static double sqrt(double a) {
    return Math.sqrt(a);
}
```

> Note: Man braucht zum berechnen der Wurzel kein extra Objekt

### statische Attribute

* exestieren unabhängig vom Objekt
* nur einmal angelegt ("im Bauplan")
* könen von allen Klassen-Methoden verwendet werden
* Lebensdauer = Programmdauer
* **Verwendung:** z.b. Instanzenzähler

### Klassen vs. Objektmethoden

#### Klassenmethode (static)

> zugriff **auf static** method's und static var's

```java
Example.getVar();
```

#### Objektmethode

> zugriff auf **static und non-static** method's und var's

```java
Example e = new Example();
e.getVar();
```

### typische Phasen Objektoriertert Programme

* Erzeugung von Objekten (`new`)
* Vernetzung der Objekte durch
  * Kontruktoraufrufe
  * Objektmethodenaufrufe
* Arbeitsphase (objekte arbeiten zusammen)
* Abbauphase (Java erkennt unbenutze Objekte automatisch)
  * &rarr; Garbage Collection

## 03_JUnit_und_Javadoc

### Software Reliability

* > "Warscheinlichkeit das Software-System unter bestimmten bedingungen keine Fehler verursacht"
* Messung durch: Uptime, Mean Time To Failure/ Between Failure/ To Reapair

### Bugs

* > "Bugs sind in Komplexen (Software)-Systemen unvermeindlich"
* Im Code verstäckte Bugs können erst viel Später sichtbar werden

### Testen (Systematischer ansatz um Fehler zu finden)

* **Failed Test:** Nachweis eines Fehlers
* **Passed Test:** Keine Fehler **gefuden** worden

* Testen kostet viel zeit, wird oft als aufgabe für Anfänger gesehen.
* Es ist unmöglich ein Komplettes System zu testen
* Test können fehlerfreiheit **nicht** beweisen

#### Arten von Tests

* **Unit Tests:** Funktionalitätstest einzelner Software-Teile
* **Integrationstests:** Zusammenarbeit verschiedener Komponenten
* **Systemtest:** Test gesamtsystem gegen Anfroderungen
* **Regressionstest:** Wiederholtes ausführen von Tests nach Änderungen
* **Stresstest:** Systemtest unter großer last

### Test-Driven Development (TDD)

#### Traditionelles Vorgehen

* **Testen erst ganz am schluss**
* Tests unter zeitdruck
* Software fertig warum noch weiter arbeiten (tests schreiben)?

#### Test-Driven

* **Tests werden konsequent vor Implementierung erstellt**
* &rarr; hinprogramierung auf ein ziel
* &rarr; frühe problemerkennung
* &rarr; gute testabdeckung (&rarr; bessere SW-Qualität)
* &rarr; programierer kennt schwachstellen besser als jeder andere

### Test Frameworks

> JUnit

#### Anforderungen an Test-Frameworks

* Erzeugen von Tests nach dem Muster:
  * Aufbau Szenario (@Before)
  * Aufruf der zu testenden Methode (@Test)
  * Überprüfung ob ergebnis korrekt ist
* Tests sind Wiederholbar (Regression)
* Integration in IDE
* jedes (@Test) wird unabhängig von einander Durchgeführt

### JUnit

> Integriert in IntelliJ zeigt grüne/rote <=> passed/failed Tests

* `Foo.java <=> FooTest.java`
* `method() <=> methodTest()`

```java
public class Foo {
    public void method() {
    }
}
```

```java
public class FooTest {// Klassename+Test
    @Test
    public void methodTest() { // methodename+Test
        assertEquals("Expected", "result")
    }
}
```

#### JUnit assert-methoden

* assertTrue("message", test): pass if test == true
* assertFalse("message", test): pass if test == false
* assertEquals("message", expected, actual): pass if expected equal actual
* assertSame("message", expected, actual): pass if expected == actual
* assertNotSame("message", expected, actual): pass if expected != actual
* assertNull("message", value): pass if value == null
* assertNotNull("message", value): pass if value != null
* fail(): causes test to fail

##### Testen mit timeout

> Falls eine Methode nicht Termeniert, endet auch der Testcase nicht. Weitere tests werden nciht gestartet.

```java
private static final int TIMEOUT = 5000;

@Test(tiemout=TIMEOUT)
public void fooTest(){...}
```

##### Testen mit Exceptions

> Pass Test wen Exception geworfen wird. Testen ob fehler eintreten

```java
@Test(expected = ExceptionType.class)
public void fooTest(){...}

@Test(expected = ArrayIndexOutOfBoundsException.class)
public void testBadIndex() {
int[] array = new int[4];
int i = array[4]; // should fail
}
```

#### Setup und Teardown

* Methode die **vor/nach** jedem Testcase ausgeführt wird:
  * @Before/@After

```java
@Before
public void setUp(){...}

@After
public void tearDown(){...}
```

* Methode die **vor/nach** allen Testcase's ausgeführt wird:
  * @BeforeClass/@AfterClass

```java
@BeforeClass
public static void beforeClass(){...}

@AfterClass
public static void afterClass(){...}
```

#### Richtlinien für Tests

* eingrenzung zu testender Eingaben/Parameter
  * Randfälle: positiv, 0, negativ
  * array enden: array[0], array[array.length-1]
  * leerfälle: 0, 1, null, leeres Array
* Verhalten von methoden in Kompination testen
* Möglichst eine sache gleichzeitig testen
* Vermeide logik in Tests. _(kein if, else, loops)_
* Test unabhängig von einander. (1. TestA 2. TestB, 1.TestB 2. TestA)

### Javadoc

> Dokumentation wird oft vernachlässigt, nicht aktuallisiert

* **Lösung:** integration von Quelltext und Dokumentation durch erweiterung des Konzepts von Blockkommentaren (/** ... */)
* javadoc generiert zu jeder `.java` datei eine `.html` datei
  * beschreibung von Klasse, Interface, Methoden etc.

```java
/**
 *  Einfache implementierung für Rationale Zahlen.
 *
 *  Rationale Zahlen werden über Zähler und Nenner dargestellt.
 *
 * @author 3zbmbn
 * @version 1.0
 */
public class Rational {
    private long num;
    private long den;

    /**
     * Rationalzahl mit Zähler und Nenner vom Typ Long
     *
     * @param num Zähler
     * @param den Nenner
     */
    public Rational(long num, long den) {}

    /**
     * Addiert zwei rationale Zahlen
     *
     * @param val rationale zahl, die addiert werden soll
     * @return Eine neue rationalzahl als Ergebnis der Operation
     */
    public Rational add(Rational val) {}
}
```

* Klassen und Interfaces:
  * _@author text_
  * _@version 1.0_
* Methoden:
  * _@param name text_
  * _@return text_
  * _@throws exceptionclass text_

* IntelliJ: `Tools > Generate Javadoc`

## 03a_TestenOOSoftware

> Ziel von Software test ist es Fehler zu entdecken. Korrektheit eines Programms kan nicht gezeigt werden.

### White-Box-Tests

> White-Box-Tests analysiren den inneren Kontrollfluss eines Programms, typischerweise mit Unit-Tests

* Aussagekraft bei Objektorientierten Sprachen fragwürdig
* Nicht implementierte features werden nicht abgedekt
* 100% überdekung ist schwer bis unmöglich

#### C0 - Anweisungsüberdeckung

* Testmenge genentspricht dem C0 Kriterium, wenn **für jede anweisung** im code ein Testfall exestiert der diese Anweisung ausführt.

#### C1 - Zweigüberdeckung

* Testmenge entspricht dem C1 Kriterium, wenn **jeder Zweig** des Kontrullflussgraphs eines Programms mindestens von einem Testfall ausgeführt wird.

#### C2 - Pfadüberdeckung

> Lässt sich in der Regel nicht erreichen da schleifen für sehr große Zahl von Pfaden sorgen

* C2 a: Alle Pfade werden durchlaufen
* C2 b: Alle Pfade werden durchlaufen, schleifen nur einmal und mehr als zwei mal
* C2 c: Alle schleifen werden genau _n mal_ durchlaufen

### Datenflussorienteirter Test

* Def: Defenition der Variable
* P-use: (prädikative) Verwendung der Variable z.b. in Bedingung
* C-use: Berechnung mit einer Variable z.b. in Formel

#### APU (All-p-uses)

* Alle Pfade von der Defenition bus zu jeder prädikativen Verwendung
* Beinhaltet Zweigüberdeckung

#### AU (All-uses)

* Alle Pfade von einer Prädikativen oder berechnenden verwendung einer Variable zu der Jeweiligen defenition

#### ACU (All-c-uses)

* Alle Pfade von der Definition einer Variable zu jeder Berechnenden Verwendung

## 04_Vererbung

> Vererbung stellt Konsistenz sicher und Vermeidet Redundanten Programmcode.

* **Konsistenz** durch verwendung von Zugänglichen methoden, einschränkung des Zugriff auf primitive Typen der Klasse
* **Redundanz** wird durch geschikte Vererbung reduziert.

```java
class Konto {
    private int knr;
    private double saldo;

    public void zahleEin(double betrag) {
        saldo += betrag;
    }
}
```

```java
// wen oberKlasse final 'extends' nciht möglich
class Gemeinschaftskonto extends Konto {
    String[] besitzer = new String[10];
}

Gemeinschaftskonto gmk = new Gemeinschaftskonto();
gmk.zahleEin(200);
```

### Grundprinzipien der Objektorientierung(2)

* Code wiederverwendbar machen
  * Bestehenden code erweitern/modifizieren
* Redundanzen vermeiden
* Generaliesierung und Spezialiesierung
  * Auto, Motorrad sind spezialiesierungen von Fahrzeugen (generaliesierung von Auto, Motorrad).
  * Spezialiesierungen haben allle Merkmale der Generaliesierung mit weiteren Merkmalen

#### Vererbung

* Defenition neuer Klassen auf Grundlage bestehender Klassen
* Die neue Klasse heist **Abgeleitete- oder Unterklasse**
* Die Klasse von der Abgeleitet wurde heist **Super- oder Oberklasse**
* Die Unterklasse kann Eigenschaften und Methoden übernehmen oder **überschreiben**

#### Polymorphie ("Vielgestaltigkeit")

* Einfaches austauschen von Code solange Schnittstelle gleich bleibt

#### Bsp

* LKW spezialiesiert Fahrzeug
* Fahrzeug ist die Oberklasse von LKW
* java: `LKW extends Fahrzeug`

* Fahrzeug generaliesiert LKW
* LKW ist die Unterklasse von Fahrzeug

### Formen der Vererbung

* Vererbung einer **Schnittstelle**
  * java: `interfaces`, `implements`
* Vererbung der **Implementierung**
  * java: `extends`
  * Klasse erbt alle methoden und Attribute der Oberklasse
  * `super(par1, par2)` **erster** aufruf von Konstruktor der unterklasse

### super()

* `super.methode()`
* `super.attr`
* `super()` kostruktoraufruf

### this

* zeigt auf aktuelle Klasse
* '#' protected gibt zugriff auf var's in Unterklasse `fav = "cheese"`

### Datentypen bei Vererbung

* Unterklasse hat datentyp der oberklasse(n) und Objekt
* An stelle eines Objektes kann auch ein objekt einer Unterklasse auftauchen `Pet p = new Cat()`
* Umgekehrt expliziter typecast `Cat c = (Cat) p`

### Interfaces

* Attribute: implicit immer: `public stativ final`
* Nur signaturen `int speed(par1, par2);`
* ~~new InterfaceXY();~~
* sind Polymorhp

```java
public interface Trainable { // "able" am ende konvention
    int train();
}
```

```java
p instanceof Klass;
p instanceof Object;
p instanceof Doable;
p.getClass();
```

```java
class Dog implements Trainable {
    private int speed;

    public Dog(String name, int speed) {
        super(name);
        this.speed = speed;
    }

    public void talk() {
        super.talk();
        System.out.println("Wuf Wuf");
    }

    @Override
    public void train() {
        this.speed++;
    }

}
```

```java
public interface A {}
public interface AB extends A {
    // public static final (implizit)
    int MAX = 10000;
}
```

* Markierungsschnittstellen: Leere schnittstellen zum markieren und mit `instanceof` erkennen
  * Bsp:
    * `java.lang.Cloneable`
    * `java.util.EventListener`
    * `java.io.Serializable`

### Abstrakte Klassen

> Mischung zwischen Schnittstellenvererbung und Implementationsvererbung (Klass & Interface)

```java
abstract class Counter {
    protected int count = 0;
    void reset() {
        this.count = 0;
    }
    int read() {
        return count;
    }

    // nur schnittstelle
    abstract void step();
}
```

* bei vererbung einer abstrakten Klasse:
  * alle abstrakten methoden überschreiben &rarr; Neue Unterklasse
  * man überschreibt nur einen teil &rarr; Neue Abstrakte Unterklasse

## 05_Objektorientierte_Modellierung

> Objektorientierung ist ein Modell der Realen Welt auf vereinfachte weise dargestellt durch objekte mit methoden und attributen

1. Objektorientierte Analyse (Modellierung der Welt, der Domäne, der Anwendung)
2. Objektorientierter Entwurf (Spezifikationen des Softwaresystems, Schnittstellen, ADT's)
    * UML
3. Objektorientierte Implementierung (Organisation des Programmcodes, so das objektorientiertes Modell im Code erkennbar ist)
    * Java, C#, C++, Dart

### Realität &rarr; Modell &rarr; Software

1. Modellierung der Realität(Welt des Kunden)
   * weglassen unwichtiger details
   * konzentration auf wesentliches
2. &rarr; Modell (Ausschinittt der Realität)
3. &rarr; Software (Wlet des Kunden ist im Code erkennbar)

### UML

> UML ist eine einheitliche Modellierungssprache für Spezifikation, Dokumentation und Konstruktion

* Datenstrukturen (Klassen-, Objektdiagramme)
* Systemverhalten (Dynamik)
* Systementwurf (Componenten, Deployment)

#### Klassendigramm

> Modell von Klassen. Kann verwendert werden im Java Code zu generieren

* **Enthält**
  * Paket
  * Objektklasse
  * Attribute
  * Operationen(Methoden)
  * Assoziationen(Beziehungen, Rollen)
  * Generaliesierungs-/Spezialiesierungsbeziehung

| Klassenname                        |
|:----------------------------------:|
|-attribut1: typ                     |
|+attribut2: typ                     |
|~attribut3: typ                     |
|#attribut3: typ                     |
|~~~~~~~~~~~~++++++++++++++++++++~~~~|
|+Klassenname(par1: typ): return-typ |
|+methode2(): return-typ             |
|-methode1(par1: typ): return-typ    |

* underline == static

![Notation für Klassendigramm](__/Screenshot_7.png)

#### Objektdiagramm

> Zeigt Objekt zu einem bestimmten zeitpunkt des Programms. Wird für beispiele/anwendungsszenarien genutzt.

* **Enthält**
  * Objektname, Objektklasse
  * Attribute mit Belgeungen
  * Assoziation

![Notation für Objektdigramm](__/Screenshot_1.png)

#### Beziehungen

* **Bidirektional**
![Bidirektional](__/Screenshot_2.png)

* **Unidirektional**
![Unidirektional](__/Screenshot_3.png)

* **Komposition**
![Komposition](__/Screenshot_4.png)

* **Vererbung**
![Vererbung](__/Screenshot_5.png)

* **Interfaces**
![Interfaces](__/Screenshot_6.png)

## 06_Ausgewaehlte_Klassen

### Arrays (WDH)

```java
int[] a;
a = new int[10];
a[2] = 2;

int[] b = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

a.length
b.length

int[] c = b.clone();
```

```java

int[] a = {1, 2, 3};
int[] b = {1, 2, 3};
if (a == b) {
    // false! vergleicht identität und nicht zustand des Objekts
}
```

### Character Klasse

```java
// Testen
Character.isDidit("0");
Character.isLetter("0");
Character.isWhitespace("0");

// Konvertieren
Character.toLowerCase("0");
Character.toUpperCase("0");
```

### Strings (&rarr;Character Arrays)

* Klassen: **String(Immutable)**, **StringBuffer(Mutable, Threadsicher)**, **StringBuilder(Mutable)**
* Bsp.:
  * `String s = new String("PRG 2")` (Erzwingt neues String-Objekt)
  * `String s2 = "PRG 2";` (JVM erzeugt String-Objekt automatisch, falss nötig)

```java
String s1 = "PRG 2";
s1.length();
s1.isEmpty();
s1.charAt();
s1.contains();
s1.indexOf();

s1.equals();
s1.equalsIgnoreCase();

s1.compareTo(s2) // <0 falls s1 im Alphabet vor s2
                // =0 falls s1 wertgleich s2
               // >0 falls s1 im Alphabet hinter s2

boolean isNullOrEmpty(String str) {
    return str == null || str.isEmpty();
}
```

```java
String s1 = "abtcd";

s1.substring(int from, int to);
s1.substring(int from);

String[] splits = s1.split("t"); // split on 't'

Scanner sc = new Scanner(System.in);

sc.nextLine(); // Liest trennzeichen "\n" ein
sc.nextInt(); // Liest Integer ein
sc.nextFloat(); // Liest Float ein

StringJoiner sj = new StringJoiner(", ");
sj.add("1").add("2").add("3");
```

### StringBuffer & StringBuilder

```java
StringBuffer sb = new StringBuffer("PRG2");

sb.append(",");
sb.append(" M2").append("GDI");
System.out.println(sb.toString());


sb.append(char c); // fügt zeichen an
sb.insert(int at, char c); // rest rückt auf
sb.deletaCharAt(int at); // Löscht zeichen, rest rückt auf
sb.toString() // erzeugt String Objekt
```

### Datentypen in Java

* Primitive Datentypen: `boolean, char, byte, short, int, long, float, double`

* Referenztypen: (zeigen auf obj im speicher)
  * Spezialisten:
    * `int[] a = new int[10];`
    * `String s = ~~new~~ "hallo"`
    * `null` leere Referenz

### Wichtige Interfaces der Java SDLiB

* **Cloneable**
  * Markierungsschnittstelle
  * &rarr; Objekt unterstützt Klonen mit `Object.clone();`
* **Comparable**
  * Objekt kann sich mit anderem Objekt vergeleichen
  * `public int compareTo(Object obj);`
* **Comperator**
  * `public int compare(Object obj1, Object obj2);`
* **Runnable**
  * enthalten `run();` methode die parallelisiert im Thread laufen kann
* **Serializable**
  * Objekte können in Bytestrom geschrieben werden (Speicher, Datenübertragung)
  * `writeObject();`
  * `readObject();`

### Comparable und Comperator

* Comperable: `compareTo(Object obj);`
* Comperator: `compare(Object obj1, Object obj2)`
  * mehrere verschiedene vergleichkritereien
* **Ergebnis:**
  * <0: Obj1 < Obj2
  * &gt;0:  Obj1 > Obj2
  * =0: Obj1 = Obj2

* Comparable:

```java
// Ohne Generics
public class Dog extends Pet implements Trainable, Comparable {
    ...
    @Override
    public int compareTo(Object o) {
        Dog other = (Dog) o;
        if (this.speed < other.speed)
            return -1;
        else if (this.speed > other.speed)
            return +1;
        else
            return 0;
    }
}

// mit Generics
public class Dog extends Pet implements Trainable, Comparable<Dog> {
    ...
    @Override
    public int compareTo(Dog o) {
        if (this.speed < o.speed)
            return -1;
        else if (this.speed > o.speed)
            return +1;
        else
            return 0;
    }
}
```

* Comperator

```java
public class PetByNameComperator implements Comperator {
    ...
    @Override
    public int compare(Object o1, Object o2) {
        Pet p1 = (Pet) o1;
        Pet p2 = (Pet) o2;

        return p1.getName().compareTo(p2.getName());
    }
}

public class PetByNameComperator implements Comperator<Pet> {
    ...
    @Override
    public int compare(Pet p1, Pet p2) {
        return p1.getName().compareTo(p2.getName());
    }
}
```

### Java Klassenbibliothek

* 208 Pakete, 2000 Klassen
* &rarr; Plattformunabhängigkeit (Platformspezifik anstrahiert in Klassen)
* Bsp.:
  * Datenstrukturen
  * Ein- & Ausgabe
  * GUI (Java FX, Swing)
  * Netwerkprogrammierung

```java
package derzeitiges_packet; // zur abgrenzung von sichbarkeiten

import java.io.IOException; // Import Klass
import java.util.* // import all Klasses
```

* Module(IntelliJ) &#8800; Packages(Java)

* Basisklass Object (java.lang.Object) ist implizite Oberklasse aller Objekte
  * methods: `.toString();`, `.equals();`, `.hashCode();`, `.clone();`, `.getClass();`

* `.toString();` empfohlen zu überschreiben
  * in Klasse Object: `<Klassenname>@<Hashwert/ID des Objekts>`

```java
@Override
public String toString() {
    return name + "-" + phone;
}
```

* `.equals();` empfohlen zu überschreiben
  1. `obj == null` &rarr; false
  2. `obj == this` &rarr; true
  3. `this.getClass().equals(obj.getClass())` &rarr; true
  4. evtl.: `super.equals();`
  5. Vergleiche Attribute

```java
@Override
public boolean equals(Object obj) {
    return (this == obj);
}
```

### .clone()

* Flache Kopie:
  * primitive datentypen werden kopiert
  * Objekte referenziert

* Tiefe Kopie:
  * Alle Attribute (auch objekte) werden echt Kopiert

* `implements Clonable` (Makierungsschnittstelle)

```java
class Person implements Cloneable {
    private String name;
    private int age;
    private MyClass attr;

    public Object clone() throws CloneNotSupportedException {
        Person newPers = (Person) super.clone();
        newPers.attr = (MyClass) attr.clone();
        newPers.age = age;
        newPers.name = name;
        newPers.name = name.clone(); // String ist ein Object! -> .clone()
        return newPers;
    }
}
```

### Wrapper-Klassen

* Bieten Statische methoden für zu Strings werden, strings Parsen
* Notwendig für Datenstrukturen
* Generics nur mit Wrapper-Klassen

* Object
  * Number
    * Byte
    * Short
    * Integer
    * Long
    * Double
    * Float
    * BigInteger
    * BigDecimal (immutable, fließkommazahlen, für arichmetische berechnungen, konvertierung, vergleichsmethoden)

### java.lang.System

* `System.in`, `System.out` (IO-Streams)
* `System.out.println("Hallo welt!");`
* `String javaVersion = System.getProperty("java.version")` (Eigenschaften Laufzeitsystem)
* `System.exit(1)`

### Klasse Class

```java
Person p = new Person("Mueller", 10);
System.out.println(p.getClass().getName());
```

## 07_Collections

* Einzellelemente: `implemetns Collection`
* Map-Datentrukturen(Key, Value): `implemetns Map`
* Interface List: ArrayList, LinkedList
* Set(keine duplikate): `implemetns Collection`
  * `add(); remove(); contains();`
  * HashSet: O(n)
  * TreeSet: O(log n), (Sortiert bezüglich Ordnung), `first(); last();`

### Map<K, V>

* Jedes Element hat Key und Value Paar
* Annahme: Key sind eindeutig!
* 2 Generics: Key, Value
* HashMap<K,V>
* TreeMap<K,V> (Binärer-Suchbaum)

### Iterrieren

```java
List<String> list = new ArrayList<String>();
Iterator<String> iter = list.iterator();

while (iter.hasNext()) {
    String temp = iter.next(); // do s.th
}
```

```java
Set<String> set = new TreeSet<String>();
Iterator<String> iter = set.iterator();

while (iter.hasNext()) {
    String temp = iter.next(); // do s.th
}
```

### bei Maps

```java
Map<String, Integer> map = new HashMap<String, Integer>();
Set<String> set = map.keySet();
Iterator<String> iter = set.iterator(); // über key

while (iter.hasNext()) {
    String key = iter.next();
    Integer val = map.get(key)
}
```

```java
Map<String, Integer> map = new HashMap<String, Integer>();

for (Map.Entry<String,Integer> e : map.entrySet()) {
    String key = e.getKey();
    Integer val = e.getValue();
}
```

## 08_Exceptions

* Fehler treten auf:
  * keim Kompilieren: Syntax-Fehler, Typüberprüfung (Generics)
  * zur Laufzeit: Logische fehler im Programm, fehlerhafte bedienung durch nutzer, Datei- oder Netzwerkprobleme
* Robuste Programme:
  * sind Vorbereitet auf Laufzeitfehler
  * reagieren Kontroliert
* Logische Fehler &rarr; Programm anhalten
* Bedienungsfehler &rarr; Aufforderung zur Korrektur
* Problem in JVM &rarr; Kaum sinnvolle Maßnahmen

```java
try {
    int div = scanner.NextInt();
    int x = (500/div);
} catch (ArithemticException e) { // wenn div = 0
    e.printStackTrace();
} catch (InputMissmatchException e) {
    System.out.println("Name of exception: 0" + e.getClass().getName());
    System.out.println("Message content: " + e.getMessage());
    System.out.println("String representation: c" + e.toString());
} finally {
    // todo
}
```

* try/catch: einschließen der problematischen bereiche
* throws: weiterleiten der ausnahme an den Aufrufer
* Es genügt einen Fehler der Oberklasse abzufangen!

### checked exceptions (Geprüfte Ausnahmen)

* Compiler besteht auf `try/catch` oder `throws`
  * Bsp.: IOException (z.b. Datei Exestiert nicht)
* IDE gibt Hinweise

### unchecked exceptions (Ungeprüfte Ausnahmen)

* Ausnahmebehandlung Optional, Compiler besteht nicht auf `try/catch` oder throws
* Grund: so müsste fast jede Klasse `try/catch` oder `throws` haben
* Meist: Denkfehler des Programierers
  * Bsp.: Alle Unterklassen von RunTimeException
    * `ArithmeticException`, `ArrayIndexOutOfBoundsException`, `NullPointerException`, `IllegalArgumentException`,

### Error

* Fehler der JVM
* Keine Reaktion möglich
* Bsp.:
  * `OutOfMemoryError`, `ClassFormatError`, `VirtualMachineError`,

### Auslösen von ausnahmen

* `throw` ~~`throws`~~

```java
public class Person extends Object implements Comparable<Person> {
private String name;
private int age;
// constructor(s)
public Person(String n, int a) {
    if (age < 18) {
        throw new IllegalArgumentException("Minderjährige Person nicht erlaubt!");
    }
    this.name = n;
    this.age = a;
}
. . .
```

### Defenition eigener Exceptions

* cheked exception: `MyException extends Exception`
* uncheked exception: `MyException extends RuntimeException`

```java
// Checked Exception
public class MyException extends Exception {
    public MyException() {};
    public MyException(String s) {
        super(s);
    }
}

// verwendung

...
throw new MyException("Es ist ein missgeschick passiert...")
...
```

```java
@Test(expected = ArrayIndexOutOfBoundsException.class)
public void testBadIndex() {
    int[] array = new int[4];
    int i = array[4]; // should fail
}
```

```java
```
