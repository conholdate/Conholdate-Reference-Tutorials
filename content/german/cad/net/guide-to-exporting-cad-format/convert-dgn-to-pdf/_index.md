---
"description": "Erfahren Sie, wie Sie mit der leistungsstarken Aspose.CAD-Bibliothek für .NET mühelos DGN-Dateien in PDF konvertieren. Diese Schritt-für-Schritt-Anleitung richtet sich an Entwickler aller Erfahrungsstufen."
"linktitle": "Konvertieren Sie DGN in PDF in Aspose.CAD für .NET"
"second_title": "Aspose.CAD .NET - CAD- und BIM-Dateiformat"
"title": "Konvertieren Sie DGN in PDF in Aspose.CAD für .NET"
"url": "/de/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## Einführung

Die Navigation in der Welt der CAD-Dateien kann eine Herausforderung sein, aber mit Aspose.CAD für .NET können Entwickler verschiedene CAD-Formate problemlos bearbeiten und konvertieren. Ein häufiges Bedürfnis ist die Konvertierung von DGN-Dateien in PDFs, die wir in diesem Tutorial Schritt für Schritt erläutern.

## Voraussetzungen

Um mitmachen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse in C# und dem .NET-Framework.
- Aspose.CAD für .NET-Bibliothek installiert. Sie können es herunterladen [Hier](https://releases.aspose.com/cad/net/).
- Eine Beispiel-DGN-Datei (z. B. Nikon_D90_Camera.dgn). 

## Schritt 1: Erforderliche Namespaces importieren

Beginnen Sie mit dem Importieren der relevanten Namespaces in Ihr C#-Projekt:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Schritt 2: Laden Sie die DGN-Datei

Geben Sie das Verzeichnis für Ihre DGN-Datei an und laden Sie sie mit dem folgenden Code:

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // Die weitere Verarbeitung erfolgt hier ...
}
```

## Schritt 3: Rasterisierungsoptionen konfigurieren

Richten Sie als Nächstes die Rasterungsoptionen ein, um zu definieren, wie Ihr DGN im PDF gerendert wird:

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // Passen Sie die Breite nach Bedarf an
    PageHeight = 300, // Passen Sie die Höhe nach Bedarf an
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## Schritt 4: PDF-Optionen erstellen

Definieren Sie die PDF-Optionen und integrieren Sie dabei die zuvor konfigurierten Rasterungseinstellungen:

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Schritt 5: Speichern Sie die DGN als PDF

Speichern Sie die DGN-Datei abschließend mit den von Ihnen konfigurierten Optionen als PDF:

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben eine DGN-Datei mit Aspose.CAD für .NET erfolgreich in ein PDF konvertiert. Dieses einfache Tutorial führte Sie durch das Laden der DGN-Datei, das Festlegen der Rasterungsoptionen und das Speichern der Ausgabe als PDF.

## Häufig gestellte Fragen

### Benötige ich CAD-Vorkenntnisse, um Aspose.CAD zu verwenden?  
Absolut! Aspose.CAD wurde entwickelt, um komplexe CAD-Aufgaben zu vereinfachen und es für alle Entwickler zugänglich zu machen, unabhängig von ihren CAD-Kenntnissen.

### Wo finde ich weitere Ressourcen und Dokumentation für Aspose.CAD?  
Umfassende Anleitungen und Beispiele finden Sie in der [Aspose.CAD-Dokumentation](https://reference.aspose.com/cad/net/).

### Gibt es eine kostenlose Testversion für Aspose.CAD?  
Ja, eine kostenlose Testversion ist erhältlich [Hier](https://releases.aspose.com/).

### Wie kann ich eine temporäre Lizenz für Aspose.CAD erhalten?  
Sie können temporäre Lizenzen anfordern [Hier](https://purchase.conholdate.com/temporary-license/).

### Benötigen Sie Hilfe oder haben Sie Fragen?  
Nehmen Sie an der Unterhaltung teil im [Aspose.CAD-Forum](https://forum.aspose.com/c/cad/19) für Community-Support und Anfragen.