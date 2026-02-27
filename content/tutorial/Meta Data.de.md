---
title: "Lied-Metadaten"
date: 2022-08-02T15:37:14+02:00
draft: false
toc: true
weight: 5
---

Cantara ermöglicht es Ihnen, Metadaten aus den Liedern abzurufen und anzuzeigen. Je nach Liedformat erhält Cantara folgende Metadaten.

## CCLI Songselect

Aus jeder CCLI-Songselect-Liedtextdatei werden folgende Daten gesammelt:

* `author`: Der Name(n) aller Autor(en), getrennt durch ein „|".
* `ccli-licensenumber`: Die Nummer der CCLI-Lizenz, die vom Benutzerkonto abhängt (nicht vom Lied).
* `ccli-songnumber`: Die CCLI-Nummer des Liedes, die vom Lied abhängt.

## Song-Format

Im Song-Format können Metadaten durch eine Zeile mit einem `#` am Anfang angegeben werden. Zum Beispiel:

    #author: John Newton
    #title: Amazing Grace

    Amazing Grace, how sweet the sound
    that saved a wretch like me.
    I once wast lost, but now am found,
    was blind, but now I'm free!

    [...]

Damit werden die Metadaten für `author` und `title` gesetzt.

## Verwendung der Metadaten:

Im Einstellungsdialog können Sie Metadaten für jedes Lied aktivieren. Im Feld *Metadaten-Inhalt* können Sie das Format angeben, in dem Metadaten angezeigt werden sollen. Neben der Anzeige von reinem Text können Sie folgende Variablen verwenden:

* `{property1}`: Zeigt die Metadaten-Eigenschaft *property1* an, wenn sie vorhanden ist.
* `{%property1%}etwas Text{%end%}`: Zeigt *etwas Text* an, wenn *property1* vorhanden ist.
* `{%property1%}etwas Text`: Zeigt *etwas Text* (bis zum Ende der Zeile) an, wenn *property1* vorhanden ist.

Die folgende Syntax zum Beispiel:

    {%ccli-licensenumber%}Liedquelle: CCLI {ccli-licensenumber}
    {%author%}Autor: {author}

würde für das obige `Amazing Grace.song` folgendes erzeugen:

    Autor: John Newton

weil `author` vorhanden ist, aber `ccli-licensenumber` nicht.
