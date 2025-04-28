<!--
Meta Description: # __package__ in Python: Bedeutung und Anwendung ## Synopsis Das `__package__` Attribut in Python gibt den Namen des Pakets an, in dem sich ein Modul ...
Meta Keywords: __package__, ist, wird, python, modul
-->

# __package__ in Python: Bedeutung und Anwendung

## Synopsis
Das `__package__` Attribut in Python gibt den Namen des Pakets an, in dem sich ein Modul befindet. Es ist besonders nützlich für die Handhabung von relativen Imports und spielt eine zentrale Rolle in der Modulorganisation.

## Dokumentation
### Zweck
Das `__package__` Attribut dient dazu, den Paketnamen eines Moduls zu identifizieren. Dies ist wichtig, um den Kontext zu verstehen, in dem das Modul geladen wird, und um sicherzustellen, dass relative Importe korrekt aufgelöst werden.

### Verwendung
- **Zugriff**: Das `__package__` Attribut kann direkt innerhalb eines Moduls aufgerufen werden. Es wird automatisch von Python gesetzt, wenn das Modul in einem Paket kontextualisiert wird.
- **Importverhalten**: Bei der Verwendung von relativen Importen hilft `__package__`, den korrekten Pfad zu bestimmen.

### Details
- Wenn ein Modul als Skript ausgeführt wird (z.B. `python mein_modul.py`), ist `__package__` leer oder nicht gesetzt.
- Bei der Ausführung innerhalb eines Pakets wird `__package__` auf den Namen des Pakets gesetzt, was die Durchführung von relativen Importen ermöglicht.

## Beispiele
### Beispiel 1: Zugriff auf __package__
```python
# Angenommen, wir haben ein Paket namens 'mein_paket' mit einem Modul 'mein_modul.py'

# mein_modul.py
print(__package__)
```
Wenn dieses Modul innerhalb des Pakets ausgeführt wird, gibt es den Namen `mein_paket` aus.

### Beispiel 2: Verwendung in relativen Importen
```python
# Angenommen, wir haben die folgende Struktur:
# mein_paket/
# ├── __init__.py
# ├── modul_a.py
# └── modul_b.py

# modul_a.py
from .modul_b import meine_funktion

# modul_b.py
def meine_funktion():
    print("Hallo von modul_b")

# Wenn wir modul_a.py ausführen, wird __package__ auf 'mein_paket' gesetzt,
# wodurch der relative Import funktioniert.
```

## Erklärung
### Häufige Fallstricke
- **Leeres __package__**: Wenn ein Modul direkt als Skript ausgeführt wird, bleibt `__package__` leer, was zu Importfehlern führen kann, wenn relative Imports verwendet werden.
- **Missverständnis bei relativen Imports**: Viele Entwickler setzen `__package__` manuell, was nicht empfohlen wird. Python setzt dieses Attribut automatisch und sollte nicht überschrieben werden.

### Zusätzliche Hinweise
- `__package__` ist ein Standardattribut, das in jedem Modul vorhanden ist, auch wenn es nicht explizit definiert ist.
- Es ist nützlich für die Entwicklung von Paketen und beim Erstellen von Bibliotheken, bei denen die Importstruktur wichtig ist.

## Zusammenfassung in einem Satz
Das `__package__` Attribut in Python identifiziert den Paketnamen eines Moduls und ist entscheidend für die korrekte Handhabung von relativen Imports.