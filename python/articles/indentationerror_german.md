<!--
Meta Description: # IndentationError in Python: Ursachen und Lösungen ## Synopsis Ein `IndentationError` in Python tritt auf, wenn der Code nicht richtig eingerückt ist...
Meta Keywords: python, und, ist, die, indentationerror
-->

# IndentationError in Python: Ursachen und Lösungen

## Synopsis
Ein `IndentationError` in Python tritt auf, wenn der Code nicht richtig eingerückt ist. In Python ist die Einrückung entscheidend für die Struktur und Lesbarkeit des Codes, da sie die Blockzugehörigkeit von Anweisungen definiert.

## Dokumentation
### Zweck
Der `IndentationError` ist ein Syntaxfehler, der auftritt, wenn der Python-Interpreter auf eine inkonsistente oder falsche Einrückung stößt. Python verwendet Einrückungen anstelle von geschweiften Klammern oder anderen Trennzeichen, um Codeblöcke zu definieren. Dies bedeutet, dass die Einrückung für die korrekte Ausführung des Codes unerlässlich ist.

### Verwendung
Ein `IndentationError` wird typischerweise angezeigt, wenn:
- Eine Zeile nicht die erwartete Einrückung hat.
- Mischen von Tabs und Leerzeichen für Einrückungen.
- Eine Blockstruktur (wie Schleifen oder Funktionsdefinitionen) nicht korrekt eingerückt ist.

### Details
- Python 3 empfiehlt die Verwendung von 4 Leerzeichen für jede Einrückungsebene.
- Es ist wichtig, konsistent zu bleiben und entweder nur Tabs oder nur Leerzeichen zu verwenden.
- Der Fehler kann in verschiedenen Kontexten auftreten, z.B. in Schleifen, Bedingungen und Funktionsdefinitionen.

## Beispiele
### Beispiel 1: Korrekte Einrückung
```python
def meine_funktion():
    print("Hallo, Welt!")
```

### Beispiel 2: IndentationError
```python
def meine_funktion():
print("Hallo, Welt!")  # IndentationError: expected an indented block
```

### Beispiel 3: Mischen von Tabs und Leerzeichen
```python
def meine_funktion():
    print("Hallo, Welt!")  # Diese Zeile ist mit 4 Leerzeichen eingerückt
	print("Fehler!")        # Diese Zeile ist mit einem Tab eingerückt
```

## Erklärung
Ein `IndentationError` kann leicht auftreten, insbesondere wenn der Code kopiert und eingefügt wird oder wenn verschiedene Editoren verwendet werden, die unterschiedliche Standards für Einrückungen haben. Hier sind einige häufige Fallstricke:
- **Mischung von Tabs und Leerzeichen**: Dies kann zu inkonsistenten Einrückungen führen und ist eine häufige Quelle für diesen Fehler.
- **Vergessen, einen Block einzurücken**: Wenn Sie eine neue Blockstruktur (wie eine Schleife oder eine Funktion) beginnen, müssen alle Anweisungen innerhalb dieses Blocks korrekt eingerückt sein.
- **Falsche Anzahl von Leerzeichen**: Auch wenn Sie nur Leerzeichen verwenden, kann eine falsche Anzahl zu einem `IndentationError` führen.

## Zusammenfassung in einem Satz
Ein `IndentationError` in Python tritt auf, wenn die Einrückung im Code nicht korrekt ist, was die Ausführung und Lesbarkeit des Codes beeinträchtigt.