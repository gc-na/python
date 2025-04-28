<!--
Meta Description: # AssertionError in Python: Fehlerbehandlung und Debugging ## Synopsis `AssertionError` ist eine integrierte Ausnahme in Python, die ausgelöst wird, w...
Meta Keywords: python, die, assertionerror, ist, wird
-->

# AssertionError in Python: Fehlerbehandlung und Debugging

## Synopsis
`AssertionError` ist eine integrierte Ausnahme in Python, die ausgelöst wird, wenn eine Assertionsbedingung fehlschlägt. Sie wird häufig zur Validierung von Annahmen im Code verwendet, um sicherzustellen, dass bestimmte Bedingungen erfüllt sind.

## Documentation
In Python wird die `assert`-Anweisung verwendet, um Bedingungen zu überprüfen. Wenn die Bedingung als `False` ausgewertet wird, wird eine `AssertionError`-Ausnahme ausgelöst. Dies ist besonders nützlich während der Entwicklung, um Fehler frühzeitig zu erkennen und sicherzustellen, dass der Code sich wie erwartet verhält.

### Zweck
Der Hauptzweck von `AssertionError` ist die Fehlererkennung während der Entwicklungsphase. Durch Assertions können Entwickler sicherstellen, dass ihre Programmannahmen gültig sind und unerwartete Zustände schnell identifiziert werden.

### Verwendung
Die grundlegende Syntax für die Verwendung von `assert` ist:

```python
assert Bedingung, "Fehlermeldung"
```

Hierbei wird `Bedingung` überprüft, und wenn sie `False` ist, wird eine `AssertionError` mit der angegebenen Fehlermeldung ausgelöst.

### Details
- `assert` kann in verschiedenen Umgebungen eingesetzt werden, ist jedoch standardmäßig in Produktionsumgebungen deaktiviert, wenn Python im Optimierungsmodus (`-O`) ausgeführt wird.
- Assertions sollten nicht für die normale Fehlerbehandlung verwendet werden, sondern sind eher ein Werkzeug für die Entwicklung und das Debugging.

## Examples
### Beispiel 1: Grundlegende Assertion
```python
def berechne_quadrat(x):
    assert x >= 0, "x muss nicht-negativ sein"
    return x * x

print(berechne_quadrat(4))  # Gibt 16 zurück
print(berechne_quadrat(-1))  # Löst AssertionError aus
```

### Beispiel 2: Assertion mit Fehlermeldung
```python
def teile(a, b):
    assert b != 0, "Der Divisor darf nicht null sein"
    return a / b

print(teile(10, 2))  # Gibt 5.0 zurück
print(teile(10, 0))  # Löst AssertionError aus
```

## Explanation
- **Häufige Fallstricke:** Ein häufiger Fehler ist es, Assertions für die reguläre Fehlerbehandlung zu verwenden. Assertions sollten nur zur Validierung von Annahmen verwendet werden und nicht für Eingabewerte.
- **Optimierungsmodus:** Wenn Sie Python im Optimierungsmodus ausführen, werden alle Assertions ignoriert. Dies kann zu unerwartetem Verhalten führen, wenn Sie sich auf Assertions verlassen.
- **Lesbarkeit:** Übermäßige Verwendung von Assertions kann den Code unübersichtlich machen. Verwenden Sie sie sparsam und nur wenn nötig.

## One Line Summary
`AssertionError` in Python signalisiert, dass eine Assertion fehlschlug, was bei der Validierung von Annahmen im Code hilfreich ist.