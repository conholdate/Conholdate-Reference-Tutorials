---
"description": "Entdecken Sie, wie Sie die Seitenausrichtung von PDF-Dateien mit Aspose.PDF für .NET einfach anpassen können. Diese Schritt-für-Schritt-Anleitung bietet klare Anweisungen zum Laden, Drehen und Speichern Ihrer Dokumente."
"linktitle": "PDF-Seitenausrichtung ändern"
"second_title": "Aspose.PDF für .NET API-Referenz"
"title": "PDF-Seitenausrichtung ändern"
"url": "/de/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Einführung

Haben Sie schon einmal eine PDF-Datei mit falscher Seitenausrichtung gesehen? Ob falsch gescannt oder einfach ein anderes Layout benötigt – die Anpassung der Ausrichtung kann einen großen Unterschied machen. Aspose.PDF für .NET bietet eine leistungsstarke und benutzerfreundliche Möglichkeit, PDF-Dateien zu bearbeiten, einschließlich der Änderung der Seitenausrichtung. In dieser Anleitung führen wir Sie Schritt für Schritt durch den Vorgang, egal ob Sie von Hoch- auf Querformat oder umgekehrt wechseln möchten.

## Voraussetzungen

Bevor wir in die Details eintauchen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:

- Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Falls Sie dies noch nicht getan haben, können Sie [Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/).
- Eine .NET-Entwicklungsumgebung: Sie können Visual Studio, JetBrains Rider oder jede andere IDE Ihrer Wahl für die .NET-Entwicklung verwenden.
- Grundkenntnisse in C#: Wenn Sie mit C# vertraut sind, können Sie den Anweisungen leichter folgen.
- Eine PDF-Datei: Halten Sie eine Beispiel-PDF-Datei zum Testen bereit. Sie können eine erstellen oder ein Beispiel online herunterladen.

Wenn Sie gerade erst anfangen, sollten Sie Aspose.PDF mit einem [kostenlose temporäre Lizenz](https://purchase.aspose.com/temporary-license/) bevor Sie sich entscheiden, [Kaufen Sie die Vollversion](https://purchase.aspose.com/buy).

## Namespaces importieren

Um PDF-Seiten zu bearbeiten, müssen Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt importieren. Fügen Sie oben in Ihrer Codedatei die folgenden Zeilen hinzu:

```csharp
using System.IO;
using Aspose.Pdf;
```

Nachdem wir nun alles eingerichtet haben, können wir loslegen!

## Schritt 1: Laden Sie das PDF-Dokument

Der erste Schritt besteht darin, die PDF-Datei zu laden, die Sie ändern möchten. Verwenden Sie die `Document` Klasse aus dem Aspose.PDF-Namespace:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Stellen Sie sicher, dass Sie `"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrer PDF-Datei.

## Schritt 2: Jede Seite durchlaufen

Als Nächstes durchlaufen wir jede Seite im PDF-Dokument. Dadurch können wir die Ausrichtungsänderung auf alle Seiten anwenden:

```csharp
foreach (Page page in doc.Pages)
{
    // Bearbeiten Sie jede Seite
}
```

## Schritt 3: Zugriff auf die MediaBox der Seite

Jede PDF-Seite hat eine `MediaBox` das seine Grenzen definiert. Wir müssen darauf zugreifen, um die aktuelle Ausrichtung zu überprüfen und Anpassungen vorzunehmen:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

Der `MediaBox` gibt die Abmessungen der Seite an, einschließlich Breite und Höhe.

## Schritt 4: Breite und Höhe vertauschen

Um die Seitenausrichtung zu ändern, tauschen wir die Werte für Breite und Höhe. Diese Anpassung ändert die Abmessungen der Seite:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Hier berechnen wir die neuen Abmessungen und positionieren die untere linke Ecke neu (`LLY`) entsprechend.

## Schritt 5: Aktualisieren Sie die MediaBox und CropBox

Da wir nun die neuen Dimensionen haben, wenden wir diese Änderungen auf die `MediaBox` Und `CropBox` um sicherzustellen, dass die Seite korrekt angezeigt wird:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Schritt 6: Drehen Sie die Seite

Um die Ausrichtungsänderung abzuschließen, drehen wir die Seite. Mit Aspose.PDF ist das ganz einfach:

```csharp
page.Rotate = Rotation.on90; // Um 90 Grad drehen
```

Diese Linie dreht die Seite effektiv in die gewünschte Ausrichtung.

## Schritt 7: Speichern Sie die Ausgabe-PDF

Nachdem Sie die Ausrichtung aller Seiten geändert haben, speichern Sie das aktualisierte Dokument in einer neuen Datei:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Geben Sie unbedingt einen neuen Dateinamen an, um ein Überschreiben des Originaldokuments zu vermeiden.

## Abschluss

Und fertig! Das Ändern der Seitenausrichtung einer PDF-Datei mit Aspose.PDF für .NET ist unkompliziert. Laden Sie das Dokument, durchlaufen Sie die Seiten, aktualisieren Sie die MediaBox und speichern Sie die Datei. So passen Sie das Layout ganz einfach an Ihre Bedürfnisse an. Egal, ob Sie ein schlecht gescanntes Dokument korrigieren oder Seiten für eine Präsentation formatieren – diese Anleitung hilft Ihnen, die Arbeit effizient zu erledigen.

## Häufig gestellte Fragen

### Kann ich bestimmte Seiten statt aller Seiten im PDF drehen?  
Ja, Sie können die Schleife so ändern, dass sie bestimmte Seiten anhand ihres Indexes anspricht, anstatt alle Seiten zu durchlaufen.

### Was ist der `MediaBox`?  
Der `MediaBox` definiert die Größe und Form der Seite in einer PDF-Datei und bestimmt, wo der Inhalt platziert wird.

### Funktioniert Aspose.PDF für .NET mit anderen Dateiformaten?  
Ja, Aspose.PDF kann verschiedene Dateiformate verarbeiten, darunter HTML, XML, XPS und mehr.

### Gibt es eine kostenlose Version von Aspose.PDF für .NET?  
Ja, Sie können mit einem [kostenlose Testversion](https://releases.aspose.com/) oder fordern Sie eine [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).

### Kann ich die Änderungen nach dem Speichern rückgängig machen?  
Sobald Sie das Dokument speichern, sind die Änderungen dauerhaft. Es empfiehlt sich, an einer Kopie zu arbeiten oder eine Sicherungskopie der Originaldatei aufzubewahren.