<!--
Meta Description: # classmethod in Python: Eine umfassende Anleitung ## Synopsis Die `classmethod`-Dekorator in Python ermöglicht es, Methoden zu definieren, die an die...
Meta Keywords: die, classmethod, klasse, der, auf
-->

# classmethod in Python: Eine umfassende Anleitung

## Synopsis
Die `classmethod`-Dekorator in Python ermöglicht es, Methoden zu definieren, die an die Klasse und nicht an eine Instanz der Klasse gebunden sind. Diese Methoden können auf die Klasse selbst zugreifen und sind nützlich, um Klassenattribute oder Klassenmethoden zu bearbeiten.

## Dokumentation
Der `classmethod`-Dekorator wird verwendet, um eine Methode zu kennzeichnen, die als Methode der Klasse fungiert. Im Gegensatz zu normalen Methoden, die immer das erste Argument `self` (die Instanz der Klasse) erwarten, erwarten Klassenmethoden das erste Argument `cls`, das auf die Klasse selbst verweist. 

### Zweck
- **Zugriff auf Klassenattribute:** `classmethod` ermöglicht es Methoden, auf Attribute der Klasse zuzugreifen und diese zu modifizieren.
- **Erleichterung von Factory-Methoden:** Sie können verwendet werden, um alternative Konstruktoren zu erstellen, die Instanzen der Klasse erzeugen, ohne die Standardinitialisierung zu verwenden.

### Verwendung
Die Verwendung von `classmethod` erfolgt durch das Hinzufügen des `@classmethod`-Dekorators vor der Methode. Hier ist die grundlegende Syntax:

```python
class MeineKlasse:
    @classmethod
    def meine_methode(cls, argument):
        # Logik hier
```

## Beispiele
Hier sind einige grundlegende Beispiele zur Veranschaulichung der Verwendung von `classmethod`.

### Beispiel 1: Einfaches classmethod

```python
class Tier:
    tierart = "Allgemein"

    @classmethod
    def zeige_tierart(cls):
        return cls.tierart

print(Tier.zeige_tierart())  # Ausgabe: Allgemein
```

### Beispiel 2: Factory-Methode

```python
class Auto:
    def __init__(self, marke):
        self.marke = marke

    @classmethod
    def von_string(cls, marken_string):
        marke = marken_string.split("-")[0]
        return cls(marke)

mein_auto = Auto.von_string("BMW-X5")
print(mein_auto.marke)  # Ausgabe: BMW
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `classmethod` ist das Missverständnis darüber, wann man `cls` anstelle von `self` verwenden sollte. Während `self` die spezifische Instanz der Klasse referenziert, bezieht sich `cls` auf die Klasse selbst, was bedeutet, dass Sie auf Klassenattribute und -methoden zugreifen und diese ändern können, ohne eine Instanz der Klasse zu erstellen.

Ein weiterer Punkt ist, dass `classmethod` nicht die gleiche Flexibilität wie Instanzmethoden bietet, da sie nicht auf Instanzattribute zugreifen können. Wenn Sie also auf spezifische Eigenschaften einer Instanz zugreifen müssen, sollten Sie eine Instanzmethode verwenden.

## Ein-Satz-Zusammenfassung
Der `classmethod`-Dekorator in Python ermöglicht es, Methoden zu erstellen, die auf die Klasse selbst zugreifen, anstatt auf eine spezifische Instanz.