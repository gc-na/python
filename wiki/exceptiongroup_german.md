<!--
Meta Description: # ExceptionGroup in Python: Eine umfassende Anleitung ## Synopsis `ExceptionGroup` ist eine neue Funktionalität in Python, die es ermöglicht, mehrere ...
Meta Keywords: exceptiongroup, die, ausnahmen, python, fehler
-->

# ExceptionGroup in Python: Eine umfassende Anleitung

## Synopsis
`ExceptionGroup` ist eine neue Funktionalität in Python, die es ermöglicht, mehrere Ausnahmen als eine Gruppe zu behandeln. Dies ist besonders nützlich in asynchronen Programmen, wo mehrere Fehler gleichzeitig auftreten können.

## Dokumentation
`ExceptionGroup` wurde mit Python 3.11 eingeführt und dient dazu, mehrere Ausnahmen zu aggregieren und sie als eine einzige Ausnahme zu verwalten. Diese Funktion ist besonders wertvoll in Situationen, in denen mehrere asynchrone Aufgaben gleichzeitig ausgeführt werden, und jede dieser Aufgaben eine eigene Ausnahme auslösen kann.

### Zweck
Der Hauptzweck von `ExceptionGroup` besteht darin, die Handhabung von Fehlern in asynchronen Programmen zu vereinfachen, indem alle relevanten Ausnahmen gebündelt und zusammen behandelt werden.

### Verwendung
Um `ExceptionGroup` zu verwenden, müssen Sie die entsprechenden Ausnahmen in einer Liste oder einem anderen iterierbaren Objekt sammeln und dann ein `ExceptionGroup`-Objekt erstellen. Die Verwendung ist denkbar einfach:

```python
from exceptiongroup import ExceptionGroup

# Beispiel für eine Gruppe von Ausnahmen
exceptions = [ValueError("Fehler 1"), TypeError("Fehler 2")]
group = ExceptionGroup("Gruppenausnahmen", exceptions)
```

### Details
- `ExceptionGroup` erbt von der Basis-Exception-Klasse und kann wie jede andere Ausnahme behandelt werden.
- Sie können benannte Ausnahmen zur Gruppe hinzufügen, um die Fehlersuche zu erleichtern.
- Es ist möglich, durch die Gruppe von Ausnahmen zu iterieren, um spezifische Fehler zu identifizieren und zu behandeln.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `ExceptionGroup`:

### Beispiel 1: Einfache Verwendung
```python
from exceptiongroup import ExceptionGroup

try:
    raise ExceptionGroup("Fehlergruppe", [ValueError("Erster Fehler"), TypeError("Zweiter Fehler")])
except ExceptionGroup as eg:
    for exception in eg.exceptions:
        print(f"Aufgetretene Ausnahme: {exception}")
```

### Beispiel 2: Asynchrone Verwendung
```python
import asyncio
from exceptiongroup import ExceptionGroup

async def task_1():
    raise ValueError("Fehler in Aufgabe 1")

async def task_2():
    raise TypeError("Fehler in Aufgabe 2")

async def main():
    try:
        await asyncio.gather(task_1(), task_2())
    except ExceptionGroup as eg:
        for exception in eg.exceptions:
            print(f"Aufgetretene Ausnahme: {exception}")

asyncio.run(main())
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `ExceptionGroup` ist, dass Entwickler versuchen, sie wie eine normale Ausnahme zu behandeln, ohne die spezifischen Ausnahmen innerhalb der Gruppe zu überprüfen. Es ist wichtig, die Einzelheiten der gruppierten Ausnahmen zu beachten, um die Fehlerursache gezielt zu adressieren. Ein weiterer Punkt ist, dass nicht alle Versionen von Python `ExceptionGroup` unterstützen, daher sollte immer die verwendete Python-Version überprüft werden.

## One Line Summary
`ExceptionGroup` in Python ermöglicht die Gruppierung mehrerer Ausnahmen zur vereinfachten Fehlerbehandlung in asynchronen Anwendungen.