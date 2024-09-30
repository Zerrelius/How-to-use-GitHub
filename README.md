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
```bash
choco install git
```
installieren. Es kann sein, dass dies noch einmal bestätigt werden muss, mit einem y.

### Linux
Bei Linux haben wir es hier deutlich einfacher, wir können mit dem Package Manager unserer aktuellen Distrubition arbeiten. In unserem Beispiel verwenden wir den der LTS Debian Server, welche für Debian als auch Ubuntu genutzt wird.
**ACHTUNG!** Bitte vergewissert euch selbst, welcher Paket Manager für euch der richtige ist, dieser ändert sich je nach Distrubition. Durch Googlen, solltet ihr spätestens dies aber mit leichtigkeit heraus bekommen. Mit dem Befehl `apt-get` als Beispiel könnt ihr euch vergewissern auf einem Debian oder Ubuntu Server oder System.

Der folgende Befehl wird folglich unter Debian und Ubuntu Systemen verwendet um Git zu installieren.
```bash
sudo apt install git-all
```
___

## Erste Einstellungen

Nun müssen wir zu aller erst, einmalig, erste Einstellungen machen. Als Beispiel müssen wir einen Benutzernamen und eine Email für unser Git einstellen. Dies dient unserem Git als auch uns nachher zur klaren differenzierung wer aktuell an was arbeitet, gepusht, gemerged oder bearbeitet hat.
```bash
git config --global user.name "DeinUserName"
git conifg --global user.email "DeineEmailAdresse"
```
Mit diesen beiden Befehlen setzen wir global, in unserem System, für unser Git, die Einstellungen unseres Usernamen und unserer Email Adresse.

___

## Initialisierung

Jetzt müssen wir ein Verzeichnis (Ordner) erstellen und ein lokales Repository erstellen bzw. initialisieren.
```bash
mkdir Projekte && cd Projekte
mkdir "DeinProjektName" && cd "DeinProjektName"
git init
```
Wir haben mit den Befehlen das Verzeichnis Projekte erstellt. Anschließend ein Verzeichnis des jeweiligen Projekts. Hierbei muss natürlich ```"DeinProjektName"``` ersetzt werden mit dem Namen eures Projekts. Dabei gehen wir immer zeitgleich in den erstellten Ordner.
Zum Schluss initialisieren wir das Projekt als Git Repository mit git init.
 
___

## Datein Hinzufügen und Commiten

Nun wollen wir eine README Datei erstellen. Diese Datei dient uns zur Beschreibung des Programms und wie man es anwendet. Auf GitHub ist dies später besonders dienlich damit man diese Anleitung auf der Frontpage unsere Repositorys sehen kann.

Dafür erstellen wir mit dem VIM Befehl eine neue Datei.
```bash
vim README.md
```
Das .md am Ende ist wichtig um es als Markdown Datei zu Kennzeichnen, dies ist eine Konvention und Datei Format um entsprechend eine Beschreibung des Programms durchzuführen.
In der Datei setzen wir in die erste Zeile nun ```# Projekt-Name``` natürlich soll hierbei "Projekt-Name" mit dem Namen eures Projekts ausgetauscht werden. Mit der Taste i kommen wir in den Insert Modus.
Um aus Vim wieder heraus zu kommen, gehen wir mit ESC aus dem Insert Modus raus und speichern die Datei mit :wq und einem Enter.

Nun müssen wir mit dem Git Add Befehl die Datei unserem Repository bekannt machen.
```bash
git add README.md
```
Nun haben wir Datei hinzugefügt. Allerdings ist sie nur bekannt. Mit ```git status``` können wir außerdem den aktuellen Status der Dateien überprüfen und checken ob diese bereits geadded sind in unserer Version.

Anschließend um sie final unserer Version hinzufügen müssen wir sie nun Commiten.
```bash
git commit -m "First Commit and README added"
```
Hierbei haben wir unseren ersten Commit gemacht und den Parameter -m benutzt. Dies bedeutet wir fügen einen Kommentar hinzu. Um den Konventionen zu entsprechen, verwenden wir für alle Kommentare, die im übrigen auch auf GitHub einsichtbar sind, die englische Sprache und möglichst kurze, klare Beschreibungen was hinzugefügt wurde.

___

## Einrichtung des SSH Keys und Verbindung mit GitHub

Nun müssen wir erst einmal ein Repository auf unserem GitHub Account erstellen. Am besten benutzen wir dafür den selben Namen wie in unserem lokalen Git.
So bald das Repo erstellt ist, behaltet ihr die Seite offen, und drückt auf SSH im Quick Setup Bereich. Dort findet ihr ebenso eine genaue Erklärung wie man es hinzufügt.

Doch erst einmal erstellen wir einen SSH Key und verbinden damit unser lokales System mit unserem GitHub Account.
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Ist der Befehl den wir nun verwenden. Damit erstellen wir einen SSH Key den wir benutzen müssen. Natürlich müssen wir auch hier "your_email@example.com" ändern zu unserer Email Adresse.

Nun müssen wir unseren erstellten Public SSH Key heraus holen. Finden tun wir diesen in unserem versteckten SSH Ordner im Home Verzeichnis.
```bash
cat ~/.ssh/id_ed25519.pub
```
Diese Zeile die wir nun vor uns haben, kopieren wir uns heraus.

Auf GitHub gehen wir dann in unsere Account Settings. Dort fügen wir im Unterpunkt Access unter SSH and GPG Keys unseren SSH Key hinzu und fügen einen Namen hinzu. Damit verbinden wir unser System mit unserem GitHub Account.

___


