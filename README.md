## Dokumentation des Codes in Markdown

Der folgende Code ist ein Windows-Batch-Skript, das eine Liste aller Dateien im aktuellen Verzeichnis in eine Textdatei schreibt.

```Batch
@echo off
setlocal EnableDelayedExpansion

set "outputFile=%~dp0filelist.txt"

if exist "%outputFile%" (
  del "%outputFile%"
)

for %%F in (*) do (
  echo %%~nxF>>"%outputFile%"
)

echo "Dateinamen wurden in die Datei %outputFile% geschrieben."

## Funktionsweise

Der Code beginnt mit der Deaktivierung der Ausgabe auf der Befehlszeile mittels @echo off. Mit setlocal EnableDelayedExpansion wird die Erweiterung von Variablen verzögert, was notwendig ist, um eine Schleife zu verwenden.

In der nächsten Zeile wird eine Variable outputFile mit dem Pfad und dem Namen der Textdatei erstellt, in die die Dateiliste geschrieben werden soll. %~dp0 gibt den Pfad des aktuellen Verzeichnisses an.

Die nächste Bedingung if exist "%outputFile%" prüft, ob die Datei bereits vorhanden ist. Wenn dies der Fall ist, wird die Datei mit del "%outputFile%" gelöscht.

Anschließend wird eine Schleife mit der Syntax for %%F in (*) gestartet, die alle Dateien im aktuellen Verzeichnis durchläuft. %%~nxF gibt den Dateinamen mit Erweiterung zurück, während >> den Text an die Textdatei anhängt.

Zuletzt wird eine Ausgabe auf der Befehlszeile angezeigt, die bestätigt, dass die Dateinamen erfolgreich in die Textdatei geschrieben wurden.


## Verwendung

Dieser Code kann auf einem Windows-System ausgeführt werden, um eine Liste aller Dateien im aktuellen Verzeichnis in eine Textdatei zu schreiben. Die Ausführung erfolgt durch Doppelklick auf die Batch-Datei oder durch Aufruf aus der Befehlszeile. Die Textdatei wird im selben Verzeichnis wie das Skript erstellt.
