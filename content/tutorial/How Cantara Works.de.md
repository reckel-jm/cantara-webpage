---
title: "Wie Cantara funktioniert"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 1
---

## Hintergrundgeschichte

Als ich auf dem Gymnasium war, wurde ich Teil der Leitung einer christlichen Jugendgruppe. Wenn wir unsere Veranstaltungen durchführten, sangen wir zu Beginn gerne ein paar Lieder. Allerdings gab es das Problem, dass die vorhandenen Liederbücher nicht ausreichten und der Inhalt manchmal nicht zu den gewünschten Liedern passte. Damals suchte ich nach einem verfügbaren Liedpräsentationsprogramm und wurde schnell enttäuscht. Die meisten existierenden Programme waren entweder kommerziell, sehr umfangreich oder einfach ein „Overkill" für den im Grunde recht einfachen Zweck: Die Leute sollten (spontan) Lieder auswählen können, das Programm sollte sie dann anzeigen.

Zu dieser Zeit beschloss ich, mit der Entwicklung von Cantara zu beginnen. Der Name kommt vom lateinischen „cantare" (singen), ist aber eher künstlich als authentisch gewählt. Ein weiterer Grund für die Wahl des Namens war, dass ich zur gleichen Zeit Organist in der Kirche wurde – und der deutsche Name für diese Position ist „Kantor", was ziemlich ähnlich klingt.

Später konnte ich die [beste Studentengruppe der Welt](https://www.smd-chemnitz.de) leiten 😃 und währenddessen wuchs das Programm langsam und wurde mit neuen Funktionen wie Multiscreen-Unterstützung und der Möglichkeit, Liedtexte direkt in die Zwischenablage zu exportieren, aktualisiert, sodass es in kleinen Gruppen ohne Beamer-Projektionsmöglichkeit verwendet werden kann. Die Entwicklung von Cantara wird weitergehen und ich hoffe, dass es ein kleines Werkzeug sein wird, um unseren großen himmlischen Vater zu loben und anzubeten!

## Die Herangehensweise

{{<mermaid align="left">}}
graph LR;
    A[Eingabedatei] -->|Lieder sammeln| B(Liedliste)
    B --> C(Liedauswahl)
    C --> D{Präsentationsdaten generieren}
    D --> E[Präsentation direkt starten]
    D --> F[Liedtexte im Markup-Format exportieren]
    D --> G[Präsentation als PPTX exportieren]
    D --> H[Präsentation als Bilder exportieren]
{{< /mermaid >}}

Cantara nimmt die Lieder aus *einem bestimmten Ordner* auf dem Dateisystem, der *Liederverzeichnis (oder Song-Repository, bzw. kurz Song-Repo) genannt wird. Jedes Lied ist eine einfache Textdatei, die mit einem Texteditor Ihrer Wahl bearbeitet werden kann. Cantara erkennt den Songtitel anhand des Dateinamens (ohne Erweiterung). Wenn Sie zum Beispiel eine Datei haben wie:

    Amazing Grace.song

erkennt Cantara diese als „Amazing Grace" im Songformat (zu den Formaten siehe den nächsten Abschnitt).

{{% notice tip %}}
Das Liederverzeichnis kann einfach über Cloud-Dienste wie NextCloud oder Git geteilt und synchronisiert werden. Auf diese Weise können Sie Lieder innerhalb Ihrer Gruppe oder Organisation weitergeben.
{{% /notice %}}

{{% notice tip %}}
Seit Version 2.4.0 bietet Cantara einen eingebauten Editor, mit dem Sie die Lieder bearbeiten und CCLI-Lieder in das Cantara-Songformat konvertieren können. Beachten Sie, dass die Lieder weiterhin einzelne Textdateien sind und daher mit jedem Texteditor bearbeitet werden können.
{{% /notice %}}

{{% notice warning %}}
Die Entwickler von Cantara sind nicht verantwortlich für Urheberrechtsfragen, die mit der öffentlichen Nutzung und Verbreitung von Liedtexten einhergehen. Vergewissern Sie sich, dass Sie die Rechte für die Verwendung der Liedtexte einholen! In Deutschland genießen religiöse Versammlungen mit freiem Eintritt eine größere urheberrechtliche Freiheit als kommerzielle Veranstaltungen. Bitte stellen Sie jedoch gemeinsam mit Ihrer Organisation sicher, dass keine rechtlichen Probleme entstehen.
{{% /notice %}}

## Die Fenster/Modi von Cantara

Cantara besteht aus verschiedenen Fenstern, die Ihnen die Nutzung des Programms ermöglichen.

{{< tabs groupid="main" style="primary" title="Fenster" icon="window-maximize" >}}
{{< tab title="Liedauswahl-Fenster" >}}
  Dieses Fenster wird nach dem Start von Cantara angezeigt. Es ermöglicht Ihnen, die verfügbaren Lieder zu sehen und diejenigen auszuwählen, die Sie in der Präsentation verwenden oder exportieren möchten.

  <img src="/images/cantara-songselection-selected-hints-de.png" loading="lazy" alt="Liedauswahl-Fenster von Cantara" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< tab title="Präsentationsfenster" style="default" >}}
  Das Präsentationsfenster zeigt und steuert die geladene Präsentation (im Einzelbildschirm-Modus). Es kann auf Vollbild gesetzt und auf einen anderen Bildschirm verschoben werden.
  Wenn Sie das Präsentationsfenster schließen, endet die Präsentation und Sie kehren zum Liedauswahl-Fenster zurück.

  <img src="/images/cantara-presentation-de.png" loading="lazy" alt="Präsentationsfenster von Cantara" class="bg-white border lazy noshadow">

{{< /tab >}}

{{< tab title="Präsentationssteuerung" style="default" >}}
  Im Multi-Screen-Modus ermöglicht die Präsentationssteuerung eine detaillierte Kontrolle der Präsentation, die im Präsentationsfenster angezeigt wird. Sie können alle Folien sehen, direkt zu einer Folie springen oder die Präsentation beenden.

  Normalerweise platzieren Sie die Präsentationssteuerung auf dem ersten Bildschirm (dem Standardbildschirm) und das Präsentationsfenster auf dem zweiten Bildschirm (der am Beamer, externen Monitor usw. angezeigt wird).

  <img src="/images/cantara-presentationcontroller-en.png" loading="lazy" alt="Präsentationssteuerung von Cantara" class="bg-white border lazy noshadow">

  {{% notice tip %}}
  Die Präsentationssteuerung verwendet das Liedauswahl-Fenster.
  {{% /notice %}}

{{< /tab >}}

{{< tab title="Einstellungen" style="default" >}}
Das Einstellungsfenster ermöglicht es Ihnen, den Präsentationsstil anzupassen und den Pfad des Song-Repositorys zu ändern. Sie können die Einstellungen im Liedauswahl-Fenster öffnen.

  <img src="/images/cantara-settings-en.png" loading="lazy" alt="Die Einstellungen in Cantara" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< tab title="Editor" style="default" >}}
Der Editor ermöglicht es, Lieder in Ihrem Song-Repository hinzuzufügen, zu bearbeiten, zu konvertieren und zu entfernen. Sie können den Editor über Bearbeiten -> Liedtexte... im Liedauswahl-Fenster öffnen.

<img src="/images/cantara-editor-en.png" loading="lazy" alt="Der Editor in Cantara" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< /tabs >}}
