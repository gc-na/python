<!--
Meta Description: # UnboundLocalError in Python: Fehlerbehebung und Verständnis ## Synopsis Der **UnboundLocalError** in Python tritt auf, wenn eine lokale Variable in ...
Meta Keywords: variable, sie, unboundlocalerror, wird, python
-->

# UnboundLocalError in Python: Fehlerbehebung und Verständnis

## Synopsis
Der **UnboundLocalError** in Python tritt auf, wenn eine lokale Variable in einer Funktion verwendet wird, bevor sie zugewiesen wurde. Dies kann zu Verwirrung führen, wenn der Code nicht korrekt strukturiert ist.

## Documentation
### Zweck
Der **UnboundLocalError** ist ein spezifischer Fehler, der darauf hinweist, dass eine lokale Variable, die innerhalb einer Funktion deklariert wurde, verwendet wurde, ohne dass ihr zuvor ein Wert zugewiesen wurde. Dieser Fehler hilft dabei, Programmierfehler zu identifizieren, die durch die falsche Handhabung von Variablen entstehen.

### Verwendung
Dieser Fehler tritt typischerweise auf, wenn:
- Eine Variable innerhalb einer Funktion deklariert wird, jedoch nicht initialisiert ist, bevor sie verwendet wird.
- Eine globale Variable mit demselben Namen existiert, die jedoch innerhalb der Funktion als lokal betrachtet wird.

### Details
- Der Fehler wird zur Laufzeit ausgelöst, wodurch die Ausführung des Programms gestoppt wird.
- Um diesen Fehler zu beheben, sollte sichergestellt werden, dass alle lokalen Variablen vor ihrer Verwendung initialisiert sind.

## Examples
Hier sind einige einfache Beispiele, die den **UnboundLocalError** verdeutlichen:

### Beispiel 1: UnboundLocalError durch nicht initialisierte Variable
```python
def beispiel_funktion():
    print(x)  # Versuch, auf 'x' zuzugreifen, bevor sie definiert ist
    x = 10

beispiel_funktion()
```
**Ausgabe:**
```
UnboundLocalError: local variable 'x' referenced before assignment
```

### Beispiel 2: Verwendung einer globalen Variable
```python
x = 5

def beispiel_funktion():
    print(x)  # Fehler, da 'x' als lokal betrachtet wird
    x = 10

beispiel_funktion()
```
**Ausgabe:**
```
UnboundLocalError: local variable 'x' referenced before assignment
```

### Beispiel 3: Korrekte Verwendung von globalen Variablen
```python
x = 5

def beispiel_funktion():
    global x  # 'x' als global deklarieren
    print(x)  # Jetzt funktioniert es, da 'x' global ist
    x = 10

beispiel_funktion()
print(x)  # Ausgabe: 10
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von Variablen in Python ist die Unterscheidung zwischen lokalen und globalen Variablen. Wenn eine Variable in einer Funktion deklariert wird, betrachtet Python sie standardmäßig als lokal. Dies kann zu einem **UnboundLocalError** führen, wenn Sie versuchen, auf die Variable zuzugreifen, bevor sie einen Wert erhält. Um dies zu vermeiden, stellen Sie sicher, dass alle lokalen Variablen initialisiert werden, bevor Sie sie verwenden. Alternativ können Sie das Schlüsselwort `global` verwenden, um auf eine globale Variable innerhalb einer Funktion zuzugreifen.

## One Line Summary
Der **UnboundLocalError** in Python tritt auf, wenn eine lokale Variable verwendet wird, bevor ihr ein Wert zugewiesen wurde.