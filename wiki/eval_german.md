<!--
Meta Description: # eval in Python: Verwendung, Beispiele und Tipps ## Synopsis Die `eval`-Funktion in Python ermöglicht die Ausführung von Python-Ausdrücken, die als Z...
Meta Keywords: eval, die, python, werden, und
-->

# eval in Python: Verwendung, Beispiele und Tipps

## Synopsis
Die `eval`-Funktion in Python ermöglicht die Ausführung von Python-Ausdrücken, die als Zeichenkette übergeben werden. Sie ist ein mächtiges Werkzeug, sollte jedoch mit Vorsicht verwendet werden, da sie Sicherheitsrisiken birgt.

## Dokumentation
Die `eval`-Funktion hat die folgende Syntax:

```python
eval(expression, globals=None, locals=None)
```

### Zweck
`eval` wird verwendet, um einen Ausdruck, der als String vorliegt, in Python auszuwerten und das Ergebnis zurückzugeben. Dies ist besonders nützlich, wenn dynamisch generierte Ausdrücke zur Laufzeit ausgewertet werden müssen.

### Verwendung
- **expression**: Ein String, der den auszuwertenden Python-Ausdruck enthält.
- **globals** (optional): Ein Dictionary, das globale Variablen enthält, die innerhalb des Ausdrucks verfügbar sind.
- **locals** (optional): Ein Dictionary, das lokale Variablen enthält, die innerhalb des Ausdrucks verfügbar sind.

Wenn `globals` und `locals` nicht angegeben werden, verwendet `eval` die aktuellen globalen und lokalen Variablen.

### Details
Die Funktion kann nur Ausdrücke auswerten, nicht aber vollständige Anweisungen. Beispielsweise funktioniert `eval("1 + 1")`, aber `eval("for i in range(3): print(i)")` führt zu einem Fehler.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `eval`:

1. **Einfacher mathematischer Ausdruck**:

   ```python
   result = eval("2 + 3 * 4")
   print(result)  # Ausgabe: 14
   ```

2. **Verwendung von Variablen**:

   ```python
   x = 10
   result = eval("x + 5")
   print(result)  # Ausgabe: 15
   ```

3. **Globale und lokale Variablen**:

   ```python
   x = 5
   def test_eval():
       y = 10
       return eval("x + y", globals(), locals())
   
   print(test_eval())  # Ausgabe: 15
   ```

## Erklärung
Die Verwendung von `eval` kann riskant sein, insbesondere wenn der eingegebene Ausdruck von Benutzern stammt. Potenzielle Sicherheitsrisiken bestehen darin, dass schadhafter Code ausgeführt werden kann, wenn beispielsweise `eval` auf unsichere Eingaben angewendet wird. Daher sollte `eval` nur verwendet werden, wenn man die vollständige Kontrolle über die Eingabe hat.

### Häufige Fallstricke:
- **Sicherheitsrisiken**: Verwenden Sie `eval` nicht mit Benutzereingaben, es sei denn, Sie haben sie gründlich validiert.
- **Fehlende Anweisungen**: `eval` kann nur Ausdrücke auswerten, keine vollständigen Anweisungen oder Funktionen.

## Zusammenfassung in einem Satz
Die `eval`-Funktion in Python wertet Python-Ausdrücke aus, die als String übergeben werden, und sollte mit Vorsicht aufgrund potenzieller Sicherheitsrisiken eingesetzt werden.