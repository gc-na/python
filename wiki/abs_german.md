<!--
Meta Description: # Python `abs()`: Der absolute Wert in Python verstehen ## Synopsis Die Funktion `abs()` in Python wird verwendet, um den absoluten Wert einer Zahl zu...
Meta Keywords: abs, der, python, wert, den
-->

# Python `abs()`: Der absolute Wert in Python verstehen

## Synopsis
Die Funktion `abs()` in Python wird verwendet, um den absoluten Wert einer Zahl zu berechnen. Sie ist eine eingebaute Funktion, die für Ganzzahlen, Gleitkommazahlen und komplexe Zahlen funktioniert.

## Dokumentation
Die Funktion `abs()` gibt den Betrag (absoluten Wert) einer Zahl zurück. Der absolute Wert einer Zahl ist der Wert ohne Vorzeichen. Diese Funktion ist besonders nützlich in mathematischen Berechnungen, wo nur der Betrag einer Zahl von Bedeutung ist.

### Verwendung
Die grundlegende Syntax der `abs()` Funktion lautet:

```python
abs(x)
```

- **Parameter**: 
  - `x`: Eine Zahl (int, float, oder complex).
  
- **Rückgabewert**: 
  - Gibt den absoluten Wert von `x` zurück.

### Details
- Bei Ganzzahlen und Gleitkommazahlen gibt `abs()` einfach den Wert ohne Vorzeichen zurück.
- Bei komplexen Zahlen gibt `abs()` den Betrag der komplexen Zahl zurück, der berechnet wird als die Quadratwurzel der Summe der Quadrate der Real- und Imaginärteile.

## Beispiele

### Beispiel 1: Ganzzahlen
```python
print(abs(-5))  # Ausgabe: 5
```

### Beispiel 2: Gleitkommazahlen
```python
print(abs(-3.14))  # Ausgabe: 3.14
```

### Beispiel 3: Komplexe Zahlen
```python
print(abs(3 + 4j))  # Ausgabe: 5.0
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von `abs()` ist, dass sie nur für positive Zahlen funktioniert. Tatsächlich funktioniert sie für alle numerischen Typen in Python. 

Ein weiterer Punkt ist, dass `abs()` für komplexe Zahlen den Betrag berechnet, was für einige Benutzer möglicherweise nicht sofort offensichtlich ist. Hierbei wird die mathematische Formel für den Betrag verwendet: \( |a + bi| = \sqrt{a^2 + b^2} \).

## Ein-Satz-Zusammenfassung
Die `abs()` Funktion in Python berechnet den absoluten Wert einer Zahl, unabhängig davon, ob es sich um eine Ganzzahl, Gleitkommazahl oder komplexe Zahl handelt.