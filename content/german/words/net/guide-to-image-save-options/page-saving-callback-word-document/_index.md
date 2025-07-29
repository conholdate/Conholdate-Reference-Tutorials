---
"description": "Erfahren Sie, wie Sie mit Aspose.Words für .NET jede Seite eines Word-Dokuments einfach in einzelne PNG-Bilder konvertieren. Diese Anleitung enthält Schritt-für-Schritt-Anleitungen mit Codebeispielen."
"linktitle": "Rückruf zum Speichern von Seiten in Word-Dokumenten"
"second_title": "Aspose.Words Dokumentverarbeitungs-API"
"title": "Rückruf zum Speichern von Seiten in Word-Dokumenten"
"url": "/de/words/net/guide-to-image-save-options/page-saving-callback-word-document/"
"weight": 10
---

## Einführung

Mussten Sie schon einmal jede Seite eines Word-Dokuments in einzelne Bilder konvertieren? Ob Sie Miniaturansichten für eine Vorschau erstellen oder einen langen Bericht in verständliche Grafiken zerlegen möchten – Aspose.Words für .NET macht diese Aufgabe einfach und effizient. In dieser Anleitung führen wir Sie durch die Einrichtung eines Callbacks zum Speichern von Seiten, um jede Seite Ihres Dokuments als PNG-Bild zu speichern. Los geht's!

## Voraussetzungen

Bevor Sie loslegen, stellen Sie sicher, dass Sie Folgendes haben:

1. Aspose.Words für .NET: Laden Sie es herunter und installieren Sie es von [Hier](https://releases.aspose.com/words/net/).
2. Visual Studio: Jede Version funktioniert, aber wir verwenden für diese Anleitung Visual Studio 2019.
3. Grundlegende C#-Kenntnisse: Wenn Sie mit C# vertraut sind, können Sie problemlos mitkommen.

## Schritt 1: Erforderliche Namespaces importieren

Zunächst müssen wir die benötigten Namespaces importieren. Dadurch können wir auf die benötigten Klassen und Methoden zugreifen, ohne jedes Mal den vollständigen Namespace eingeben zu müssen.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Schritt 2: Definieren Sie Ihr Dokumentverzeichnis

Legen Sie anschließend den Pfad zu Ihrem Dokumentverzeichnis fest. Hier befindet sich Ihr Word-Eingabedokument und hier werden die Ausgabebilder gespeichert.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Laden Sie Ihr Dokument

Laden Sie nun das zu verarbeitende Dokument. Stellen Sie sicher, dass sich das Dokument „Rendering.docx“ im angegebenen Verzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 4: Konfigurieren Sie die Bildspeicheroptionen

Wir richten die Optionen zum Speichern von Bildern ein und geben an, dass wir die Seiten als PNG-Dateien speichern möchten.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

Hier, `PageSet` definiert den Bereich der zu speichernden Seiten und `PageSavingCallback` verweist auf unsere benutzerdefinierte Rückrufklasse.

## Schritt 5: Implementieren des Rückrufs zum Speichern der Seite

Jetzt müssen wir die Rückrufklasse implementieren, die regelt, wie jede Seite gespeichert wird.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

Diese Klasse implementiert die `IPageSavingCallback` Schnittstelle. Im `PageSaving` Methode geben wir das Benennungsmuster für jede gespeicherte Seite an.

## Schritt 6: Speichern Sie das Dokument als Bilder

Abschließend speichern wir das Dokument mit den konfigurierten Optionen.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich einen Rückruf zum Speichern von Seiten eingerichtet, um jede Seite eines Word-Dokuments mit Aspose.Words für .NET als separates PNG-Bild zu speichern. Diese Technik ist für verschiedene Anwendungen äußerst nützlich, von der Erstellung von Seitenvorschauen bis hin zur Generierung einzelner Seitenbilder für Berichte.

## Häufig gestellte Fragen

### Kann ich Seiten in anderen Formaten als PNG speichern?
Ja! Sie können Seiten in Formaten wie JPEG, BMP und TIFF speichern, indem Sie die `SaveFormat` In `ImageSaveOptions`.

### Wie kann ich nur bestimmte Seiten speichern?
Um bestimmte Seiten zu speichern, passen Sie die `PageSet` Parameter in `ImageSaveOptions` um nur die gewünschten Seiten einzuschließen.

### Ist es möglich, die Bildqualität anzupassen?
Absolut! Sie können die Qualität des Ausgabebildes steuern, indem Sie Eigenschaften wie `ImageSaveOptions.JpegQuality`.

### Wie kann ich große Dokumente effizient verarbeiten?
Erwägen Sie bei großen Dokumenten die Verarbeitung der Seiten in Stapeln, um die Speichernutzung effektiv zu verwalten.

### Wo finde ich weitere Informationen zu Aspose.Words für .NET?
Umfassende Anleitungen und Beispiele finden Sie in der [Aspose.Words-Dokumentation](https://reference.aspose.com/words/net/).