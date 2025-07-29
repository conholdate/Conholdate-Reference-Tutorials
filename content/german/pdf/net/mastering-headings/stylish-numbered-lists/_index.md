---
"description": "Entdecken Sie, wie Sie mit Aspose.PDF für .NET ansprechend nummerierte Listen in Ihren PDF-Dokumenten erstellen. Diese Anleitung führt Sie durch die Anwendung verschiedener Nummerierungsstile – beispielsweise römischer Ziffern."
"linktitle": "Stilvolle nummerierte Listen mit Aspose.PDF für .NET"
"second_title": "Aspose.PDF für .NET API-Referenz"
"title": "Stilvolle nummerierte Listen mit Aspose.PDF für .NET"
"url": "/de/net/programming-with-headings/stylish-numbered-lists/"
"weight": 10
---

## Einführung

Mussten Sie schon einmal gut strukturierte, nummerierte Listen in Ihren PDF-Dokumenten erstellen? Ob für juristische Dokumente, Berichte oder Präsentationen – effektive Nummerierungsstile sind entscheidend für die Organisation Ihrer Inhalte. Mit Aspose.PDF für .NET können Sie Ihren PDF-Überschriften ganz einfach verschiedene Nummerierungsstile hinzufügen und so ansprechende und professionelle Dokumente erstellen.

## Voraussetzungen

Bevor wir mit der Codierung beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:

1. Aspose.PDF für .NET: Laden Sie die neueste Version herunter von [Hier](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Sie benötigen Visual Studio oder eine beliebige .NET-kompatible IDE.
3. .NET Framework: Stellen Sie sicher, dass Sie .NET Framework 4.0 oder höher installiert haben.
4. Lizenz: Sie können eine temporäre Lizenz von [Hier](https://purchase.aspose.com/temporary-license/) oder erkunden Sie die [kostenlose Testversion](https://releases.aspose.com/) Optionen.

## Importieren der erforderlichen Pakete

Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr Projekt:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 1: Einrichten des Dokuments

Beginnen wir mit der Erstellung eines neuen PDF-Dokuments und der Konfiguration seines Layouts, einschließlich Seitengröße und Rändern.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Festlegen von Seitenabmessungen und Rändern
pdfDoc.PageInfo.Width = 612.0; // 8,5 Zoll
pdfDoc.PageInfo.Height = 792.0; // 11 Zoll
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo(72, 72, 72, 72); // 1-Zoll-Ränder
```

Mit dieser Einstellung erhält Ihr Dokument die Standardbriefgröße mit einem Rand von einem Zoll auf allen Seiten.

## Schritt 2: Hinzufügen einer Seite zum PDF

Als nächstes fügen wir dem PDF-Dokument eine leere Seite hinzu, auf der wir später die Nummerierungsstile anwenden.

```csharp
// Fügen Sie dem PDF-Dokument eine neue Seite hinzu
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo = pdfDoc.PageInfo; // Verwenden Sie dieselben Einstellungen wie im Dokument
```

## Schritt 3: Erstellen einer schwebenden Box

Mit einer FloatingBox können Sie Inhalte unabhängig vom Seitenfluss positionieren und haben so mehr Kontrolle über Ihr Layout.

```csharp
// Erstellen Sie eine FloatingBox für strukturierte Inhalte
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox
{
    Margin = pdfPage.PageInfo.Margin
};
pdfPage.Paragraphs.Add(floatBox);
```

## Schritt 4: Überschriften mit römischen Ziffern hinzufügen

Fügen wir nun unsere erste Überschrift mit einer Nummerierung in Kleinbuchstaben mit römischen Ziffern hinzu.

```csharp
// Erstellen Sie die erste Überschrift mit römischen Ziffern
Aspose.Pdf.Heading heading1 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 1,
    Text = "List 1",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading1);
```

## Schritt 5: Hinzufügen einer zweiten Überschrift mit benutzerdefinierter Startnummer

Als Nächstes fügen wir eine zweite Überschrift hinzu, beginnend mit der römischen Zahl 13.

```csharp
// Erstellen Sie eine zweite Überschrift, beginnend bei der römischen Zahl 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 13,
    Text = "List 2",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading2);
```

## Schritt 6: Hinzufügen einer Überschrift mit alphabetischer Nummerierung

Zur Abwechslung fügen wir eine dritte Überschrift mit alphabetischer Nummerierung in Kleinbuchstaben hinzu.

```csharp
// Erstellen Sie eine Überschrift mit alphabetischer Nummerierung
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2)
{
    IsInList = true,
    StartNumber = 1,
    Text = "The value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed",
    Style = NumberingStyle.LettersLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading3);
```

## Schritt 7: Speichern der PDF

Speichern wir abschließend die PDF-Datei im gewünschten Verzeichnis.

```csharp
// Speichern Sie das PDF-Dokument
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine($"\nNumber style applied successfully in headings.\nFile saved at {dataDir}");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich verschiedene Nummerierungsstile – römische Ziffern und alphabetische – auf Überschriften in einer PDF-Datei angewendet. Dank der Flexibilität von Aspose.PDF können Sie Seitenlayout, Nummerierungsstile und Inhaltspositionierung steuern und so übersichtliche und professionelle PDF-Dokumente erstellen.

## Häufig gestellte Fragen

### Kann ich verschiedene Nummerierungsstile auf dasselbe PDF-Dokument anwenden?  
Ja, Sie können verschiedene Nummerierungsstile wie römische Ziffern, arabische Ziffern und alphabetische Nummerierungen im selben Dokument mischen.

### Wie kann ich die Startnummer für Überschriften anpassen?  
Sie können die Startnummer für jede Überschrift mit dem `StartNumber` Eigentum.

### Gibt es eine Möglichkeit, die Nummerierungsreihenfolge zurückzusetzen?  
Ja, Sie können die Nummerierung zurücksetzen, indem Sie die `StartNumber` Eigenschaft für jede Überschrift.

### Kann ich Überschriften zusätzlich zur Nummerierung fett oder kursiv formatieren?  
Absolut! Sie können Überschriftenstile anpassen, indem Sie Eigenschaften wie Schriftart, Größe, Fettdruck und Kursivschrift mithilfe der `TextState` Objekt.

### Wie erhalte ich eine temporäre Lizenz für Aspose.PDF?  
Eine vorläufige Lizenz erhalten Sie bei [Hier](https://purchase.aspose.com/temporary-license/) um Aspose.PDF ohne Einschränkungen zu testen.