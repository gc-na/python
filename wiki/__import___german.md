<!--
Meta Description: # __import__ in Python: Dynamisches Importieren von Modulen ## Synopsis Der `__import__`-Befehl in Python ermöglicht das dynamische Importieren von Mo...
Meta Keywords: __import__, die, python, der, das
-->

# __import__ in Python: Dynamisches Importieren von Modulen

## Synopsis
Der `__import__`-Befehl in Python ermöglicht das dynamische Importieren von Modulen zur Laufzeit. Er ist eine grundlegende Funktion für fortgeschrittene Programmiertechniken und wird häufig in Metaprogrammierung und bei der Erstellung von Plugins verwendet.

## Dokumentation
Der `__import__`-Befehl ist eine eingebaute Funktion in Python, die es ermöglicht, Module programmgesteuert zu importieren. Die Syntax lautet:

```python
__import__(name, globals=None, locals=None, fromlist=(), level=0)
```

### Parameter
- **name** (str): Der Name des Moduls, das importiert werden soll. Dies kann ein einfacher Modullname oder ein verschachtelter Name (z.B. `package.module`) sein.
- **globals** (dict, optional): Ein Dictionary, das die globalen Variablen zur Verfügung stellt. Standardmäßig ist dies das aktuelle Modul.
- **locals** (dict, optional): Ein Dictionary, das die lokalen Variablen zur Verfügung stellt. Standardmäßig wird dies auf `None` gesetzt.
- **fromlist** (list, optional): Eine Liste von Attributen, die aus dem Modul importiert werden sollen. Wenn dieser Parameter leer ist, wird nur das Modul selbst zurückgegeben.
- **level** (int, optional): Definiert, ob ein relativer Import (Wert 1) oder ein absoluter Import (Wert 0) durchgeführt wird.

### Rückgabewert
Die Funktion gibt das importierte Modul zurück.

## Beispiele
### Einfaches Beispiel
```python
# Dynamisches Importieren eines Moduls
modul_name = "math"
math_modul = __import__(modul_name)

print(math_modul.sqrt(16))  # Ausgabe: 4.0
```

### Importieren mit fromlist
```python
# Importieren einer spezifischen Funktion
modul_name = "os"
os_modul = __import__(modul_name, fromlist=["path"])

print(os_modul.path.abspath('.'))  # Ausgabe: Absoluter Pfad des aktuellen Verzeichnisses
```

### Relativer Import
```python
# Angenommen, wir haben eine Paketstruktur
# __init__.py
# module1.py
# module2.py

# In module1.py
modul_name = ".module2"
module2 = __import__(modul_name, fromlist=[''])

# Verwendung einer Funktion aus module2
module2.some_function()
```

## Erklärung
Obwohl `__import__` eine mächtige Funktion ist, kann ihre Verwendung einige Fallstricke mit sich bringen:

- **Komplexität**: `__import__` kann den Code weniger lesbar und schwerer wartbar machen. Für die meisten Anwendungsfälle sind die regulären Importanweisungen (`import` und `from ... import ...`) ausreichend.
  
- **Performance**: Dynamische Importe können die Leistung beeinträchtigen, da sie zur Laufzeit erfolgen und möglicherweise nicht die Vorteile der Optimierungen des Python-Importmechanismus nutzen.

- **Fehlende Fehlerbehandlung**: Bei der Verwendung von `__import__` muss der Entwickler sicherstellen, dass das Modul existiert und ordnungsgemäß importiert werden kann, da Fehler in der Regel nicht so klar angezeigt werden wie bei regulären Importanweisungen.

## Ein-Satz-Zusammenfassung
Der `__import__`-Befehl in Python ermöglicht das dynamische Importieren von Modulen zur Laufzeit und bietet eine flexible, aber komplexe Lösung für fortgeschrittene Programmieraufgaben.