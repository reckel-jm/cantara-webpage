---
title: "Übersetzen"
date: 2022-08-10T15:11:10+02:00
weight: 2
---

Cantara kann einfach in eine andere Sprache übersetzt werden. Dabei helfen Sie, die Nutzung der Software auf der ganzen Welt zu verbreiten, sodass auch Menschen, die kein Englisch sprechen, Zugang zu Cantara haben.

## Wie es funktioniert

Cantara verwendet Sprachdateien (`*.mo`-Dateien), die die übersetzten Sprachzeichenfolgen in einer binären Sprache enthalten. Diese Dateien können mithilfe eines Editors wie [Poedit](https://poedit.net/) und der [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot)-Datei als Vorlage erstellt werden.

Wenn Sie eine Übersetzung in eine neue Sprache durchführen möchten, gehen Sie wie folgt vor:

1. Laden Sie [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot) herunter und öffnen Sie es mit einem geeigneten Editor.
2. Übersetzen Sie die Zeichenfolgen in die gewünschte Zielsprache.
3. Exportieren Sie den übersetzten Inhalt als `.mo`-Datei, **behalten Sie aber auch die übersetzte `.po`-Datei!**
4. Kopieren Sie die `sprache.mo`-Datei nach `<cantara-verzeichnis>/languages/sprache/cantara.mo` (ersetzen Sie `sprache` durch den Kurzcode der Sprache, z. B. *de* für Deutsch, *en* für Englisch, *zh* für Chinesisch usw.).
5. Testen Sie Ihre Übersetzung, indem Sie Cantara mit der Option `--lang` ausführen:

    `cantara --lang=<sprachcode>`


6. Wenn die Übersetzung gut funktioniert, erstellen Sie bitte einen Pull Request auf GitHub, damit auch andere davon profitieren können.

## Aktueller Stand

Derzeit ist Cantara in folgende Sprachen übersetzt:

| Sprache | Vollständigkeit |
|---------|----------------|
| Arabisch              | 100 %        |
| Bahasa Indonesia      | 100 %        |
| Englisch              | 100 %        |
| Chinesisch (traditionell) | 100 %    |
| Niederländisch        | 100 %        |
| Farsi                 | 100 %        |
| Französisch           | 100 %        |
| Deutsch               | 100 %        |
| Hebräisch             | 100 %        |
| Italienisch           | 100 %        |
| Japanisch             | 100 %        |
| Koreanisch            | 100 %        |
| Polnisch              | 100 %        |
| Russisch              | 100 %        |
| Spanisch              | 100 %        |
| Türkisch              | 100 %        |
| Ukrainisch            | 100 %        |
| Vietnamesisch         | 100 %        |
