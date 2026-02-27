---
title: "Allgemeine Verwendung"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 3
---

## Erste Schritte

Öffnen Sie nach der Installation einfach Cantara über Ihr Startmenü oder den Befehl `cantara`. Sie sehen dann den **Willkommens-Assistenten**, der Sie durch die Konfiguration von Cantara führt.
![Der englische Cantara-Einstellungsdialog](/images/cantara-welcome-assistent-step-1.png)

Hier sollten Sie ein Song-Repository-Verzeichnis wählen, in dem alle Liedtextdateien gespeichert sind. Wenn Sie noch keines haben, können Sie einen neuen leeren Ordner erstellen und ihn als Song-Repository auswählen. Der Assistent schlägt vor, „Amazing Grace" als Beispiellied hinzuzufügen, mit dem Sie verstehen können, wie das Programm funktioniert.

Nachdem Sie den Willkommens-Assistenten abgeschlossen haben, sollten Sie auch die Schriftarteinstellungen, die Textfarbe oder die Hintergrundfarbe nach Ihren Wünschen anpassen. Dies können Sie in den **Einstellungen** (Bearbeiten -> Einstellungen) tun. Die Option *Nächste Folie vorzeigen* zeigt die Liedtexte des nächsten Liedabschnitts in kleinerer Schriftgröße unter dem aktuellen Abschnitt an.

Darüber hinaus können Sie konfigurieren, wie die **Metadaten** der Lieder angezeigt werden sollen. Weitere Details finden Sie im Abschnitt Metadaten.

## Das Liedauswahl-Fenster

Wenn die Konfiguration erfolgreich abgeschlossen wurde, gelangen Sie zum Liedauswahl-Fenster, in dem Sie die Lieder auswählen können, die Sie singen möchten. Das Suchfeld kann Ihnen helfen, das gewünschte Lied zu finden. Doppelklicken Sie einfach oder drücken Sie die Eingabetaste nach der Auswahl des Liedes in der linken Liste, und das Lied wird in die rechte Liste verschoben, wo Sie die Reihenfolge anpassen oder ausgewählte Lieder entfernen können.
![](/images/cantara-songselection-en.png)

Wenn Sie fertig sind, drücken Sie die Schaltfläche *Präsentation*, um die Präsentation zu starten. Sie können stattdessen auch *STRG+P* drücken.

{{% notice tip %}}
Cantara erkennt beim Start automatisch, ob Sie einen zweiten Monitor (wie einen zweiten Bildschirm oder einen Beamer) an Ihren PC angeschlossen haben. Falls ja, wählt es automatisch den Zwei-Fenster-Modus. Sie können dies auch nach Belieben anpassen.
{{% /notice %}}

## Während des Präsentationsmodus

Im Präsentationsmodus können Sie die Präsentationsfolien auf verschiedene Arten steuern:

* Mit den Pfeiltasten: Sie können die Pfeiltasten Ihrer Tastatur verwenden, um vorwärts oder rückwärts zu navigieren
* F5/F11 drücken: Schaltet den Vollbildmodus um
* Enter- oder Leertaste: Sie können Enter oder die Leertaste verwenden, um eine Folie vorwärts zu bewegen
* ESC drücken: Beendet die Präsentation
* Mausklick: Bewegt eine Folie vorwärts
* Auf ein Lied in der rechten Auswahlliste im Liedauswahl-Fenster klicken (nur im Multi-Screen-Modus): Sie können direkt zu einem bestimmten Lied springen

{{% notice tip %}}
Wenn Sie andere Programme wie LibreOffice Impress oder MS PowerPoint gleichzeitig im Präsentationsmodus ausführen, können Sie mit Alt+Tab einfach zwischen den Präsentatoren wechseln. Wenn der Präsentationsmodus in Cantara gestartet wird, deckt er den zweiten Bildschirm ab und befindet sich im Vordergrund. Um Cantara in den Hintergrund zu verschieben, drücken Sie Alt+Tab, um zu dem Programm zu navigieren, das Sie anzeigen möchten.
{{% /notice %}}

## Die Präsentation anpassen

Nachdem Sie den Standard-Präsentationsstil gesehen haben, möchten Sie ihn möglicherweise nach Ihren Wünschen und Bedürfnissen anpassen. Dazu können Sie den Einstellungsdialog öffnen (Bearbeiten -> Einstellungen). Dort können Sie Folgendes einrichten:

![](/images/cantara-settings-en.png)

- **Song-Repo-Pfad**: Der Pfad des Song-Repositorys. Verwenden Sie die Schaltfläche mit den drei Punkten (..), um einen Dateiauswahl-Dialog zu öffnen.
- **Leere Folien zwischen Liedern**: Erstellt eine zusätzliche leere Folie in der Präsentation *zwischen* zwei verschiedenen Liedern.
- **Nächste Folie vorzeigen**: Zeigt den Inhalt oder Teile der nächsten Folie unterhalb des Textes an, wenn das Lied eine weitere Folie hat und der Platz auf der Folie ausreicht.
- **Ausrichtung**: Passen Sie die horizontale und vertikale Ausrichtung des Textes auf den Präsentationsfolien an. Drücken Sie **Details**, um die Randgröße einzurichten.
- **Automatischer Zeilenumbruch**: Bricht die Folien auf, wenn ein Vers (Liedteil) das festgelegte Zeilenlimit erreicht hat (besonders empfohlen bei Liedern mit langen Versen).
- **Schriftarteinstellungen ändern.../Hintergrundfarbe.../Textfarbe...**: Öffnet Dialoge zur Festlegung des Präsentationsdesigns.
- **Hintergrundbild**: Öffnet einen Dateiauswahl-Dialog, in dem Sie ein Hintergrundbild für Ihre Präsentationen auswählen können. Wenn verfügbar, wird zunächst der Ordner mit einigen Standard-Hintergrundbildern geöffnet.
- **Bildtransparenz ändern**: Passt die Bildtransparenz **in Richtung** der Hintergrundfarbe an. Das bedeutet: Wenn die Hintergrundfarbe beispielsweise auf Schwarz eingestellt ist, macht ein höherer Wert das Bild *dunkler*. Bei weißem Hintergrund würde ein höherer Wert das Bild *heller* machen.
- **Metadaten anzeigen**: Bestimmte Metadaten können auf einer speziellen Titelfolie (falls gewählt), auf der ersten oder auf der letzten Folie angezeigt werden. Geben Sie die Syntax in das große Bearbeitungsfeld unten ein und lesen Sie [Metadaten](/tutorial/meta-data) für Details.
- **Vorschaubild**: Klicken Sie auf die Vorschau, um eine Folie vorwärts zu gehen. Wenn die Präsentation ihr Ende erreicht hat, kehrt sie zum Anfang zurück.

## Präsentation exportieren

Cantara bietet verschiedene Möglichkeiten zum Exportieren von Präsentationen, damit sie in einem anderen Programm oder für einen anderen Zweck wiederverwendet werden können. Alle Exportoptionen sind im *Export-Menü* des Hauptfensters verfügbar. Im Allgemeinen gibt es zwei Arten von Exporten:

1. **Präsentationsfolien exportieren**: Damit werden die Präsentationsfolien genau so exportiert, wie sie in Cantara angezeigt werden. Derzeit gibt es zwei Exportoptionen für diesen Typ:
   1. **PowerPoint-Präsentation** (.pptx-Datei): Exportiert die Folienpräsentation als pptx-Datei, damit sie in einem Präsentationsprogramm (Microsoft PowerPoint, LibreOffice Impress, SoftMaker Presentation usw.) verwendet werden kann. Für die Erstellung der Folien wird die JavaScript-Bibliothek [PptxGenJs](https://gitbrent.github.io/PptxGenJS/) (MIT-Lizenz) im lokalen Webbrowser als Renderer verwendet.
   2. **Bilder/Fotos**: Exportiert eine JPEG-Datei für jede Folie und speichert sie in einem Ordner Ihrer Wahl.
2. **Liedtexte als Markup exportieren**: Exportiert die Liedtexte in der richtigen Reihenfolge in einem bestimmten Markup-Format, jedoch ohne Präsentationseinstellungen (Folienumbrüche, Hintergrundbild, Farben usw.). Dies kann (aber ist nicht beschränkt auf) folgendes verwendet werden:
   - Export der Lieder als WhatsApp-/Telegram-Nachricht, die in Gruppen/Kanälen für die Gemeinde/Personen zum Mitsingen geteilt werden kann
   - Export der Lieder als HTML-Webseite zur Veröffentlichung auf einer Webseite
   - Export nur der Liedtitel zur Meldung an CCLI

Die Struktur des Markups kann durch eine LaTeX-ähnliche Markup-Sprache festgelegt werden. Gehen Sie zu *Export -> Markup-Text*, um das Markup-Exportfenster zu öffnen.

![](/images/cantara-markup-export.png)

Die Vorlagensprache unterstützt folgende Befehle/Umgebungen. Alle sind *optional*:

- ```\header { ... }```: Der Kopfbereich des Dokuments, der oben im Dokument angezeigt wird. Hier können keine liedspezifischen Inhalte angezeigt werden, da dieser Teil außerhalb der Lied-Schleife liegt.
- ```\footer { ... }```: Der Fußbereich des Dokuments, der unten im Dokument angezeigt wird. Hier können keine liedspezifischen Inhalte angezeigt werden, da dieser Teil außerhalb der Lied-Schleife liegt.
- ```\newline```: Fügt einen systemstandardmäßigen Zeilenumbruch ein
- ```\betweensongs { ... }```: Definiert, was zwischen zwei Liedern angezeigt werden soll (aber nicht vor dem ersten und nach dem letzten Lied). Der Standardwert ist auf zwei Zeilenumbrüche eingestellt (ein neuer Absatz: ```\betweensongs { \newline \newline }```)
- ```\lineending```: Gibt das Zeilenende innerhalb der Lied-Schleife an (Standardwert ist ```\newline```)
- ```\songloop { ... }``` Der Inhalt, der **für jedes Lied** angezeigt wird (für jedes Lied wiederholt). Innerhalb dieser Umgebung kann auf Lied-Tags (siehe [Metadaten](/tutorial/meta-data)) über ```\tagname``` zugegriffen werden – z. B. ```\title``` für den ```title```-Tag und ```\author``` für den ```author```-Tag. Die Liedtexte selbst werden über den Befehl ```\lyrics``` geladen.

## Liedauswahlen speichern und laden

Sie können Liedauswahlen in Cantara speichern und laden, um sie innerhalb der Organisation zu teilen oder für eine Veranstaltung vorzubereiten. Dabei haben Sie zwei Möglichkeiten:

1. Das **Songtex**-Format enthält die Liedtitel **und** die Lieddate mit ihrem Inhalt. Das bedeutet: Wenn Sie die Liedauswahl in eine Songtex-Datei exportieren, muss der Empfänger die Lieder nicht in seinem Song-Repository haben. Beim Importieren der Songtex-Datei prüft Cantara, ob die Datei bereits im Repository vorhanden ist, und fügt sie gegebenenfalls hinzu.
2. Die ältere Export-/Importfunktion importiert nur die Titel, das heißt, der Empfänger muss die Lieder in seinem Song-Repository haben.
