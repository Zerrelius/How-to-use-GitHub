# GitHub Anleitung
Dies ist eine Anleitung um sich ein lokales Git Repository zu erstellen und es anschließend mit einem GitHub Repository zu verbinden

_____

## Installation

Zuerst einmal, müssen wir die Versionierungs Software Git installieren auf unserem System. Dafür geht ihr in die Konsole eures Betriebssystems.
Nun ist die Frage unter welchem Betriebssystem wir uns befinden.


### Windows
Für Windows benutzen wir hier das Installations Tool Chocolatey, sollte dies noch nicht installiert sein, muss dies vorher getan werden. Eine gezielte Anleitung findet ihr auf der Website von Chocolatey selbst. 
https://chocolatey.org/install

So bald dieses installiert ist, können wir mithilfe des einfachen Befehls
```choco install git```
installieren. Es kann sein, dass dies noch einmal bestätigt werden muss, mit einem y.

### Linux
Bei Linux haben wir es hier deutlich einfacher, wir können mit dem Package Manager unserer aktuellen Distrubition arbeiten. In unserem Beispiel verwenden wir den der LTS Debian Server, welche für Debian als auch Ubuntu genutzt wird.
**ACHTUNG!** Bitte vergewissert euch selbst, welcher Paket Manager für euch der richtige ist, dieser ändert sich je nach Distrubition. Durch Googlen, solltet ihr spätestens dies aber mit leichtigkeit heraus bekommen. Mit dem Befehl `apt-get` als Beispiel könnt ihr euch vergewissern auf einem Debian oder Ubuntu Server oder System.

Der folgende Befehl wird folglich unter Debian und Ubuntu Systemen verwendet um Git zu installieren.
```sudo apt install git-all```

___

## Initialisierung

Jetzt müssen wir ein Verzeichnis (Ordner) erstellen und ein lokales Repository erstellen bzw. initialisieren.
    


