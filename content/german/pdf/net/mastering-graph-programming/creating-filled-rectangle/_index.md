---
"description": "Entdecken Sie in diesem Schritt-für-Schritt-Tutorial die Möglichkeiten der PDF-Bearbeitung mit Aspose.PDF für .NET. Erfahren Sie, wie Sie durch das Zeichnen gefüllter Rechtecke programmgesteuert optisch ansprechende PDF-Dokumente erstellen."
"linktitle": "Erstellen eines gefüllten Rechtecks"
"second_title": "Aspose.PDF für .NET API-Referenz"
"title": "Erstellen eines gefüllten Rechtecks"
"url": "/de/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## Einführung

Wollten Sie schon immer visuell beeindruckende PDFs programmgesteuert erstellen? Dann sind Sie hier genau richtig! In diesem Tutorial erkunden wir Aspose.PDF für .NET, eine leistungsstarke Bibliothek, die die Bearbeitung von PDF-Dokumenten vereinfacht. Heute konzentrieren wir uns auf die Erstellung eines gefüllten Rechtecks in einer PDF-Datei. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, diese Anleitung führt Sie Schritt für Schritt durch jeden Schritt. Also, schnappen Sie sich Ihren Programmierhut und los geht‘s!

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Visual Studio: Installieren Sie Visual Studio auf Ihrem Computer, da es eine hervorragende IDE für die .NET-Entwicklung ist.
2. Aspose.PDF für .NET: Laden Sie die Aspose.PDF-Bibliothek herunter und installieren Sie sie von [Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie die Codeausschnitte besser verstehen.

## Schritt 1: Erstellen Sie ein neues Projekt

1. Öffnen Sie Visual Studio und erstellen Sie ein neues Konsolenanwendungsprojekt.
2. Geben Sie Ihrem Projekt einen passenden Namen.

## Schritt 2: Aspose.PDF-Referenz hinzufügen

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach Aspose.PDF und installieren Sie die neueste Version.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nachdem wir nun alles eingerichtet haben, tauchen wir in den Code ein!

## Schritt 3: Richten Sie Ihr Dokumentverzeichnis ein

Geben Sie den Pfad an, in dem Ihre PDF-Datei gespeichert werden soll:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersetzen `"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad auf Ihrem Computer, in dem Sie die PDF-Datei speichern möchten.

## Schritt 4: Erstellen einer Dokumentinstanz

Initialisieren Sie ein neues PDF-Dokument:

```csharp
// Dokumentinstanz erstellen
Document doc = new Document();
```

## Schritt 5: Dem Dokument eine Seite hinzufügen

Jedes PDF benötigt mindestens eine Seite. Fügen wir eine hinzu:

```csharp
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Page page = doc.Pages.Add();
```

## Schritt 6: Erstellen einer Graph-Instanz

A `Graph` Instanz fungiert als Leinwand zum Zeichnen von Formen:

```csharp
// Graph-Instanz erstellen
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## Schritt 7: Fügen Sie das Diagramm zur Seite hinzu

Hängen Sie das Diagramm an die Seite an:

```csharp
// Fügen Sie der Absatzsammlung der Seiteninstanz ein Diagrammobjekt hinzu
page.Paragraphs.Add(graph);
```

## Schritt 8: Erstellen Sie eine Rechteckinstanz

Definieren Sie die Position und Größe des Rechtecks:

```csharp
// Rechteckinstanz erstellen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## Schritt 9: Füllfarbe festlegen

Wählen Sie eine Farbe für Ihr Rechteck. Für dieses Beispiel verwenden wir Rot:

```csharp
// Füllfarbe für Graph-Objekt angeben
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Schritt 10: Fügen Sie das Rechteck zum Diagramm hinzu

Fügen Sie dem Diagramm das Rechteck hinzu:

```csharp
// Fügen Sie der Formensammlung des Graph-Objekts ein Rechteckobjekt hinzu
graph.Shapes.Add(rect);
```

## Schritt 11: Speichern Sie das PDF-Dokument

Speichern Sie Ihr Dokument abschließend im angegebenen Verzeichnis:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
```

## Schritt 12: Bestätigungsnachricht

Drucken Sie eine Bestätigungsmeldung, um den Erfolg anzuzeigen:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich ein gefülltes Rechteck in einem PDF-Dokument erstellt. Diese leistungsstarke Bibliothek eröffnet Ihnen unzählige Möglichkeiten zur PDF-Bearbeitung und ermöglicht Ihnen die programmgesteuerte Erstellung beeindruckender Dokumente. Egal, ob Sie Berichte, Rechnungen oder andere PDF-Dateien erstellen – Aspose.PDF bietet Ihnen alles.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können.

### Kann ich Aspose.PDF kostenlos nutzen?
Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Funktionen der Bibliothek erkunden können. Sie können es herunterladen [Hier](https://releases.aspose.com/).

### Gibt es eine Möglichkeit, Support für Aspose.PDF zu erhalten?
Absolut! Sie erhalten Unterstützung über das Aspose-Forum [Hier](https://forum.aspose.com/c/pdf/10).

### Wie kann ich Aspose.PDF kaufen?
Sie können Aspose.PDF kaufen, indem Sie die Kaufseite besuchen [Hier](https://purchase.aspose.com/buy).

### Welche Arten von Formen kann ich mit Aspose.PDF erstellen?
Mit der Aspose.PDF-Bibliothek können Sie verschiedene Formen erstellen, darunter Rechtecke, Kreise, Linien und mehr.