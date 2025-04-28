<!--
Meta Description: # Die Bedeutung von "__name__" in Python: Ein umfassender Leitfaden ## Synopsis In Python ist `__name__` eine spezielle Variable, die den Namen des Mo...
Meta Keywords: wird, das, __name__, ausgeführt, modul
-->

# Die Bedeutung von "__name__" in Python: Ein umfassender Leitfaden

## Synopsis
In Python ist `__name__` eine spezielle Variable, die den Namen des Moduls repräsentiert. Sie spielt eine entscheidende Rolle beim Testen von Modulen und beim Definieren des Modus der Ausführung.

## Dokumentation
Die Variable `__name__` wird automatisch von Python erstellt, wenn ein Skript ausgeführt wird. Sie hat unterschiedliche Werte, abhängig davon, wie das Skript ausgeführt wird:

- Wenn das Skript direkt ausgeführt wird, wird `__name__` auf `"__main__"` gesetzt.
- Wenn das Skript als Modul in ein anderes Skript importiert wird, erhält `__name__` den Namen des Moduls.

### Zweck
Der Hauptzweck von `__name__` besteht darin, Code zu trennen, der nur ausgeführt werden soll, wenn das Modul direkt ausgeführt wird, von Code, der ausgeführt werden soll, wenn das Modul importiert wird. Dies ermöglicht eine bessere Wiederverwendbarkeit und Modularität des Codes.

### Verwendung
Um die Funktionalität von `__name__` zu nutzen, können Sie den folgenden Code in Ihrem Modul verwenden:

```python
if __name__ == "__main__":
    # Code, der nur ausgeführt wird, wenn das Modul direkt gestartet wird
    print("Das Modul wird direkt ausgeführt.")
else:
    # Code, der ausgeführt wird, wenn das Modul importiert wird
    print("Das Modul wurde importiert.")
```

## Beispiele
Hier sind einige einfache Beispiele, die die Verwendung von `__name__` demonstrieren:

### Beispiel 1: Direktes Ausführen
```python
# datei: mein_modul.py
if __name__ == "__main__":
    print("Das Modul wird direkt ausgeführt.")
```
Wenn Sie `mein_modul.py` direkt über die Kommandozeile ausführen, wird die Ausgabe sein:
```
Das Modul wird direkt ausgeführt.
```

### Beispiel 2: Importieren eines Moduls
```python
# datei: mein_modul.py
if __name__ == "__main__":
    print("Das Modul wird direkt ausgeführt.")
else:
    print("Das Modul wurde importiert.")

# datei: anderes_modul.py
import mein_modul
```
Wenn Sie `anderes_modul.py` ausführen, wird die Ausgabe sein:
```
Das Modul wurde importiert.
```

## Erklärung
Ein häufiger Stolperstein beim Umgang mit `__name__` ist das Missverständnis über dessen Wert. Anfänger glauben manchmal, dass der Code innerhalb des `if __name__ == "__main__":` Blocks immer ausgeführt wird, egal wie das Skript aufgerufen wird. Es ist wichtig zu verstehen, dass dieser Code nur beim direkten Ausführen des Skripts aktiv wird.

Ein weiterer Punkt ist, dass `__name__` nicht nur für die Hauptausführungslogik nützlich ist, sondern auch für das Testen von Modulen. Sie können Testfunktionen oder Beispielaufrufe innerhalb des Blocks einfügen, um sicherzustellen, dass diese nur ausgeführt werden, wenn das Modul nicht importiert wird.

## Einzeilige Zusammenfassung
`__name__` ist eine spezielle Variable in Python, die den Namen des Moduls angibt und wichtig für die Unterscheidung zwischen direkter Ausführung und Import ist.