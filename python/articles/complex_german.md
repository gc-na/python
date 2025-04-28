<!--
Meta Description: # Komplexe Zahlen in Python: Verwendung des `complex` Datentyps ## Synopsis Der `complex` Datentyp in Python ermöglicht die Arbeit mit komplexen Zahle...
Meta Keywords: der, zahlen, python, komplexen, complex
-->

# Komplexe Zahlen in Python: Verwendung des `complex` Datentyps

## Synopsis
Der `complex` Datentyp in Python ermöglicht die Arbeit mit komplexen Zahlen, die aus einem Real- und einem Imaginärteil bestehen. Dieser Artikel beschreibt die Verwendung von komplexen Zahlen in Python, einschließlich ihrer Erstellung, Manipulation und grundlegender Operationen.

## Dokumentation
In Python ist der `complex` Datentyp eine eingebaute Funktion, die es ermöglicht, komplexe Zahlen zu erstellen, die in der Form `a + bj` dargestellt werden, wobei `a` der Realteil und `b` der Imaginärteil ist. Der Imaginärteil wird mit einem `j` (oder `J`) gekennzeichnet, was in Python anstelle des üblichen `i` in der Mathematik verwendet wird.

### Zweck
Der Zweck des `complex` Datentyps ist es, mathematische Operationen mit komplexen Zahlen zu ermöglichen, die in verschiedenen Bereichen wie Ingenieurwesen, Physik und Mathematik häufig vorkommen.

### Verwendung
Um eine komplexe Zahl zu erstellen, kann der `complex()`-Konstruktor oder die direkte Notation verwendet werden:
- Mit dem Konstruktor: `z = complex(realteil, imaginaerteil)`
- Mit der direkten Notation: `z = 3 + 4j`

### Details
- Der Realteil kann eine Ganzzahl oder Fließkommazahl sein.
- Der Imaginärteil muss immer mit `j` oder `J` angegeben werden.
- Es sind verschiedene mathematische Operationen wie Addition, Subtraktion, Multiplikation und Division zwischen komplexen Zahlen möglich.

## Beispiele
### Beispiel 1: Erstellen einer komplexen Zahl
```python
# Erstellung einer komplexen Zahl
z1 = complex(2, 3)
print(z1)  # Ausgabe: (2+3j)
```

### Beispiel 2: Grundlegende mathematische Operationen
```python
# Addition von komplexen Zahlen
z2 = complex(1, 2)
result = z1 + z2
print(result)  # Ausgabe: (3+5j)

# Multiplikation von komplexen Zahlen
result = z1 * z2
print(result)  # Ausgabe: (-4+7j)
```

### Beispiel 3: Zugriff auf Real- und Imaginärteil
```python
# Zugriff auf Real- und Imaginärteil
realteil = z1.real
imaginaerteil = z1.imag
print(realteil)  # Ausgabe: 2.0
print(imaginaerteil)  # Ausgabe: 3.0
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von komplexen Zahlen in Python ist die Notation des Imaginärteils. Viele Benutzer verwenden `i` anstelle von `j`, was zu einem Syntaxfehler führt. Achten Sie darauf, immer `j` zu verwenden.

Ein weiteres häufiges Problem ist das Vergessen, dass der Real- und Imaginärteil als Fließkommazahlen interpretiert werden, was zu unerwarteten Ergebnissen führen kann, wenn sie mit Ganzzahlen kombiniert werden. 

## Ein-Satz-Zusammenfassung
Der `complex` Datentyp in Python ermöglicht die einfache Erstellung und Manipulation von komplexen Zahlen für mathematische Berechnungen.