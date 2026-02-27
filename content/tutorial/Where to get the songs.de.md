---
title: "Lieder verwalten"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 4
---

Bei der Verwendung von Cantara müssen Sie Lieder sammeln, bearbeiten und verteilen, die für Präsentationen oder Exporte verwendet werden können. Wenn Sie Cantara zum ersten Mal starten, werden Sie feststellen, dass – je nachdem, was Sie im Willkommens-Assistenten gewählt haben – möglicherweise nur ein Lied verfügbar ist: „Amazing Grace". Von da an können Sie damit beginnen, Lieder zu holen und hinzuzufügen.

Der Ordner, den Sie als Song-Repository wählen, enthält alle Lieder, die Sie in Cantara verwenden. Das bedeutet, dass es ausreicht, eine neue Datei in diesem Ordner hinzuzufügen, um ein neues Lied hinzuzufügen. Ebenso können Sie zum Bearbeiten oder Löschen von Liedern vorgehen. Wenn Sie alle Lieder mit jemandem teilen möchten, kopieren Sie einfach die Dateien Ihres Verzeichnisses oder teilen Sie den Ordner selbst.
Es hat sich auch als gängige Praxis entwickelt, ein Git-Repository in Ihrem Repository-Ordner zu erstellen, das dann über Github, Gitlab oder andere Anbieter geteilt werden kann.

## Die Art und Weise verstehen, wie Lieder gespeichert werden

Cantara unterstützt zwei verschiedene Liedformate. Eines hat die Dateiendung `.song` und ist sehr einfach aufgebaut. Es enthält lediglich die Liedtexte in der Reihenfolge, in der sie präsentiert werden sollen, zusammen mit einigen Tags, die die Metadaten der Lieder beschreiben. Das andere Format wird von [CCLI Songselect](https://songselect.ccli.com/) verwendet und hat die Dateiendungen `.txt` oder `.ccli`. CCLI ist eine kommerzielle Datenbank, aus der Sie viele christliche Lieder für die Verwendung in Kirchen oder christlichen Gruppen herunterladen können.

{{% notice tip %}}
Viele christliche Kirchengemeinschaften und Gruppen in Deutschland (darunter FeG, SMD, soweit ich weiß) bieten Mitgliedszugang zu CCLI Songselect an. Sie können herausfinden, ob Ihre Organisation bereits ein Abonnement für Sie abgeschlossen hat.
{{% /notice %}}

Cantara erkennt automatisch das richtige Liedformat und interpretiert es entsprechend.

### Das Song-Dateiformat

Das Song-Dateiformat ist eine Datei mit der Endung `.song`. Die Liedtexte müssen dort in der Reihenfolge angegeben werden, in der sie angezeigt werden sollen, einschließlich Wiederholungen. Verschiedene Folien werden durch einen doppelten Zeilenumbruch (eine leere Zeile) getrennt. Wenn Sie zum Beispiel das Lied „'Tis so sweet to trust in Jesus" hinzufügen möchten, fügen Sie eine neue Datei `'Tis so sweet to trust in Jesus.song` mit folgendem Inhalt hinzu:

{{%expand "Dateiinhalt anzeigen " %}}
    'Tis so sweet to trust in Jesus
    Just to take Him at His word
    Just to rest upon His promise
    Just to know thus saith the Lord

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    O how sweet to trust in Jesus
    Just to trust His cleansing blood
    Just in simple faith to plunge me
    'Neath the healing cleansing flood

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    Yes 'tis sweet to trust in Jesus
    Just from sin and self to cease
    Just from Jesus simply taking
    Life and rest and joy and peace

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    I'm so glad I learned to trust Thee
    Precious Jesus Savior Friend
    And I know that Thou art with me
    Wilt be with me to the end

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
{{% /expand%}}

Das Lied besteht aus vier Strophen mit dem Refrain, der nach jeder Strophe wiederholt wird. Angenommen, wir möchten eine leicht abweichende Version des Liedes, bei der wir zwei Strophen zusammen singen. Eine gute Konvention dafür wäre, die vorhandene Datei `'Tis so sweet to trust in Jesus.song` nach `'Tis so sweet to trust in Jesus [zwei Strophen zusammen].song` zu kopieren und den Inhalt anzupassen:

{{%expand "Dateiinhalt anzeigen " %}}
    'Tis so sweet to trust in Jesus
    Just to take Him at His word
    Just to rest upon His promise
    Just to know thus saith the Lord

    O how sweet to trust in Jesus
    Just to trust His cleansing blood
    Just in simple faith to plunge me
    'Neath the healing cleansing flood

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    Yes 'tis sweet to trust in Jesus
    Just from sin and self to cease
    Just from Jesus simply taking
    Life and rest and joy and peace

    I'm so glad I learned to trust Thee
    Precious Jesus Savior Friend
    And I know that Thou art with me
    Wilt be with me to the end

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
{{% /expand%}}

Cantara erkennt beide Liedateien und listet sie nebeneinander auf. Obwohl dieser Ansatz zu Beginn etwas kompliziert erscheinen mag, hat die praktische Erfahrung gezeigt, dass er viel einfacher ist als komplexere Dateiformate. Sie können jederzeit Ihren lokalen Texteditor verwenden, um die Liedtexte nach Belieben anzupassen. Es besteht keine Gefahr von Fehldeutungen oder falscher Reihenfolge.

### CCLI Songselect

Das CCLI-Songselect-Format wird verwendet, wenn Sie ein Lied von CCLI Songselect herunterladen. Im Gegensatz zum Song-Format liefert das CCLI-Songselect-Liedtextformat keine klaren Informationen über die korrekte Reihenfolge der verschiedenen Teile eines Liedes (Strophen/Refrains usw.). Daher muss Cantara die Reihenfolge mit einem implementierten Algorithmus erraten. Für **die meisten Lieder** wird Cantara die Liedtexte in die richtige Reihenfolge bringen. Einige CCLI-Lieddateien weisen jedoch Inkonsistenzen auf. In diesem Fall können Sie die CCLI-Datei in eine Song-Datei konvertieren und sie manuell nach Ihren Bedürfnissen bearbeiten.

{{% notice note %}}
Aufgrund der Inkonsistenzen wird davon abgeraten, eine CCLI-Songselect-Datei direkt zu bearbeiten. Cantara fordert Sie auf, sie zuerst in eine Song-Datei zu konvertieren.
{{% /notice %}}

Hier sind einige Informationen zu den Teilen, die Cantara versteht:

  * „Vers/Strophe": Eine Strophe, die nur einmal an der platzierten Position gesungen wird
  * „Chorus": Falls vorhanden, wird der Refrain an der platzierten Position gesungen und danach nach jeder Strophe oder Bridge wiederholt. Wenn ein anderer Refrain folgt, ersetzt er den ersten.
  * „Bridge": Wird wie eine Strophe behandelt. Ein Refrain folgt (höchstwahrscheinlich), wenn zuvor einer vorhanden war.
  * „PreChorus": Wird vor dem Refrain gesungen (hier ist das Format recht inkonsistent!)
  * „Schluss": Ein abschließender Teil des Liedes. Kein Refrain folgt.

{{% notice note %}}
Der Editor ist in der Lage, CCLI-Dateien in das Song-Format zu konvertieren. Öffnen Sie einfach eine CCLI-Datei im Editor und bestätigen Sie, dass Sie die Konvertierung durchführen möchten.
{{% /notice %}}

## Lieder von CCLI Songselect herunterladen

Wie oben erwähnt, können Sie Lieder direkt von [CCLI Songselect](https://songselect.ccli.com/) importieren. Gehen Sie auf deren Webseite, melden Sie sich mit Ihrem Konto an und suchen Sie nach dem Lied, das Sie herunterladen möchten. Drücken Sie das Sprechblasensymbol rechts daneben (siehe Bild unten). Nachdem der Text angezeigt wird, klicken Sie auf die dritte blaue Schaltfläche von links mit dem Download-Symbol. Speichern Sie die .txt-Datei direkt in das Cantara-Song-Repository-Verzeichnis. Cantara sollte das Lied erkennen und die Liedtexte in der richtigen Reihenfolge verwenden.

![](/images/ccli-results.jpg?width=800) ![](/images/ccli-song-download.jpg?width=800)

{{% notice warning %}}
Wie bereits erwähnt, liegt es in Ihrer Verantwortung, die rechtlichen Anforderungen von CCLI und den Lied-Urheberrechtsinhabern bei der Nutzung ihrer Dienste einzuhalten!
{{% /notice %}}

## Weitere Liedtext-Quellen

  * [Hymnary.org](https://hymnary.org/): Eine sehr große Hymnensammlung (überwiegend Englisch)
  * [Evangeliums.net](https://www.evangeliums.net/lieder/): Eine deutsche Sammlung christlicher Lieder, einige sind aufgrund von Urheberrechtsbeschränkungen nicht direkt zugänglich
  * [Das Cantara SongRepo auf Github](https://github.com/reckel-jm/cantara_songrepo): Enthält gemeinfreie Lieder zur freien und direkten Nutzung

## Lieder mit dem eingebauten Editor bearbeiten und konvertieren

Cantara bietet einen eingebauten Editor, der eine einfache Möglichkeit bietet, Lieder zu erstellen, zu bearbeiten oder zu entfernen. Darüber hinaus können Sie ein CCLI-Lied in das Song-Format konvertieren, damit es nach Ihren Bedürfnissen angepasst werden kann.
