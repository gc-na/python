<!--
Meta Description: # Python dict: Alles, was Sie über Dictionaries in Python wissen müssen ## Synopsis Ein Dictionary in Python ist eine eingebaute Datentypstruktur, die...
Meta Keywords: python, schlüssel, die, sie, ein
-->

# Python dict: Alles, was Sie über Dictionaries in Python wissen müssen

## Synopsis
Ein Dictionary in Python ist eine eingebaute Datentypstruktur, die eine Zuordnung von Schlüssel-Wert-Paaren ermöglicht. Es ist eine der vielseitigsten und am häufigsten verwendeten Datenstrukturen in Python.

## Dokumentation
Ein Dictionary (dict) in Python ist eine ungeordnete Sammlung von Elementen, die als Schlüssel-Wert-Paare gespeichert werden. Der Hauptzweck eines Dictionaries besteht darin, Daten auf eine Weise zu organisieren, die einen schnellen Zugriff auf die Werte über ihre zugehörigen Schlüssel ermöglicht.

### Grundlegende Merkmale:
- **Schlüsselspeicherung**: Jeder Schlüssel in einem Dictionary muss einzigartig sein und kann nur einmal verwendet werden. Schlüssel können verschiedene Datentypen haben, einschließlich Strings, Zahlen und sogar Tuples.
- **Wertspeicherung**: Die Werte, die mit den Schlüsseln verknüpft sind, können beliebige Datentypen sein, einschließlich Listen, Strings, Zahlen oder sogar andere Dictionaries.
- **Zugriff und Modifikation**: Sie können auf Werte zugreifen, sie hinzufügen oder ändern, indem Sie den zugehörigen Schlüssel verwenden.

### Syntax
```python
dictionary_name = {key1: value1, key2: value2, ...}
```

### Erstellen eines Dictionaries
Ein Dictionary kann auf verschiedene Arten erstellt werden:
1. Mit geschweiften Klammern:
   ```python
   my_dict = {'name': 'Max', 'alter': 25}
   ```
2. Mit der `dict()` Funktion:
   ```python
   my_dict = dict(name='Max', alter=25)
   ```

## Beispiele
### Beispiel 1: Erstellen und Zugreifen auf ein Dictionary
```python
# Erstellen eines Dictionaries
person = {'name': 'Anna', 'alter': 30, 'stadt': 'Berlin'}

# Zugriff auf Werte
print(person['name'])  # Ausgabe: Anna
print(person['alter'])  # Ausgabe: 30
```

### Beispiel 2: Hinzufügen und Ändern von Werten
```python
# Hinzufügen eines neuen Schlüssels
person['beruf'] = 'Ingenieur'

# Ändern eines bestehenden Wertes
person['alter'] = 31

print(person)  # Ausgabe: {'name': 'Anna', 'alter': 31, 'stadt': 'Berlin', 'beruf': 'Ingenieur'}
```

### Beispiel 3: Iteration über ein Dictionary
```python
for key, value in person.items():
    print(f'Schlüssel: {key}, Wert: {value}')
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von Dictionaries ist die Annahme, dass sie geordnet sind. Bis Python 3.6 hatte die Reihenfolge der Elemente keine Garantie. Ab Python 3.7 sind Dictionaries jedoch geordnet, was bedeutet, dass die Elemente in der Reihenfolge ihrer Einfügung gespeichert werden. 

Ein weiterer Punkt ist, dass Schlüssel unveränderlich sein müssen. Das bedeutet, dass Sie keine Listen oder andere veränderbare Datentypen als Schlüssel verwenden können. Wenn Sie versuchen, einen veränderbaren Typ als Schlüssel zu verwenden, erhalten Sie einen `TypeError`.

## One Line Summary
Ein Dictionary in Python ist eine flexible und leistungsstarke Datenstruktur zur Speicherung von Schlüssel-Wert-Paaren, die schnellen Zugriff und einfache Modifikation ermöglicht.