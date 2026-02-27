---
title: "Versionshinweise"
date: 2022-08-02T16:34:40+02:00
draft: false
weight: 2

---

Diese Seite enthält Informationen über die Änderungen in verschiedenen Versionen (Releases) und Pläne für die Zukunft.

---

## Versionen

### Version 2.7.1 (27.02.2026)

#### Neue Funktionen

- **Schwarzen Bildschirm während der Präsentation umschalten**: Eine neue Schaltfläche in der Präsentationssteuerleiste ermöglicht es, den Bildschirm sofort auf Schwarz zu schalten und wieder herzustellen. Die Tastenkombination `B` hat denselben Effekt.

#### Fehlerbehebungen

- Speicherlecks behoben: `DestroyPresentationStyleSettings` war eine Nulloperation und hat das zugehörige `TFont` nie freigegeben, was bei jedem Präsentationsstart, jeder Stilvorschau-Aktualisierung und jedem Bildexport zu Schriftart-Lecks führte.
- Einen SIGSEGV-Absturz beim Schließen von Cantara während einer aktiven Präsentation behoben: `FormHide` wurde während der Formularzerstörung ausgelöst (nachdem `FormDestroy` bereits Objekte freigegeben hatte), was zu Nullzeiger-Dereferenzierungen über `PresentationCanvas` und ungültigen Fensterhandle-Zugriffen führte.
- Alle blanken `.Destroy`-Aufrufe in Destruktoren und `FormDestroy`-Handlern durch `FreeAndNil` ersetzt, um Nullzeiger-Abstürze beim Abbau zu verhindern.
- Ein Speicherleck in `TLoadImageThread` behoben: das gespeicherte `TPresentationStyleSettings.Font` wurde beim Überschreiben durch einen neuen `LoadData`-Aufruf nie freigegeben.
- Ein Speicherleck in `TfrmSettings.gbPresentationClick` behoben: der vorhandene Vorschau-Canvas wurde vor dem Erstellen eines neuen nicht freigegeben.

### Version 2.7.0 (21.02.2026)

#### Neue Funktionen

- **Liedspezifische Stilüberschreibungen**: Jedes Lied in der Auswahl kann nun ein eigenes Hintergrundbild, eine eigene Hintergrundfarbe, Textfarbe, Schriftart, Transparenz und horizontale Ausrichtung haben – unabhängig von den globalen Präsentationseinstellungen. Ein dedizierter „Liedstil"-Dialog ist über das Rechtsklick-Kontextmenü auf jedem Lied zugänglich.
- **Liedspezifische PPTX-Master**: Beim Export nach PowerPoint kann jedes Lied seine eigene benutzerdefinierte Master-Folie verwenden.
- **Überblendungsübergang zwischen Folien**: Ein sanfter Überblendungseffekt zwischen Folien kann in den Einstellungen aktiviert werden. Die Überblendungsdauer ist konfigurierbar (Standard: 150 ms).
- **Schwarzer Bildschirm bei leerer Folie**: Eine neue Einstellung bewirkt, dass Cantara einen reinen schwarzen Bildschirm anstelle des Hintergrunds anzeigt, wenn eine leere Folie angezeigt wird.
- **JSON-Liedauswahl-Export/Import**: Liedauswahlen können jetzt als `.json`-Dateien gespeichert und geladen werden. Das Format bündelt Liedinhalt, liedspezifische Stilüberschreibungen und Hintergrundbilder in einer einzigen portablen Datei, was einen vollständigen Roundtrip-Export/Import zwischen verschiedenen Geräten ermöglicht.
- **Windows-Dunkelmodus**: Cantara folgt jetzt der Systemeinstellung für den Dunkelmodus unter Windows.
- **Windows-Installer**: Ein Inno-Setup-Installer ist jetzt für Windows verfügbar.
- **Dialog für Drittanbieter-Bibliotheken**: Ein neuer Dialog listet alle von Cantara verwendeten Drittanbieter-Bibliotheken zusammen mit ihren Lizenzen auf.

#### Verbesserungen

- Verbesserte Flatpak-Berechtigungsverwaltung: Cantara verwendet jetzt das XDG-Portal für den Dateizugriff in Sandbox-Umgebungen und bietet einen Standardöffnungs-Dialog zur Auswahl von Hintergrundbildern.
- Verbesserte Textwiedergabe mit einer benutzerdefinierten Zeilenumbruchfunktion für genauere Zeilenumbrüche.
- Verbesserte Schriftart-Rendering-Qualitätseinstellungen.
- Aktualisierte und erweiterte Übersetzungen.
- Der Hauptfenstertitel wurde auf „Cantara" vereinfacht.

#### Fehlerbehebungen

- Einen Absturz (SIGSEGV) beim Starten einer Präsentation behoben, nachdem Lieder über „Alle auswählen" oder Drag-and-Drop hinzugefügt wurden oder nach Verwendung des Suchfilters – der `TRepoFile`-Objektverweis wurde in diesen Codepfaden nicht an Listeneinträge angehängt.
- Behoben, dass der Liededitor beim Aufruf aus dem Kontextmenü das falsche Lied öffnete (falsche Dateisuche und ein Timing-Problem bei der Formularinitialisierung).
- Behoben, dass Hintergrundfarbe und Transparenzänderungen nicht im Liedstil-Vorschaudialog widergespiegelt wurden.
- Behoben, dass Hintergrundfarbe und Transparenzänderungen nicht im Präsentationsfenster und Bildexport angewendet wurden, wenn zwei Lieder dasselbe Hintergrundbild, aber unterschiedliche Farben verwenden.
- Behoben, dass das Metadaten-Parsing Feldwerte abschnitt, die ein Doppelpunkt-Zeichen enthielten.
- Ein Layout-Überlappungsproblem des Hintergrundfarbpanels und ein falsches Vorzeichen beim Transparenzwert im Liedstil-Dialog behoben.
- Einen Typumwandlungsfehler bei der PPTX-benutzerdefinierten Master-Folie-Suche behoben.
- Eine Ausnahme beim Schließen der Anwendung unter bestimmten Bedingungen behoben.
- Behoben, dass `.txt`-Dateien nicht als gültige Liedateien erkannt wurden.
- Mehrere Textgrößen- und Zeilenlängenberechnungsprobleme im Präsentations-Canvas behoben.
- Einen Inhaltsbereich-Layout-Fehler behoben, der Cantara als Flatpak betraf.

### Version 2.6.0 (31.05.2024)

- Migration zu bgrabitmap für eine bessere Handhabung und Anzeige der Präsentationsfolien. In Zukunft können weitere Texteffekte wie Schatten usw. einfach implementiert werden.
- Neugestaltung des Multi-Screen-Präsentationscontrollers: Zusätzlich zu den Liedern werden jetzt alle Folien mit Inhalt aufgelistet und können direkt ausgewählt werden.
- Kontextmenü des Präsentationsfensters: Vollbild und Beenden der Präsentation können jetzt auch mit diesem Menü ausgewählt werden.
- Kleinere Verbesserungen des Lied-Editors und der Volltextsuche.
- „Alle Lieder auswählen" unter dem Dateimenü in der Liedauswahl hinzugefügt.
- Fehlerbehebung: Falsche Anzeige der Präsentation, wenn keine spezifische Schriftart ausgewählt wurde #24
- Fehlerbehebung: Drag-and-Drop-Ausnahme im Liedauswahl-Fenster
- Fehlerbehebung: Falsches Escaping von Sonderzeichen im pptx-Export
- Viele kleinere Fehlerbehebungen und Korrekturen
- Übersetzungsupdate

### Version 2.5.0 (21.08.2023)

- Vollständige Neuschreibung großer Teile des Quellcodes einschließlich der internen Strukturen zur Generierung und Darstellung von Präsentationsfolien
- Verbesserung des Präsentationslayouts
- Verbesserung des Lied-Editors
- Implementierung einer Vorschau der Präsentation im Einstellungsmenü
- Implementierung des Folienexports nach pptx (unter Verwendung von PptxgenJs)
- Implementierung des Folienexports als Bilder
- Implementierung des Liedtext-Exports in Markup-Textdateien
- Implementierung einer Volltextsuche zum Durchsuchen von Liedtexten
- Implementierung einer zweisprachigen Liedpräsentation
- Verbesserungen des Präsentationsfensters und der Steuerung (weitere Tasten und Fernbedienungen werden unterstützt)
- Behebung von [Issue #17](https://github.com/reckel-jm/cantara/issues/17)
- Cantara kann jetzt direkt mit einer ```.songtex```-Datei geöffnet werden.

### Version 2.4.1 (30.01.2023) Italienische und spanische Übersetzung

Version 2.4.1 fügt Cantara eine italienische und spanische Übersetzung hinzu. Abgesehen davon gibt es keine zusätzliche Funktionalität im Vergleich zu Version 2.4.0, was bedeutet, dass Sie nicht unbedingt auf diese Version aktualisieren müssen, wenn Sie keine dieser Sprachen verwenden.

**Vielen Dank an die Übersetzer!**

* Die italienische Übersetzung wurde von [@albanobattistella](https://github.com/albanobattistella) bereitgestellt
* Die spanische Übersetzung wurde von [@haggen88](https://github.com/haggen88) bereitgestellt

Vielen Dank für die Mühe!

### Version 2.4.0 (06.01.2023)

Version 2.4 ist endlich da! Neben neuen Funktionen bringt sie auch viele Fehlerbehebungen. Weitere Details finden Sie in der Liste unten.

#### Verbesserungen/Erweiterungen

* Ein neuer Editor wurde implementiert, der das Bearbeiten von Liedern, die Konvertierung von CCLI-Liedern in das Song-Format, das Erstellen neuer Lieder, das Archivieren und Klonen (z. B. für verschiedene Versionen) ermöglicht.
* Ein Willkommens-Assistent führt neue Benutzer nach dem ersten Start von Cantara durch die Einrichtung und hilft, das Programm zu verstehen.
* Cantara kann lange Folien automatisch in zwei Seiten aufteilen, wenn dies in den Einstellungen konfiguriert ist.
* Das neu implementierte SongTeX-Dateiformat ermöglicht den Export von Liedfolien mit den Liedtexten und der Reihenfolge.

#### Fehlerbehebungen

- Gleitkomma-Fehler, wenn kein Hintergrundbild ausgewählt war
- Das Laden der Folien dauerte lange, wenn ein Hintergrund ausgewählt war

### Version 2.3.2 (10.11.2022)

Dies ist ein Minor-Release mit zwei kleinen, aber nützlichen Verbesserungen:

* Vervollständigung der traditionellen chinesischen Übersetzung
* Bereitschaft für Flatpak

Weitere Details finden Sie auf der entsprechenden [GitHub-Seite](https://github.com/reckel-jm/cantara/releases/tag/v2.3.2).

### Version 2.3.1 (12.08.2022)

Dies ist ein Minor-Release und Nachfolger von Version 2.3.

#### Verbesserungen

- Version 2.3.1 bringt Unterstützung für Hintergrundbilder. Diese können angepasst und transparent gemacht werden (in Richtung der Hintergrundfarbe) oder heller.

#### Fehlerbehebungen

- Behebung eines Rechtschreibfehlers im CCLI-Lizenz-Tag. Es heißt jetzt korrekt `ccli-licensenumber`
- Vollständige deutsche Übersetzung

### Version 2.3 (02.08.2022)

Nach Tests und weiterer Entwicklung kann Version 2.3 veröffentlicht werden.

Verbesserungen:

* Unterstützung des CCLI Songselect-Formats
* Unterstützung für Metadaten, die während des Liedes dynamisch angezeigt werden können
* Verbesserungen im Quellcode
* Vorbereitungen für die weitere Entwicklung im Quellcode, Abstraktionen
* Fehlerbehebungen bei der Anzeige der Lieder

Wie immer freue ich mich über Feedback, Vorschläge und Fehlerberichte.
Vielen Dank!

[Zur Github-Seite des Releases](https://github.com/reckel-jm/cantara/releases/tag/v2.3)
