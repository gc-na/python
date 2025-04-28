<!--
Meta Description: # `getattr` in Python: Dynamischer Zugriff auf Attribute von Objekten ## Synopsis `getattr` ist eine eingebaute Funktion in Python, die es ermöglicht,...
Meta Keywords: wird, name, getattr, der, person
-->

# `getattr` in Python: Dynamischer Zugriff auf Attribute von Objekten

## Synopsis
`getattr` ist eine eingebaute Funktion in Python, die es ermöglicht, auf Attribute eines Objekts dynamisch zuzugreifen. Sie wird häufig verwendet, um eine flexible und dynamische Programmierung zu ermöglichen.

## Dokumentation
Die Funktion `getattr` hat die folgende Syntax:

```python
getattr(object, name[, default])
```

### Parameter:
- **object**: Das Objekt, von dem das Attribut abgerufen werden soll.
- **name**: Der Name des Attributs, das als String angegeben wird.
- **default** (optional): Ein Standardwert, der zurückgegeben wird, wenn das Attribut nicht gefunden wird. Wenn dieser Parameter nicht angegeben wird und das Attribut nicht existiert, wird eine `AttributeError`-Ausnahme ausgelöst.

### Zweck:
`getattr` wird verwendet, um auf Attribute eines Objekts zuzugreifen, ohne den Namen des Attributs direkt in den Code zu schreiben. Dies ist besonders nützlich in Fällen, in denen der Attributname zur Laufzeit ermittelt wird.

### Verwendung:
Die Funktion wird häufig in dynamischen Anwendungen, Reflection, und bei der Arbeit mit Datenstrukturen wie Dictionaries oder Klassen verwendet.

## Beispiele

### Beispiel 1: Einfacher Zugriff auf Attribute
```python
class Person:
    def __init__(self, name):
        self.name = name

person = Person("Max")
name = getattr(person, 'name')
print(name)  # Ausgabe: Max
```

### Beispiel 2: Verwendung des Standardwerts
```python
class Person:
    def __init__(self, name):
        self.name = name

person = Person("Max")
age = getattr(person, 'age', 30)
print(age)  # Ausgabe: 30, da 'age' nicht existiert
```

### Beispiel 3: Dynamischer Attributzugriff
```python
class Auto:
    def __init__(self, marke):
        self.marke = marke

mein_auto = Auto("BMW")
attribut_name = 'marke'
marke = getattr(mein_auto, attribut_name)
print(marke)  # Ausgabe: BMW
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `getattr` ist das Verständnis, wann der `default`-Parameter benötigt wird. Wenn ein Attribut nicht existiert und kein Standardwert angegeben ist, wird ein `AttributeError` ausgelöst. Es ist auch wichtig, darauf zu achten, dass der Name des Attributs als String übergeben wird; andernfalls wird ein `TypeError` ausgelöst.

Zusätzlich kann der Einsatz von `getattr` in Kombination mit anderen Funktionen wie `setattr` und `delattr` zur Laufzeit eine mächtige Dynamik in der Programmierung ermöglichen.

## Eine Zeilen Zusammenfassung
`getattr` ist eine Python-Funktion, die den dynamischen Zugriff auf Attribute eines Objekts ermöglicht und dabei einen optionalen Standardwert bereitstellt, falls das Attribut nicht vorhanden ist.