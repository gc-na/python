<!--
Meta Description: # NotADirectoryError in Python: Fehlerbehandlung für Verzeichnisse ## Synopsis Der `NotADirectoryError` ist eine Ausnahme in Python, die auftritt, wen...
Meta Keywords: ist, der, notadirectoryerror, fehler, ein
-->

# NotADirectoryError in Python: Fehlerbehandlung für Verzeichnisse

## Synopsis
Der `NotADirectoryError` ist eine Ausnahme in Python, die auftritt, wenn ein erwartetes Verzeichnis nicht gefunden wird oder wenn ein Pfad, der als Verzeichnis interpretiert werden sollte, tatsächlich eine Datei ist.

## Dokumentation
`NotADirectoryError` ist eine spezielle Ausnahme, die von Python ausgelöst wird, wenn ein Programm versucht, eine Verzeichnisoperation auf einer Datei durchzuführen. Diese Ausnahme ist Teil der Standardbibliothek und wird häufig in Dateisystemoperationen verwendet.

### Zweck
Der Hauptzweck des `NotADirectoryError` ist es, Programmierern zu helfen, Fehler im Umgang mit Dateisystemen zu erkennen und zu beheben. Wenn beispielsweise ein Skript versucht, auf Inhalte eines Verzeichnisses zuzugreifen, und der angegebene Pfad eine Datei ist, wird dieser Fehler ausgelöst.

### Verwendung
Der `NotADirectoryError` wird typischerweise in Situationen verwendet, in denen Funktionen wie `os.listdir()`, `os.path.join()` oder `os.chdir()` aufgerufen werden, um sicherzustellen, dass der angegebene Pfad ein Verzeichnis ist. Es ist wichtig, Verzeichnisse korrekt zu überprüfen, um unerwartete Fehler zu vermeiden.

## Beispiele

### Beispiel 1: Grundlegender Gebrauch
```python
import os

def list_directory_contents(path):
    try:
        return os.listdir(path)
    except NotADirectoryError:
        print(f"Fehler: {path} ist kein Verzeichnis.")

# Aufruf der Funktion mit einem Dateipfad
list_directory_contents("example_file.txt")
```

### Beispiel 2: Fehlerbehandlung
```python
import os

def change_directory(path):
    try:
        os.chdir(path)
        print(f"Verzeichnis gewechselt zu: {path}")
    except NotADirectoryError:
        print(f"Fehler: {path} ist kein gültiges Verzeichnis.")

# Aufruf der Funktion mit einem Dateipfad
change_directory("example_file.txt")
```

## Erklärung
Ein häufiger Stolperstein, der zur Auslösung des `NotADirectoryError` führen kann, ist die Verwirrung zwischen Dateien und Verzeichnissen. Wenn ein Programmierer versucht, ein Verzeichnis zu verwenden, das tatsächlich eine Datei ist, wird dieser Fehler ausgelöst. 

Zusätzlich kann der Fehler auch auftreten, wenn der angegebene Pfad nicht existiert oder falsch geschrieben ist. Es ist ratsam, vor dem Zugriff auf Verzeichnisse die Existenz und den Typ des Pfades zu überprüfen, um solche Fehler zu vermeiden.

## Zusammenfassung
Der `NotADirectoryError` ist eine wichtige Ausnahme in Python, die hilft, Fehler beim Arbeiten mit Dateisystemen zu identifizieren, indem sie sicherstellt, dass Pfade, die als Verzeichnisse verwendet werden, tatsächlich Verzeichnisse sind.