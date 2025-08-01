---
"description": "Nutzen Sie das volle Potenzial Ihrer Excel-zu-PDF-Konvertierungen mit Aspose.Cells für .NET. In diesem umfassenden Leitfaden erfahren Sie, wie Sie externe Ressourcen wie Bilder verwalten und sicherstellen, dass Ihre PDFs Ihren genauen Formatierungsanforderungen entsprechen."
"linktitle": "Steuern Sie externe Ressourcen mit Aspose.Cells für .NET"
"second_title": "Aspose.Cells .NET Excel-Verarbeitungs-API"
"title": "Steuern Sie externe Ressourcen mit Aspose.Cells für .NET"
"url": "/de/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## Einführung

In der heutigen digitalen Welt ist die Konvertierung von Excel-Tabellen in PDF-Dokumente eine gängige und unverzichtbare Aufgabe. Ob Berichte, Finanzdaten oder Präsentationsmaterialien – die PDF-Dateien müssen das gewünschte Format aufweisen. Aspose.Cells für .NET bietet eine leistungsstarke Bibliothek, mit der Sie diesen Konvertierungsprozess detailliert steuern können, insbesondere bei externen Ressourcen wie Bildern. In diesem Leitfaden erfahren Sie, wie Sie externe Ressourcen während der Konvertierung von Excel in PDF mit Aspose.Cells effektiv verwalten. Los geht‘s!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:

1. Visual Studio oder eine beliebige .NET-kompatible IDE: Dies wird Ihre Entwicklungsumgebung sein.
2. Aspose.Cells für .NET: Wenn Sie es noch nicht installiert haben, besuchen Sie die [Aspose Downloads](https://releases.aspose.com/cells/net/) Seite, um die neueste Version zu erhalten.
3. Grundkenntnisse in C#: Kenntnisse in C# sind von Vorteil. Wenn Sie Erläuterungen zu bestimmten Konzepten benötigen, können Sie diese gerne nachschlagen.
4. Beispiel-Excel-Datei: Bereiten Sie eine Excel-Datei wie „samplePdfSaveOptions_StreamProvider.xlsx“ vor, die externe Ressourcen enthält, die Sie konvertieren möchten.
5. Bilddatei zum Testen: Verwenden Sie während der Konvertierung eine Bilddatei wie „newPdfSaveOptions_StreamProvider.png“ als externe Ressource.

## Importieren Sie die erforderlichen Pakete

Zunächst müssen Sie die erforderlichen Namespaces aus der Aspose.Cells-Bibliothek importieren. Fügen Sie oben in Ihrer C#-Datei die folgenden using-Direktiven hinzu:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

Diese Namespaces stellen die wesentlichen Klassen und Methoden für Ihre Aufgaben bereit.

## Schritt 1: Erstellen einer Stream-Provider-Klasse

Erstellen Sie zunächst eine Stream-Provider-Klasse, die Folgendes implementiert: `IStreamProvider` Schnittstelle. Mit dieser Klasse können Sie steuern, wie externe Ressourcen geladen werden.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // Laden Sie das Bild in einen Speicherstream
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: Diese Methode wird aufgerufen, wenn der Stream geschlossen wird und derzeit eine Debug-Meldung protokolliert wird.
- InitStream: Diese Methode liest die externe Bilddatei als Byte-Array, konvertiert sie in einen Speicherstrom und weist sie dem `options.Stream` Eigentum.

## Schritt 2: Quell- und Ausgabeverzeichnisse einrichten

Definieren Sie als Nächstes die Verzeichnisse für Ihre Excel-Datei und das Ausgabe-PDF.

```csharp
// Quellverzeichnis
string sourceDir = "Your Document Directory";
// Ausgabeverzeichnis
string outputDir = "Your Document Directory";
```

Ersetzen `"Your Document Directory"` durch den tatsächlichen Pfad auf Ihrem System, in dem sich Ihre Dateien befinden.

## Schritt 3: Laden Sie Ihre Excel-Datei

Laden Sie nun die Excel-Datei, aus der Sie das PDF erstellen möchten.

```csharp
// Laden Sie die Excel-Quelldatei mit externen Bildern
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

Der `Workbook` Die Klasse von Aspose.Cells stellt Ihre Excel-Datei dar, die verschiedene externe Ressourcen wie Bilder enthalten kann.

## Schritt 4: PDF-Speicheroptionen festlegen

Bevor Sie die Arbeitsmappe als PDF speichern, geben Sie die gewünschten Speicheroptionen an.

```csharp
// PDF-Speicheroptionen angeben – Stream-Anbieter
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // Jedes Blatt auf einer neuen Seite speichern
};
```

Dadurch wird eine Instanz von `PdfSaveOptions`, mit dem Sie das PDF-Format anpassen können. Die `OnePagePerSheet` stellt sicher, dass jedes Excel-Blatt im endgültigen PDF auf einer separaten Seite angezeigt wird.

## Schritt 5: Weisen Sie Ihren Stream-Anbieter zu

Verbinden Sie Ihre `Workbook` Instanz mit dem `MyStreamProvider` Klasse, die Sie zuvor erstellt haben.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

Diese Zeile stellt sicher, dass Ihr benutzerdefinierter Anbieter bei der Konvertierung auf externe Ressourcen trifft und diese entsprechend verwaltet.

## Schritt 6: Speichern Sie die Arbeitsmappe als PDF

Speichern Sie jetzt Ihre Excel-Arbeitsmappe als PDF.

```csharp
// Speichern Sie die Arbeitsmappe als PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

Durch den Aufruf der `Save` Wenn Sie die Methode auf dem Arbeitsmappenobjekt anwenden und das Ausgabeverzeichnis zusammen mit den PDF-Optionen übergeben, konvertieren Sie die Excel-Datei in eine gut formatierte PDF-Datei.

## Schritt 7: Erfolgreiche Ausführung bestätigen

Abschließend empfiehlt es sich, den erfolgreichen Abschluss des Vorgangs zu bestätigen.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

Diese Nachricht informiert Sie über den Status Ihres Vorgangs und gibt Ihnen nützliches Feedback.

## Abschluss

Sie beherrschen nun die Steuerung externer Ressourcen bei der Konvertierung von Excel in PDF mit Aspose.Cells! Mit diesen Schritten stellen Sie sicher, dass Ihre Dokumente Bilder und andere externe Elemente korrekt enthalten, was jedes Mal zu einem hochwertigen Endprodukt führt.

## Häufig gestellte Fragen

### Was ist Aspose.Cells?
Aspose.Cells ist eine leistungsstarke Bibliothek für .NET-Entwickler, die das Erstellen, Bearbeiten, Konvertieren und Rendern von Excel-Dateien in verschiedenen Formaten ermöglicht.

### Wie lade ich Aspose.Cells herunter?
Sie können die neueste Version von der [Download-Link](https://releases.aspose.com/cells/net/).

### Kann ich Aspose.Cells kostenlos testen?
Ja! Sie können eine kostenlose Testversion erhalten, indem Sie die [Seite „Kostenlose Testversion“](https://releases.aspose.com/).

### Wo finde ich Support für Aspose.Cells?
Bei Supportanfragen besuchen Sie die [Aspose Support-Forum](https://forum.aspose.com/c/cells/9).

### Wie kann ich eine temporäre Lizenz für Aspose.Cells erhalten?
Sie können eine vorläufige Lizenz beantragen [Hier](https://purchase.aspose.com/temporary-license/).