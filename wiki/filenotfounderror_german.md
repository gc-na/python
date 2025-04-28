<!--
Meta Description: # Python FileNotFoundError: Umgang mit Dateifehlern in Python ## Synopsis Der `FileNotFoundError` ist eine Ausnahme in Python, die auftritt, wenn ein ...
Meta Keywords: die, der, datei, filenotfounderror, python
-->

# Python FileNotFoundError: Umgang mit Dateifehlern in Python

## Synopsis
Der `FileNotFoundError` ist eine Ausnahme in Python, die auftritt, wenn ein Programm versucht, auf eine Datei zuzugreifen, die nicht vorhanden ist. Diese Fehlerbehandlung ist entscheidend, um robuste und benutzerfreundliche Anwendungen zu erstellen.

## Dokumentation
In Python ist der `FileNotFoundError` eine spezifische Ausnahme, die zur Familie der `OSError`-Ausnahmen gehört. Diese wird ausgelöst, wenn ein Versuch unternommen wird, eine Datei zu öffnen oder auf sie zuzugreifen, jedoch die angegebene Datei nicht im angegebenen Verzeichnis gefunden wird.

### Zweck
Der Zweck des `FileNotFoundError` besteht darin, Entwicklern zu ermöglichen, auf das Fehlen einer Datei angemessen zu reagieren. Dies ist besonders wichtig in Anwendungen, die auf externe Ressourcen angewiesen sind, wie z.B. Konfigurationsdateien, Datensätze oder Mediendateien.

### Verwendung
Der `FileNotFoundError` kann in jedem Kontext auftreten, in dem File-Operationen durchgeführt werden, einschließlich der Verwendung der Funktionen `open()`, `os.remove()`, und `os.rename()`. Um diesen Fehler zu handhaben, können Entwickler den `try`-`except`-Block verwenden.

### Details
- **Python-Versionen**: `FileNotFoundError` ist seit Python 3.3 verfügbar.
- **Fehlercode**: Der Fehler hat die Fehlernummer `2`, die auf ein "No such file or directory" hindeutet.
- **Vererbung**: Er vererbt von `OSError`.

## Beispiele

### Beispiel 1: Öffnen einer nicht vorhandenen Datei
```python
try:
    with open('nicht_existierende_datei.txt', 'r') as datei:
        inhalt = datei.read()
except FileNotFoundError:
    print("Die angegebene Datei wurde nicht gefunden.")
```

### Beispiel 2: Entfernen einer Datei
```python
import os

try:
    os.remove('nicht_existierende_datei.txt')
except FileNotFoundError:
    print("Die Datei, die Sie löschen möchten, existiert nicht.")
```

## Erklärung
Ein häufiger Fehler, der beim Umgang mit `FileNotFoundError` auftreten kann, ist das Missverständnis über den aktuellen Arbeitsordner. Der Pfad zur Datei muss relativ zum Arbeitsverzeichnis des Skripts angegeben werden. Ein weiterer häufiger Fall ist die falsche Schreibweise des Dateinamens oder das Fehlen der entsprechenden Dateierweiterung.

Zusätzlich kann es in Umgebungen mit verschiedenen Betriebssystemen Unterschiede im Dateipfad geben (z.B. Verwendung von `/` in Unix-ähnlichen Systemen und `\` in Windows). Daher ist es ratsam, die Bibliothek `os.path` oder `pathlib` zu verwenden, um plattformunabhängige Pfade zu erstellen.

## Ein-Satz-Zusammenfassung
Der `FileNotFoundError` in Python tritt auf, wenn eine Datei, auf die zugegriffen werden soll, nicht im vorgesehenen Verzeichnis gefunden werden kann.