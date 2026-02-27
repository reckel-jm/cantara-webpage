---
title: "Cantara installieren"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 2
---

Diese Seite beschreibt, wie Sie Cantara auf Ihrem lokalen Betriebssystem installieren können.

## Windows

Die Installation unter Windows ist sehr einfach und in nur einer Minute erledigt. Sie können entweder den Windows-Paketmanager [Winget](https://learn.microsoft.com/de-de/windows/package-manager/winget/) verwenden oder den Installer manuell herunterladen und ausführen.

### Winget verwenden (Windows 10 und Windows 11)

Wenn Sie eine der modernen Windows-Versionen (Windows 10 1709 oder neuer) verwenden, können Sie [Winget](https://learn.microsoft.com/de-de/windows/package-manager/winget/) nutzen, um Cantara sicher zu installieren und aktuell zu halten. Öffnen Sie einfach eine Windows-PowerShell und führen Sie folgenden Befehl aus:

```Powershell
winget install cantara
```

Winget lädt den Installer herunter, fragt einmalig nach einer Bestätigung und führt den Installer anschließend im Hintergrund aus. Wenn eine neue Version veröffentlicht wird, können Sie über `winget upgrade --all` oder `winget upgrade cantara` aktualisieren.

Wenn Sie Cantara von Ihrem System entfernen möchten, können Sie `winget uninstall cantara` ausführen.

### Den Installer ausführen

Falls Sie Winget nicht verwenden möchten, können Sie den Installer auch manuell herunterladen und ausführen, der Sie durch den Installationsprozess führt.

[Laden Sie den Installer einfach herunter und führen Sie ihn aus](https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-{{% param "cantaraVersion" %}}_setup_win64.exe), beantworten Sie die Fragen und installieren Sie Cantara. Nach der Installation finden Sie das Programm in Ihrem Startmenü. Außerdem haben Sie – wenn Sie diese Option während des Setups gewählt haben – auch eine Verknüpfung auf Ihrem Desktop.

{{% notice info %}}
Beim Starten des Installers könnte Windows Sie warnen, dass die Quelle unbekannt und die ausführbare Datei nicht signiert ist. In diesem Fall können Sie „Trotzdem ausführen" wählen, um fortzufahren.
Dies liegt daran, dass ich kein Zertifikat besitze, das ich zur Zertifizierung der ausführbaren Datei verwenden könnte.
Da die Software jedoch bei Winget veröffentlicht wurde, können Sie sie dort sicher und ohne diese Meldung installieren.
{{% /notice %}}

## Linux

Cantara wurde von einem Linux-Fan und -Enthusiasten entwickelt. Es ist mir daher eine Freude sicherzustellen, dass Cantara auf jeder Linux-Distribution gut funktioniert.

{{% notice info %}}
Cantara kann die Qt6-, Qt5- und GTK2-Bibliotheken für die grafische Benutzeroberfläche verwenden. Je nach Distributionskanal ist Cantara mit Qt6- oder Qt5-Bindungen vorkompiliert. Wenn Sie GTK2 bevorzugen, [kompilieren Sie Cantara bitte selbst](#generic-compilation).
{{% /notice %}}

### Arch Linux und Arch-basierte Distributionen (Manjaro, Garuda usw.)

#### Das Arch User Repository (AUR)

[![cantara](https://img.shields.io/aur/version/cantara?color=1793d1&label=cantara&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara/)[![cantara-bin](https://img.shields.io/aur/version/cantara-bin?color=1793d1&label=cantara-bin&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara-bin/)

Das [Arch User Repository (AUR)](https://wiki.archlinux.org/title/Arch_User_Repository) enthält Paketbauinformationen, mit denen Softwarepakete automatisch gebaut und auf dem lokalen Dateisystem installiert werden können. Dies ist die bevorzugte Methode zur Installation von Software außerhalb der offiziellen Repositories. Es gibt zwei Cantara-Pakete im AUR: Verwenden Sie [cantara-bin](https://aur.archlinux.org/packages/cantara-bin) für eine vorkompilierte Version von Cantara und [cantara](https://aur.archlinux.org/packages/cantara), wenn das System das Paket selbst kompilieren soll. Beachten Sie, dass für die Installation der **zweiten Option** die Compiler und Bibliotheken von Pascal und Lazarus heruntergeladen und installiert werden müssen, was möglicherweise mehrere hundert Megabyte Speicherplatz erfordert. Diese Tools können nach Abschluss des Kompilierungsprozesses gelöscht werden.

Es gibt viele Möglichkeiten, ein Paket aus dem AUR zu installieren. Die meisten Benutzer verwenden einen Helfer wie `yay`. Installieren Sie **eines der Pakete**:

```bash
yay cantara-bin # schnelle und kompakte Installation des vorkompilierten Binaries
yay cantara # lädt den Quellcode herunter und kompiliert selbst
```

{{% notice note %}}
Ein großer Vorteil der Verwendung eines Helfers wie yay ist, dass er die Pakete auch aktuell hält! Immer wenn eine neue Version von Cantara veröffentlicht wird, sollten Sie über `sudo yay -Syu` aktualisieren können.
{{% /notice %}}

Nach der Installation kann Cantara über pacman deinstalliert werden: `sudo pacman -R cantara`.

### Ubuntu/Debian-basierte Linux-Distributionen

Bitte verwenden Sie [Snap](#snap) oder [Flatpak](#flatpakflathub) wie in den entsprechenden Abschnitten beschrieben.

### Snap

Cantara ist im Snap Store verfügbar! Das Snap-Paket umfasst jetzt nur noch 4,5 MB und ist daher eine gute distributionsunabhängige Möglichkeit, Cantara zu installieren. Sie können den Anweisungen auf der [Cantara-Store-Seite](https://snapcraft.io/cantara) folgen, um herauszufinden, wie Sie es auf Ihrem lokalen System installieren können, oder – wenn snapd bereits läuft – es über die Befehlszeile installieren.

[![Im Snap Store erhältlich](https://snapcraft.io/static/images/badges/de/snap-store-black.svg)](https://snapcraft.io/cantara)

```bash
sudo snap install cantara
```

{{% notice info %}}
Die Art und Weise, wie eine Snap-Anwendung ausgeführt wird, unterscheidet sich von einem normalen Paket. Daher kann es zu einem etwas anderen Verhalten kommen, z. B. einem anderen Aussehen des Programms. Melden Sie in jedem Fall jedes unerwartete Verhalten, damit ich versuchen kann, es zu beheben.
{{% /notice %}}

Snap erstellt einen Starter im Startmenü. Wenn Sie Cantara über die Befehlszeile ausführen möchten, lautet der Befehl `snap run cantara`.

{{% notice tip %}}
Sie können auch verschiedene Versionen von Cantara gleichzeitig installieren und sogar Cantara als klassisches Paket und als Snap zusammen installieren. Weitere Informationen finden Sie in der [Snap-Dokumentation](https://snapcraft.io/docs/parallel-installs).
{{% /notice %}}

### Flatpak/Flathub

Cantara wurde auch als Flatpak verpackt und kann von [flathub.org](https://flathub.org/apps/details/app.cantara.Cantara) installiert und aktualisiert werden. Dies erfordert ein installiertes Flatpak auf Ihrem Betriebssystem. Einige Distributionen wie Fedora haben dies bereits von Haus aus, in anderen Distributionen wie Arch Linux müssen Sie es manuell installieren.

Die Installation eines Flatpaks von Flathub kann über ein grafisches Softwareverwaltungstool, z. B. Gnome Software oder KDE Discover, oder über die Befehlszeile erfolgen:

```bash
flatpak install app.cantara.Cantara
```

Je nach den bereits installierten Flatpaks kann Flatpak mehrere hundert Megabyte für die erforderlichen KDE/Qt-Laufzeitumgebungen herunterladen. Obwohl das eigentliche Cantara-Flatpak weniger als 4 MB groß ist, ist die Installation von Cantara über Flatpak daher sicher nicht die festplattenfreundlichste Methode.

### Ausführung als Binary (ohne Installation)

{{% notice warning %}}
Die Installation von Cantara ohne den nativen Paketmanager oder ein containerisiertes Format (Snap/Flatpak) wird ausdrücklich nicht empfohlen. Verwenden Sie dies nur zum lokalen Ausführen von Cantara ohne Installation.
{{% /notice %}}

Als weitere distributionsunabhängige Möglichkeit zur Nutzung von Cantara können Sie das Binary manuell herunterladen und ausführen. Bitte beachten Sie, dass Cantara die libqt5pas-Bibliothek benötigt, die normalerweise durch die Abhängigkeitsverwaltung des Paketmanagers Ihrer Distribution aufgelöst wird. Wenn Sie den Paketmanager jedoch nicht zur Installation verwenden, müssen Sie libqt5pas manuell installieren. Laden Sie danach die Zip-Datei aus dem Github-Repository herunter, entpacken Sie sie, machen Sie das Binary ausführbar und führen Sie `cantara` aus:

```sh
mkdir cantara && cd cantara
wget https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
unzip cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
chmod +x cantara
./cantara
```

### Selbst kompilieren {#generic-compilation}

Installieren Sie `lazarus` und `lazbuild` aus Ihrem lokalen Repository. Wenn Sie Qt5 bevorzugen, könnten Sie auch `lazarus-qt` anstelle von lazarus installieren, sofern die Distribution ein entsprechendes Paket bereitstellt. Danach ist die Kompilierung recht einfach: Laden Sie den Quellcode herunter, entpacken Sie ihn und führen Sie lazbuild mit den entsprechenden Optionen aus.

```sh
wget https://github.com/reckel-jm/cantara/archive/refs/tags/v{{% param "cantaraVersion" %}}.tar.gz
tar -zxvf v{{% param "cantaraVersion" %}}.tar.gz
cd v{{% param "cantaraVersion" %}}
make
```

Wenn Sie GTK2 bevorzugen, ändern Sie die Option in der Makefile auf `--ws=gtk2`. Nach einer fehlerfreien Kompilierung finden Sie das ausführbare Binary `cantara` im selben Ordner.

## Mac OS

Cantara funktioniert unter Mac OS X. Es wurde jedoch noch nicht offiziell zertifiziert, was bedeutet, dass Sie es noch nicht auf normalem Wege installieren können.
Bitte befolgen Sie diese Schritte, um Cantara zu verwenden:

1. Laden Sie das [Cantara Mac OS X Binary](https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-macos-x64.zip) von Github herunter.
2. Öffnen Sie das Zip-Archiv im Finder, sodass der Inhalt in einen Ordner entpackt wird.
3. Öffnen Sie ein Terminal und navigieren Sie zu dem Ordner, zum Beispiel mit `cd Downloads/cantara-{{% param "cantaraVersion" %}}-macos`, wenn Sie den Standard-Download-Ordner verwenden.
4. Wenn Sie sich im entpackten Ordner befinden, machen Sie die Binärdatei mit `chmod +x src/cantara.app/Contents/cantara` ausführbar.
5. Führen Sie das Binary mit `./src/cantara.app/Contents/cantara` aus. Cantara sollte jetzt starten. Sie können es im Dock fixieren, damit Sie es einfach wieder öffnen können.
