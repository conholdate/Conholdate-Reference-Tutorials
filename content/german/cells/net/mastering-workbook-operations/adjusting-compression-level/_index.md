---
"description": "Erfahren Sie, wie Sie große Excel-Dateien effizient verwalten, indem Sie die Komprimierungsstufen mit Aspose.Cells für .NET anpassen. Diese Schritt-für-Schritt-Anleitung deckt alles ab, vom Einrichten von Verzeichnissen bis zum Messen der Komprimierungszeiten, und hilft Ihnen, die Dateigröße zu optimieren und die Leistung zu verbessern."
"linktitle": "Anpassen der Komprimierungsstufe in der Arbeitsmappe"
"second_title": "Aspose.Cells .NET Excel-Verarbeitungs-API"
"title": "Anpassen der Komprimierungsstufe in der Arbeitsmappe"
"url": "/de/cells/net/mastering-workbook-operations/adjusting-compression-level/"
"weight": 14
---

## Einführung

Die Verwaltung großer Excel-Dateien kann eine Herausforderung sein, insbesondere wenn es um Speicher- und Übertragungseffizienz geht. Glücklicherweise kann die Dateikomprimierung die Größe dieser Dateien deutlich reduzieren und so ihre Handhabung erleichtern. Wenn Sie Aspose.Cells für .NET verwenden, können Sie den Komprimierungsgrad Ihrer Arbeitsmappen einfach anpassen. Diese Anleitung führt Sie Schritt für Schritt durch den Prozess und bietet klare Erklärungen zu jedem Codeteil.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie die Codeausschnitte besser verstehen.
2. Aspose.Cells-Bibliothek: Laden Sie die Aspose.Cells-Bibliothek herunter und installieren Sie sie von [Hier](https://releases.aspose.com/cells/net/).
3. Visual Studio: Zum Ausführen des Codes ist eine Entwicklungsumgebung wie Visual Studio erforderlich.
4. .NET Framework: Stellen Sie sicher, dass Ihr Projekt mit einer kompatiblen Version des .NET Frameworks eingerichtet ist.

## Importieren der erforderlichen Pakete

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. Fügen Sie oben in Ihrer Codedatei die folgenden Zeilen hinzu:

```csharp
using Aspose.Cells.Rendering;
using Aspose.Cells.WebExtensions;
using System;
```

Diese Pakete sind für die Arbeit mit Excel-Dateien mit der Aspose.Cells-Bibliothek unerlässlich. Die `Aspose.Cells` Namespace enthält alle Klassen, die zum Bearbeiten von Excel-Dateien erforderlich sind, während `Aspose.Cells.Xlsb` bietet Optionen zum Speichern von Dateien im XLSB-Format.

## Schritt 1: Quell- und Ausgabeverzeichnisse definieren

Richten Sie zunächst die Verzeichnisse ein, in denen sich Ihre Quelldateien befinden und in denen Sie die Ausgabedateien speichern möchten:

```csharp
// Definieren Sie Quell- und Ausgabeverzeichnisse
string sourceDir = "Your Document Directory\\";
string outDir = "Your Document Directory\\";
```

Stellen Sie sicher, dass Sie `"Your Document Directory\\"` mit den tatsächlichen Pfaden zu Ihren Verzeichnissen. Dadurch wird sichergestellt, dass Ihr Programm die Dateien findet, mit denen es arbeiten muss.

## Schritt 2: Laden Sie die Arbeitsmappe

Laden Sie als Nächstes die Arbeitsmappe, die Sie komprimieren möchten:

```csharp
Workbook workbook = new Workbook(sourceDir + "LargeSampleFile.xlsx");
```

Hier erstellen wir eine neue Instanz des `Workbook` Klasse und laden Sie eine vorhandene Excel-Datei. Stellen Sie sicher, dass der Dateiname mit dem in Ihrem Quellverzeichnis übereinstimmt.

## Schritt 3: Speicheroptionen einrichten

Konfigurieren Sie nun die Speicheroptionen für Ihre Arbeitsmappe:

```csharp
XlsbSaveOptions options = new XlsbSaveOptions();
```

Der `XlsbSaveOptions` Mit der Klasse können Sie beim Speichern Ihrer Arbeitsmappe im XLSB-Format verschiedene Optionen angeben, einschließlich der Komprimierungsstufen.

## Schritt 4: Messen Sie die Komprimierungszeit für Stufe 1

Beginnen Sie mit der ersten Komprimierungsstufe und messen Sie die Zeit, die zum Speichern der Arbeitsmappe benötigt wird:

```csharp
options.CompressionType = OoxmlCompressionType.Level1;
var watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_1_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 1 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Dieses Snippet setzt den Komprimierungstyp auf Stufe 1, speichert die Arbeitsmappe und misst die verstrichene Zeit.

## Schritt 5: Messen Sie die Komprimierungszeit für Stufe 6

Testen Sie als Nächstes die Leistung mit Komprimierung der Stufe 6:

```csharp
options.CompressionType = OoxmlCompressionType.Level6;
watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_6_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 6 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Dieser Schritt ähnelt dem vorherigen, weist jedoch eine höhere Komprimierungsstufe auf.

## Schritt 6: Messen Sie die Komprimierungszeit für Stufe 9

Bewerten Sie abschließend die Leistung mit der höchsten Komprimierungsstufe:

```csharp
options.CompressionType = OoxmlCompressionType.Level9;
watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_9_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 9 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Dieser Schritt setzt die Komprimierungsstufe auf Stufe 9, bei der Sie wahrscheinlich die deutlichste Reduzierung der Dateigröße feststellen werden, die Verarbeitung kann jedoch länger dauern.

## Schritt 7: Endgültige Ausgabe

Nachdem alle Komprimierungsstufen abgeschlossen sind, geben Sie eine Meldung aus, die angibt, dass der Vorgang erfolgreich abgeschlossen wurde:

```csharp
Console.WriteLine("Compression adjustment completed successfully.");
```

Diese einfache Zeile bestätigt, dass Ihr Programm ohne Probleme ausgeführt wurde.

## Abschluss

Das Anpassen des Komprimierungsgrads Ihrer Arbeitsmappen mit Aspose.Cells für .NET ist ein unkomplizierter Vorgang, der zu erheblichen Verbesserungen der Dateigröße und Leistung führen kann. Mit den in diesem Handbuch beschriebenen Schritten können Sie die Komprimierung effizient in Ihre Anwendungen implementieren und so Ihre Excel-Dateiverwaltung verbessern.

## Häufig gestellte Fragen

### Was ist Aspose.Cells?  
Aspose.Cells ist eine leistungsstarke Bibliothek für .NET, mit der Entwickler Excel-Dateien erstellen, bearbeiten und konvertieren können, ohne Microsoft Excel zu benötigen.

### Wie installiere ich Aspose.Cells?  
Sie können Aspose.Cells von der [Aspose-Website](https://releases.aspose.com/cells/net/).

### Welche Komprimierungsstufen sind verfügbar?  
Aspose.Cells unterstützt mehrere Komprimierungsstufen von Stufe 1 (niedrigste Komprimierung) bis Stufe 9 (höchste Komprimierung).

### Kann ich Aspose.Cells kostenlos testen?  
Ja! Sie können eine kostenlose Testversion von Aspose.Cells erhalten [Hier](https://releases.aspose.com/).

### Wo finde ich Support für Aspose.Cells?  
Bei Fragen oder für Support besuchen Sie das Aspose-Supportforum [Hier](https://forum.aspose.com/c/cells/9).