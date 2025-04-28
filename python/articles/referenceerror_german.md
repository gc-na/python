<!--
Meta Description: # ReferenceError in Python: Umgang mit nicht definierten Variablen ## Zusammenfassung Der `ReferenceError` in Python tritt auf, wenn ein lokal definie...
Meta Keywords: referenceerror, die, nicht, auf, eine
-->

# ReferenceError in Python: Umgang mit nicht definierten Variablen

## Zusammenfassung
Der `ReferenceError` in Python tritt auf, wenn ein lokal definierter oder globaler Name nicht gefunden werden kann. Dies geschieht häufig, wenn auf eine Variable zugegriffen wird, die entweder nicht definiert oder außerhalb des Gültigkeitsbereichs ist.

## Dokumentation
### Zweck
Der `ReferenceError` ist eine spezielle Ausnahme, die in Python geworfen wird, wenn ein Code auf eine nicht definierte oder nicht mehr existierende Referenz zugreift. Diese Ausnahme hilft Entwicklern, Probleme beim Zugriff auf Variablen zu identifizieren und zu beheben.

### Verwendung
Ein `ReferenceError` wird normalerweise in den folgenden Szenarien ausgelöst:
- Der Zugriff auf eine Variable, die nicht definiert wurde.
- Der Versuch, auf eine Variable zuzugreifen, die außerhalb des Gültigkeitsbereichs (Scope) existiert.
- Der Verweis auf eine Funktion oder Methode, die nicht verfügbar ist.

### Details
In Python wird der `ReferenceError` durch die `ReferenceError`-Klasse repräsentiert, die von der Basisklasse `Exception` abgeleitet ist. Diese Ausnahme kann in einem `try-except`-Block behandelt werden, um die Programmoberfläche zu schützen und eine kontrollierte Fehlerbehandlung zu ermöglichen.

## Beispiele
Hier sind einige grundlegende Beispiele, die die Entstehung eines `ReferenceError` zeigen:

### Beispiel 1: Zugriff auf eine nicht definierte Variable
```python
try:
    print(x)
except ReferenceError as e:
    print(f"ReferenceError: {e}")
```
*Erklärung: Hier wird auf die Variable `x` zugegriffen, die nicht definiert ist, was zu einem `ReferenceError` führt.*

### Beispiel 2: Zugriff auf eine lokale Variable außerhalb des Gültigkeitsbereichs
```python
def my_function():
    y = 10

try:
    my_function()
    print(y)
except ReferenceError as e:
    print(f"ReferenceError: {e}")
```
*Erklärung: Die Variable `y` ist nur innerhalb von `my_function` definiert, sodass der Zugriff außerhalb des Gültigkeitsbereichs einen `ReferenceError` auslöst.*

## Erklärung
Häufige Stolpersteine beim Umgang mit `ReferenceError` sind:
- **Unbeabsichtigtes Überschreiben:** Manchmal wird eine Variable absichtlich oder versehentlich in einem anderen Gültigkeitsbereich überschrieben.
- **Tipparbeiten:** Tippfehler beim Variablennamen können ebenfalls zu einem `ReferenceError` führen.
- **Funktionale Programmierung:** Bei der Verwendung von Funktionen, die lokale Variablen definieren, sollte man darauf achten, dass diese nicht außerhalb der Funktion verwendet werden.

Es ist wichtig, den Gültigkeitsbereich zu verstehen und sicherzustellen, dass alle benötigten Variablen vor ihrem Zugriff definiert sind.

## Ein-Satz-Zusammenfassung
Ein `ReferenceError` in Python tritt auf, wenn versucht wird, auf eine nicht definierte oder nicht zugängliche Variable zuzugreifen.