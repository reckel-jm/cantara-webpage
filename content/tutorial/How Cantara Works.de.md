---
title: "Wie Cantara funktioniert"
date: 2022-07-19T15:37:14+02:00
draft: true
toc: true
weight: 1
---

## Hintergrundgeschichte

Als ich auf dem Gymnasium war, wurde ich Teil der Leitung einer christlichen Jugendgruppe. Wenn wir unsere Veranstaltungen durchführten, sangen wir zu Beginn gerne ein paar Lieder. Allerdings gab es das Problem, dass die vorhandenen Liederbücher nicht ausreichten und der Inhalt manchmal nicht zu den gewünschten Liedern passte. Damals suchte ich nach einem verfügbaren Liedpräsentationsprogramm und wurde schnell enttäuscht. Die meisten existierenden Programme waren entweder kommerziell, sehr umfangreich oder einfach ein "Overkill" für den im Grunde recht einfachen Zweck: Die Leute sollten (spontan) Lieder auswählen können, das Programm sollte sie dann anzeigen.

Zu dieser Zeit beschloss ich, mit der Entwicklung von Cantara zu beginnen. Der Name kommt vom lateinischen "cantare" (singen), ist aber eher künstlich als echt. Ein weiterer Grund für die Wahl des Namens war, dass ich zur gleichen Zeit Organist in der Kirche wurde - und der deutsche Name für diese Position ist "Kantor", was ziemlich ähnlich klingt.

Später konnte ich die [beste Studentengruppe der Welt] (https://www.smd-chemnitz.de) leiten 😃 und währenddessen wuchs das Programm langsam und wurde mit neuen Funktionen wie Multiscreen-Unterstützung und der Möglichkeit, Liedtexte direkt in die Zwischenablage zu exportieren, aktualisiert, so dass es in kleinen Gruppen ohne Beamer-Projektionsmöglichkeit verwendet werden kann. Die Entwicklung von Cantara wird weitergehen und ich hoffe, dass es ein kleines Werkzeug sein wird, um unseren großen himmlischen Vater zu loben und anzubeten!

## Die Herangehensweise

{{<mermaid align="left">}}
graph LR;
    A[Liedrepository] -->|Sammeln von Liedern| B(Liedliste)
    B --> C{Liedauswahl}
    C -->|Präsentationsdaten generieren| D[Präsentation ausführen]
{{< /mermaid >}}

Cantara nimmt die Lieder aus *einem bestimmten Ordner* auf dem Dateisystem, der *Song Repository* (oder kurz Song Repo) genannt wird. Jeder Song ist eine einfache Textdatei, die mit einem Texteditor Ihrer Wahl bearbeitet werden kann. Cantara erkennt den Songtitel anhand des Dateinamens (ohne Erweiterung). Also zum Beispiel. Wenn Sie eine Datei haben wie:

    Amazing Grace.song

erkennt Cantara, dass es sich um "Amazing Grace" handelt, das im Songformat geschrieben ist (zu den Formaten siehe den nächsten Abschnitt).

{{% notice tip %}}
Das Song-Repository-Wörterbuch kann einfach über Cloud-Dienste wie NextCloud oder Git geteilt und synchronisiert werden. Auf diese Weise können Sie Lieder innerhalb Ihrer Gruppe oder Organisation weitergeben.
{{% /notice %}}

{{% notice warning %}}
Die Entwickler von Cantara sind nicht verantwortlich für Urheberrechtsfragen, die mit der öffentlichen Nutzung und Verbreitung von Liedtexten einhergehen. Vergewissern Sie sich, dass Sie die Rechte für die Verwendung der Liedtexte einholen! In Deutschland genießen religiöse Versammlungen mit freiem Eintritt eine größere Urheberrechtsfreiheit als kommerzielle Veranstaltungen. Bitte stellen Sie jedoch mit Ihrer Organisation sicher, dass keine rechtlichen Probleme entstehen.
{{% /notice %}}