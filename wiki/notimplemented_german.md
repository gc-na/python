<!--
Meta Description: # NotImplemented in Python: Bedeutung und Verwendung ## Synopsis In Python wird das Schlüsselwort `NotImplemented` verwendet, um anzuzeigen, dass eine...
Meta Keywords: notimplemented, ist, nicht, python, die
-->

# NotImplemented in Python: Bedeutung und Verwendung

## Synopsis
In Python wird das Schlüsselwort `NotImplemented` verwendet, um anzuzeigen, dass eine bestimmte Methode oder Operation noch nicht implementiert ist. Es ist ein spezielles Singleton-Objekt, das typischerweise in benutzerdefinierten Klassen verwendet wird, um die Unterstützung für bestimmte Operationen zu signalisieren.

## Dokumentation
### Zweck
`NotImplemented` wird hauptsächlich in der Implementierung von Operatoren und Methoden verwendet, die in einer Klasse definiert sind, um zu zeigen, dass die jeweilige Funktionalität noch nicht verfügbar ist. Dies ist besonders nützlich in Fällen, in denen eine Methode nicht für alle möglichen Eingaben definiert ist, oder wenn eine Klasse eine bestimmte Funktionalität erfordert, die noch nicht implementiert wurde.

### Verwendung
Das Singleton-Objekt `NotImplemented` kann in benutzerdefinierten Methoden und Operatoren verwendet werden, um anzuzeigen, dass die Methode nicht für bestimmte Typen geeignet ist. Es kann auch als Rückgabewert verwendet werden, wenn ein Benutzer versucht, eine nicht unterstützte Operation durchzuführen.

#### Beispiel
```python
class MyNumber:
    def __add__(self, other):
        if isinstance(other, MyNumber):
            # Hier könnte die Logik zur Addition implementiert werden
            return MyNumber()  # Beispiel Rückgabe
        return NotImplemented
```

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `NotImplemented`:

### Beispiel 1: Verwendung in einer benutzerdefinierten Klasse
```python
class MyClass:
    def __sub__(self, other):
        if isinstance(other, MyClass):
            return MyClass()  # Beispiel-Rückgabe
        return NotImplemented

a = MyClass()
b = MyClass()

result = a - b  # Funktioniert
print(result)

result = a - 5  # Gibt NotImplemented zurück
print(result)  # Ausgabe: NotImplemented
```

### Beispiel 2: Verwendung in der Überladung von Operatoren
```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __mul__(self, other):
        if isinstance(other, (int, float)):
            return Vector(self.x * other, self.y * other)
        return NotImplemented

v = Vector(2, 3)
print(v * 2)  # Erfolgreiche Multiplikation
print(v * 'a')  # Gibt NotImplemented zurück
```

## Erklärung
Ein häufiger Fallstrick bei der Verwendung von `NotImplemented` ist das Missverständnis darüber, wann es verwendet werden sollte. `NotImplemented` sollte zurückgegeben werden, wenn ein Operator oder eine Methode nicht mit dem gegebenen Typ arbeiten kann. Dies ermöglicht es Python, alternative Implementierungen zu versuchen, anstatt einen Fehler zu werfen. Es ist wichtig, sicherzustellen, dass `NotImplemented` nur dann zurückgegeben wird, wenn die Operation tatsächlich nicht unterstützt wird.

Ein weiterer Punkt ist, dass `NotImplemented` nicht dasselbe ist wie `None`. Es handelt sich um ein spezifisches Singleton, das für die Interoperabilität zwischen verschiedenen Typen in Python entwickelt wurde.

## Einzeilensummary
`NotImplemented` ist ein spezielles Singleton in Python, das anzeigt, dass eine Methode oder Operation nicht implementiert ist oder für den gegebenen Typ nicht unterstützt wird.