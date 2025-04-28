<!--
Meta Description: # Python chr() – Zeichen aus einem Unicode-Codepunkt erstellen ## Synopsis Die `chr()`-Funktion in Python wandelt einen ganzzahligen Unicode-Codepunkt...
Meta Keywords: chr, zeichen, unicode, python, codepunkt
-->

# Python chr() – Zeichen aus einem Unicode-Codepunkt erstellen

## Synopsis
Die `chr()`-Funktion in Python wandelt einen ganzzahligen Unicode-Codepunkt in das entsprechende Zeichen um. Diese Funktion ist nützlich, um Zeichen aus deren Unicode-Werten zu erzeugen und zu manipulieren.

## Dokumentation
Die `chr()`-Funktion ist eine eingebaute Funktion in Python, die einen einzelnen Parameter akzeptiert: einen ganzzahligen Wert, der den Unicode-Codepunkt repräsentiert. Der Rückgabewert ist das Zeichen, das diesem Codepunkt entspricht.

### Verwendung
```python
chr(codepoint)
```

- **Parameter:**
  - `codepoint`: Ein ganzzahliger Wert (int), der den Unicode-Codepunkt des gewünschten Zeichens angibt. Der Wert muss im Bereich von 0 bis 1114111 (0x10FFFF) liegen.

### Rückgabewert
Der Rückgabewert ist ein einzelnes Zeichen (str), das dem angegebenen Unicode-Codepunkt entspricht.

### Beispiel:
```python
# Beispiel zur Verwendung von chr()
zeichen = chr(97)  # Gibt 'a' zurück
print(zeichen)     # Ausgabe: a
```

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung der `chr()`-Funktion:

1. **Einzelnes Zeichen aus Unicode-Codepunkt:**
   ```python
   print(chr(65))  # Ausgabe: A
   ```

2. **Zeichen für verschiedene Codepunkte:**
   ```python
   print(chr(8364))  # Ausgabe: €
   print(chr(9786))   # Ausgabe: ☺
   ```

3. **Zeichen aus dem Unicode-Bereich für Emojis:**
   ```python
   print(chr(128512))  # Ausgabe: 😀
   ```

## Erklärung
Einige häufige Fallstricke und wichtige Hinweise zur Verwendung der `chr()`-Funktion:

- **Zulässige Werte:** Der übergebene Codepunkt muss im Bereich von 0 bis 1114111 liegen. Andernfalls wird ein `ValueError` ausgelöst.
  
- **Eingabewerte:** Wenn ein Wert außerhalb dieses Bereichs eingegeben wird, wird eine Fehlermeldung angezeigt. Zum Beispiel:
  ```python
  print(chr(2000000))  # Dies führt zu einem ValueError.
  ```

- **Unicode und Zeichenkodierung:** `chr()` ist besonders nützlich, wenn man mit Unicode-Texten arbeitet oder eine spezifische Zeichenkodierung benötigt. Es ist wichtig, sich der Unterschiede zwischen ASCII und Unicode bewusst zu sein, da `chr()` über die ASCII-Zeichen hinausgeht.

## Ein-Satz-Zusammenfassung
Die `chr()`-Funktion in Python konvertiert einen Unicode-Codepunkt in das entsprechende Zeichen und ist äußerst nützlich für die Arbeit mit Unicode-Zeichen.