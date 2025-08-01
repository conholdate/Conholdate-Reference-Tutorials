---
"description": "Entdecken Sie, wie Sie XPS-Dokumente (XML Paper Specification) mithilfe der leistungsstarken Aspose.Page für .NET-Bibliothek nahtlos in PDF (Portable Document Format) konvertieren."
"linktitle": "Konvertieren von XPS in PDF"
"second_title": "Aspose.Page .NET API"
"title": "Konvertieren von XPS in PDF mit Aspose.Page für .NET"
"url": "/de/page/net/convert-document/converting-xps-to-pdf/"
"weight": 11
---

## Einführung

In diesem Tutorial erfahren Sie, wie Sie XPS-Dokumente (XML Paper Specification) mithilfe der vielseitigen Aspose.Page für .NET-Bibliothek in PDF (Portable Document Format) konvertieren. Diese leistungsstarke Bibliothek vereinfacht die Dokumentkonvertierung und bietet zahlreiche Anpassungsmöglichkeiten, was sie zu einer hervorragenden Wahl für Entwickler macht.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:

- Aspose.Page für .NET-Bibliothek: Laden Sie die Aspose.Page für .NET-Bibliothek von der [Aspose.Page-Dokumentation](https://reference.aspose.com/page/net/).
  
- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung mit Visual Studio oder einer anderen kompatiblen IDE ein.

- XPS-Dokument: Halten Sie die XPS-Datei, die Sie konvertieren möchten, bereit und speichern Sie sie in einem dafür vorgesehenen Verzeichnis.

## Schritt 1: Erforderliche Namespaces importieren

Beginnen Sie mit dem Importieren des erforderlichen Namespaces, um auf die Aspose.Page-Funktionen zuzugreifen:

```csharp
using Aspose.Page.XPS;
```

## Schritt 2: Dokumentverzeichnis initialisieren

Definieren Sie den Verzeichnispfad, in dem Ihre Dokumente gespeichert werden:

```csharp
string dataDir = "Your Document Directory";
```

Stellen Sie sicher, dass Sie `"Your Document Directory"` durch den tatsächlichen Pfad zum Verzeichnis, das Ihr XPS-Dokument enthält.

### Schritt 3: PDF- und XPS-Streams öffnen

Initialisieren Sie als Nächstes die Streams sowohl für die XPS-Eingabedatei als auch für die PDF-Ausgabedatei:

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Stellen Sie sicher, dass Sie den richtigen Pfad für Ihre Dateien festgelegt haben.

### Schritt 4: Laden Sie das XPS-Dokument

Laden Sie nun Ihr XPS-Dokument mithilfe der Aspose.Page-Bibliothek:

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Schritt 5: PDF-Speicheroptionen konfigurieren

Richten Sie die Speicheroptionen für Ihr PDF ein, einschließlich Bildqualität und Komprimierungsparameter:

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100, // Stellen Sie die JPEG-Qualitätsstufe ein
    ImageCompression = PdfImageCompression.Jpeg, // Verwenden Sie die JPEG-Komprimierung für Bilder
    TextCompression = PdfTextCompression.Flate, // Wenden Sie die Flate-Komprimierung für Text an
    PageNumbers = new int[] { 1, 2, 6 } // Geben Sie die einzuschließenden Seitenzahlen an
};
```

Passen Sie diese Parameter gerne Ihren Anforderungen an.

### Schritt 6: Erstellen Sie das PDF-Rendering-Gerät

Erstellen Sie ein Rendering-Gerät für das PDF-Format:

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Schritt 7: Speichern Sie das Dokument als PDF

Speichern Sie das XPS-Dokument abschließend mit dem angegebenen Gerät und den angegebenen Optionen als PDF:

```csharp
document.Save(device, options);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben ein XPS-Dokument mit Aspose.Page für .NET erfolgreich in PDF konvertiert. Diese Bibliothek vereinfacht nicht nur die Dokumentkonvertierung, sondern bietet auch umfangreiche Funktionen für die Verarbeitung verschiedener Formate.

## Häufig gestellte Fragen

### Kann ich mehrere XPS-Dateien in eine einzige PDF-Datei konvertieren?

Auf jeden Fall! Sie können mehrere XPS-Dateien durchlaufen und sie mit denselben Konvertierungsschritten zu einem einzigen PDF-Dokument zusammenführen.

### Welche anderen Ausgabeformate unterstützt Aspose.Page für .NET?

Zusätzlich zu PDF unterstützt Aspose.Page für .NET eine Reihe von Formaten, darunter TIFF, JPEG und PNG.

### Wie kann ich das Erscheinungsbild der konvertierten PDF-Datei anpassen?

Sie können die Parameter im `PdfSaveOptions` Objekt, wie JPEG-Qualität und Komprimierungseinstellungen, um das gewünschte Erscheinungsbild zu erzielen.

### Gibt es eine Testversion für Aspose.Page für .NET?

Ja, Sie können Aspose.Page für .NET mit einer kostenlosen Testversion ausprobieren. [Hier](https://releases.aspose.com/).

### Wo finde ich Community-Support für Aspose.Page für .NET?

Für Community-Diskussionen und Support besuchen Sie die [Aspose.Page-Forum](https://forum.aspose.com/c/page/39).