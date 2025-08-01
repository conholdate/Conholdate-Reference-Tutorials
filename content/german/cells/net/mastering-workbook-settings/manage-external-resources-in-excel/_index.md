---
"description": "Entdecken Sie, wie Sie externe Ressourcen in Excel-Arbeitsmappen mit Aspose.Cells für .NET nahtlos steuern. Diese umfassende Anleitung führt Sie durch jeden Schritt – von der Implementierung eines benutzerdefinierten Stream-Providers bis zum Rendern von Arbeitsblättern."
"linktitle": "Verwalten Sie externe Ressourcen in Excel mit Aspose.Cells für .NET"
"second_title": "Aspose.Cells .NET Excel-Verarbeitungs-API"
"title": "Verwalten Sie externe Ressourcen in Excel mit Aspose.Cells für .NET"
"url": "/de/cells/net/mastering-workbook-settings/manage-external-resources-in-excel/"
"weight": 10
---

## Einführung

Bei der Arbeit mit Daten in Excel kann die nahtlose Verwaltung externer Ressourcen die Funktionalität Ihrer Anwendung erheblich verbessern. Wenn Sie Bilder und andere externe Elemente in Excel-Arbeitsmappen mit Aspose.Cells für .NET steuern möchten, sind Sie hier richtig! Diese Anleitung führt Sie Schritt für Schritt durch den Prozess und ermöglicht Ihnen die Implementierung einer maßgeschneiderten Lösung für den mühelosen Umgang mit diesen Ressourcen.

## Voraussetzungen

Bevor wir uns mit den Codierungsaspekten befassen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:

1. Visual Studio: Eine IDE zum Schreiben und Testen Ihrer .NET-Anwendungen. Visual Studio wird aufgrund seines umfassenden Supports und der benutzerfreundlichen Oberfläche empfohlen.
2. Aspose.Cells für .NET: Laden Sie die Bibliothek von der [Aspose Cells-Releaseseite](https://releases.aspose.com/cells/net/).
3. Grundkenntnisse in C#: Wenn Sie mit den Konzepten von C# und .NET vertraut sind, verstehen Sie die Implementierung besser.
4. Richten Sie Ihr Projekt ein: Stellen Sie sicher, dass Ihr Projekt auf die Aspose.Cells-Bibliothek verweist, die Sie über den NuGet-Paket-Manager in Visual Studio hinzufügen können.
5. Beispieldateien: Halten Sie zu Demonstrationszwecken eine Excel-Beispieldatei bereit, die externe Ressourcen (z. B. verknüpfte Bilder) enthält.

Sobald alle Voraussetzungen erfüllt sind, können wir mit der Verwaltung externer Ressourcen mit Aspose.Cells beginnen.

## Pakete importieren
Um mit dem Programmieren zu beginnen, müssen Sie die erforderlichen Pakete in Ihre C#-Datei importieren. Folgendes benötigen Sie:
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using Aspose.Cells.Rendering;
using System.Drawing.Imaging;
```

## Schritt 1: Verzeichnisse definieren

Geben Sie zunächst die Quell- und Ausgabeverzeichnisse an, in denen Ihre Dateien gespeichert sind und wo Ihre Ausgabedateien gespeichert werden sollen.

```csharp
// Definieren Sie das Quellverzeichnis
static string sourceDir = @"C:\Path\To\Your\Documents\"; // Passen Sie den Pfad an
// Definieren Sie das Ausgabeverzeichnis
static string outputDir = @"C:\Path\To\Your\Output\";
```

Stellen Sie sicher, dass Sie die Pfade durch die tatsächlichen Verzeichnisse auf Ihrem Computer ersetzen.

### Schritt 2: Implementieren der IStreamProvider-Schnittstelle

Als nächstes erstellen Sie eine benutzerdefinierte Klasse, die Folgendes implementiert: `IStreamProvider` Schnittstelle. Diese Klasse verwaltet den Zugriff auf externe Ressourcen wie Bilder.

```csharp
class CustomStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        // Bereinigen Sie Ressourcen, falls erforderlich
        options.Stream?.Close();
    }

    public void InitStream(StreamProviderOptions options)
    {
        // Öffnen Sie den Dateistream für die externe Ressource
        options.Stream = new FileStream(Path.Combine(sourceDir, "image.png"), FileMode.Open, FileAccess.Read);
    }
}
```

Im `InitStream` Methode öffnen wir die Datei, die als Ihre externe Ressource dient, und weisen sie dem `Stream` Eigentum.

### Schritt 3: Laden Sie die Excel-Datei

Laden wir nun die Excel-Arbeitsmappe, die die externe Ressource enthält.

```csharp
public static void Execute()
{
    // Laden Sie die Excel-Datei
    Workbook workbook = new Workbook(Path.Combine(sourceDir, "sample.xlsx"));
    
    // Zuweisen des benutzerdefinierten Streamanbieters
    workbook.Settings.StreamProvider = new CustomStreamProvider();
```

Dieses Snippet lädt Ihre Excel-Datei und weist den benutzerdefinierten Stream-Anbieter für die Handhabung externer Ressourcen zu.

### Schritt 4: Zugriff auf das Arbeitsblatt

Nach dem Laden der Arbeitsmappe können Sie problemlos auf das gewünschte Arbeitsblatt zugreifen.

```csharp
    // Greifen Sie auf das erste Arbeitsblatt zu
    Worksheet worksheet = workbook.Worksheets[0];
```

Sie können auf jedes Arbeitsblatt zugreifen, indem Sie seinen Index angeben.

### Schritt 5: Bild- und Druckoptionen konfigurieren

Definieren Sie, wie das Ausgabebild aussehen soll, indem Sie Bild- oder Druckoptionen konfigurieren.

```csharp
    // Bild- oder Druckoptionen festlegen
    ImageOrPrintOptions options = new ImageOrPrintOptions
    {
        OnePagePerSheet = true,
        ImageType = Drawing.ImageType.Png
    };
```

Die Wahl von PNG gewährleistet eine scharfe und klare Ausgabe.

### Schritt 6: Rendern Sie das Arbeitsblatt in ein Bild

Jetzt kommt der spannende Teil – das Rendern des Arbeitsblatts in eine Bilddatei!

```csharp
    // Erstellen Sie ein Blatt-Rendering und konvertieren Sie das Arbeitsblatt in ein Bild
    SheetRender sheetRender = new SheetRender(worksheet, options);
    sheetRender.ToImage(0, Path.Combine(outputDir, "output.png"));
    
    Console.WriteLine("Excel sheet rendered successfully to an image!");
}
```

Dieser Code konvertiert das gesamte Arbeitsblatt in ein PNG-Bild, das in Ihrem angegebenen Ausgabeverzeichnis gespeichert wird.

## Abschluss

Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie externe Ressourcen in Excel-Dateien mit Aspose.Cells für .NET steuern. Diese Funktionalität erweitert nicht nur die Möglichkeiten Ihrer Anwendung, sondern vereinfacht auch die Verwaltung von Datensätzen und Präsentationen. Mit den oben beschriebenen Schritten können Sie diese Lösung an die individuellen Anforderungen Ihres Projekts anpassen.

## Häufig gestellte Fragen

### Was ist Aspose.Cells?
Aspose.Cells ist eine robuste Bibliothek, die für .NET-Entwickler zum Erstellen, Bearbeiten und Verwalten von Excel-Dateien entwickelt wurde, ohne dass Microsoft Excel erforderlich ist.

### Wie kann ich Aspose.Cells für .NET herunterladen?
Sie können es herunterladen von der [Aspose-Website](https://releases.aspose.com/cells/net/).

### Gibt es eine kostenlose Testversion?
Ja! Aspose bietet eine kostenlose Testversion von Aspose.Cells an, verfügbar auf ihrer [Release-Seite](https://releases.aspose.com/cells/net/).

### Welche Dateitypen unterstützt Aspose.Cells?
Aspose.Cells unterstützt verschiedene Excel-Formate, darunter XLS, XLSX, CSV und mehr.

### Wo finde ich Support für Aspose.Cells?
Besuchen Sie die [Aspose Forum](https://forum.aspose.com/c/cells/9) für Hilfe und Unterstützung durch die Gemeinschaft.