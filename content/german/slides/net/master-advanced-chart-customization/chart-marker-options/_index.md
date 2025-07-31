---
"description": "Erfahren Sie, wie Sie Ihre PowerPoint-Diagramme mit Aspose.Slides für .NET mit benutzerdefinierten Markierungsoptionen optimieren. Diese Schritt-für-Schritt-Anleitung behandelt Voraussetzungen, Diagrammerstellung, Datenpunktformatierung und mehr."
"linktitle": "Diagrammmarkierungsoptionen für Datenpunkte in Aspose.Slides .NET"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Diagrammmarkierungsoptionen für Datenpunkte in Aspose.Slides .NET"
"url": "/de/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## Einführung

Visuelle Hilfsmittel sind für eine wirkungsvolle Kommunikation unerlässlich. Aspose.Slides für .NET bietet leistungsstarke Tools zum Erstellen und Anpassen von Diagrammen und ermöglicht Entwicklern, ihre Datenpräsentationen zu optimieren. Eines der herausragenden Features ist die Möglichkeit, Diagrammmarkierungen für Datenpunkte zu verwenden, um präzise Anpassungen für professionell wirkende Diagramme zu ermöglichen. Dieser Artikel führt Sie Schritt für Schritt durch die Umsetzung.

## Voraussetzungen

Bevor Sie fortfahren, stellen Sie Folgendes sicher:

- Aspose.Slides für .NET installiert: Laden Sie es herunter von [Hier](https://releases.aspose.com/slides/net/).
- Grundlegende Einrichtung: Eine Präsentationsdatei, z. B. „Test.pptx“, in Ihrem Arbeitsverzeichnis.
- Entwicklungsumgebung: Visual Studio oder gleichwertig, konfiguriert für .NET.

## Importieren der erforderlichen Namespaces

Fügen Sie Ihrem Projekt die erforderlichen Namespaces für eine nahtlose Entwicklung hinzu:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Schritt 1: Erstellen Sie ein Diagramm in Ihrer Präsentation

Beginnen Sie mit der Erstellung eines Standarddiagramms auf der ersten Folie Ihrer Präsentation:

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

Dies fügt eine `LineWithMarkers` Fügen Sie Ihrer Folie ein Diagramm mit den angegebenen Abmessungen hinzu.

## Schritt 2: Abrufen des Arbeitsblattindexes für Diagrammdaten

Der Standardindex des Diagrammdaten-Arbeitsblatts ist für die weitere Anpassung unerlässlich:

```csharp
int defaultWorksheetIndex = 0;
```

## Schritt 3: Zugriff auf die Arbeitsmappe „Diagrammdaten“

Um Diagrammdaten zu bearbeiten, rufen Sie die zugehörige Arbeitsmappe ab:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## Schritt 4: Diagrammreihen konfigurieren und Datenpunkte hinzufügen

Löschen Sie die Standardreihen und fügen Sie neue Datenpunkte für Ihre Reihen hinzu:

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Datenpunkte zur Reihe hinzufügen
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## Schritt 5: Bildfüllungen auf Datenpunktmarkierungen anwenden

Benutzerdefinierte Bilder können Datenmarkierungen optisch ansprechend gestalten:

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Benutzerdefinierte Bilder für Markierungen festlegen
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## Schritt 6: Markierungsgröße anpassen

Ändern Sie die Größe der Markierungen, um die Sichtbarkeit zu verbessern:

```csharp
series.Marker.Size = 20;
```

## Schritt 7: Speichern Sie die aktualisierte Präsentation

Speichern Sie die angepasste Präsentation am gewünschten Ort:

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Abschluss

Aspose.Slides für .NET bietet Entwicklern Tools zur Erstellung professioneller Diagramme mit umfangreichen Anpassungsmöglichkeiten. Durch die Nutzung von Diagrammmarkierungsoptionen können Sie die visuelle Attraktivität und Übersichtlichkeit Ihrer Präsentationen deutlich verbessern. Diese Schritt-für-Schritt-Anleitung stellt sicher, dass selbst komplexe Anpassungen einfach umzusetzen sind.

## Häufig gestellte Fragen

### Kann ich jedes Bildformat zur Markeranpassung verwenden?
Ja, Aspose.Slides unterstützt verschiedene Bildformate, darunter JPEG, PNG und BMP, zur Markeranpassung.

### Wie ändere ich den Diagrammtyp nach der Erstellung?
Um den Diagrammtyp zu ändern, rufen Sie das `chart.Type` Eigenschaft und weisen Sie eine andere `ChartType`.

### Ist Aspose.Slides für .NET mit älteren PowerPoint-Versionen kompatibel?
Ja, es unterstützt die Abwärtskompatibilität mit älteren PowerPoint-Formaten und gewährleistet so Vielseitigkeit.

### Kann ich Diagrammdaten dynamisch aktualisieren?
Absolut. Nutzen Sie die `IChartDataWorkbook` um Diagrammdaten programmgesteuert zu aktualisieren.

### Wo finde ich weitere Ressourcen?
Entdecken Sie die [Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) oder treten Sie der [Community-Foren](https://forum.aspose.com/) für Unterstützung.