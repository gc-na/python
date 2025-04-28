<!--
Meta Description: # IOError in Python: Fehlerbehandlung bei Ein-/Ausgabefunktionen ## Synopsis `IOError` ist eine Ausnahme in Python, die auftritt, wenn eine Ein-/Ausga...
Meta Keywords: ioerror, ist, die, python, fehler
-->

# IOError in Python: Fehlerbehandlung bei Ein-/Ausgabefunktionen

## Synopsis
`IOError` ist eine Ausnahme in Python, die auftritt, wenn eine Ein-/Ausgabeoperation fehlschlägt, beispielsweise beim Lesen oder Schreiben von Dateien.

## Dokumentation
`IOError` ist eine eingebaute Ausnahme, die in Python verwendet wird, um Fehler zu kennzeichnen, die während der Ein-/Ausgabeverarbeitung auftreten. Diese Fehler können durch verschiedene Faktoren verursacht werden, darunter:

- Das Fehlen einer Datei
- Unzureichende Berechtigungen zum Lesen oder Schreiben von Dateien
- Probleme mit der Hardware, wie ein fehlerhaftes Speichermedium

In Python 3 wurde `IOError` in `OSError` integriert, aber es ist wichtig, die Verwendung von `IOError` in Python 2 zu verstehen, da viele ältere Codebasen noch existieren.

### Verwendung
Um `IOError` zu handhaben, verwenden Sie einen `try`-`except`-Block. Dies ermöglicht es Ihnen, auf die Ausnahme zu reagieren und geeignete Maßnahmen zu ergreifen, anstatt das Programm unerwartet zu beenden.

```python
try:
    with open('datei.txt', 'r') as file:
        inhalt = file.read()
except IOError as e:
    print(f"Ein Fehler ist aufgetreten: {e}")
```

## Beispiele
Hier sind einige grundlegende Beispiele für den Umgang mit `IOError`:

### Beispiel 1: Datei nicht gefunden
```python
try:
    with open('nicht_vorhanden.txt', 'r') as file:
        inhalt = file.read()
except IOError as e:
    print(f"Fehler: {e}")  # Ausgabe: Fehler: [Errno 2] No such file or directory: 'nicht_vorhanden.txt'
```

### Beispiel 2: Schreibberechtigungen
```python
try:
    with open('/geschuetzter_ordner/datei.txt', 'w') as file:
        file.write("Hallo, Welt!")
except IOError as e:
    print(f"Fehler: {e}")  # Ausgabe: Fehler: [Errno 13] Permission denied: '/geschuetzter_ordner/datei.txt'
```

## Erklärung
Ein häufiger Fallstrick bei der Arbeit mit `IOError` ist, dass die Ausnahme möglicherweise nicht sofort offensichtlich ist. Häufige Ursachen sind:

- Falsche Dateipfade: Überprüfen Sie, ob der angegebene Pfad korrekt ist.
- Berechtigungen: Stellen Sie sicher, dass Ihr Programm die erforderlichen Berechtigungen hat, um auf die Datei zuzugreifen.
- Verwaiste Dateihandles: Achten Sie darauf, dass Dateien ordnungsgemäß geschlossen werden, um Dateisperren oder unvorhergesehene Fehler zu vermeiden.

Es ist auch wichtig, zu beachten, dass in Python 3 die Verwendung von `IOError` als spezifische Ausnahme nicht mehr erforderlich ist, da sie in `OSError` integriert wurde. Dennoch ist das Verständnis dieser Ausnahme für die Wartung älterer Anwendungen von Bedeutung.

## Ein-Satz-Zusammenfassung
`IOError` ist eine Ausnahme in Python, die auf Fehler bei Ein-/Ausgabeoperationen hinweist, wie das Nichtfinden von Dateien oder mangelnde Berechtigungen.