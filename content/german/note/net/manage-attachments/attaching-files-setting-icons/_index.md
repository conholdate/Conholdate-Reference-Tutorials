---
"description": "Erfahren Sie Schritt für Schritt, wie Sie mit Aspose.Note für .NET Dateien anhängen und benutzerdefinierte Symbole in Microsoft OneNote-Dokumenten festlegen. Erweitern Sie Ihre .NET-Anwendung mit nahtlosen Dokumentverwaltungs- und Anpassungsfunktionen."
"linktitle": "Datei anhängen und Symbol in Aspose.Note festlegen"
"second_title": "Aspose.Note .NET API"
"title": "Anhängen von Dateien und Festlegen von Symbolen in Aspose.Note für .NET"
"url": "/de/note/net/manage-attachments/attaching-files-setting-icons/"
"weight": 10
---

## Einführung

Aspose.Note für .NET ist eine erweiterte Bibliothek für Entwickler zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von Microsoft OneNote-Dateien. Ein herausragendes Feature dieser Bibliothek ist die Möglichkeit, Dateien an OneNote-Dokumente anzuhängen und deren Symbole anzupassen. In dieser Anleitung erfahren Sie, wie Sie mit Aspose.Note für .NET nahtlos Dateien anhängen und benutzerdefinierte Symbole festlegen und so die Funktionalität Ihrer OneNote-Dokumente erweitern können.

## Voraussetzungen

Stellen Sie vor der Implementierung der Lösung sicher, dass Sie über Folgendes verfügen:

- Entwicklungsumgebung: Visual Studio oder eine ähnliche IDE, die für die .NET-Entwicklung konfiguriert ist.
- Bibliotheksinstallation: Installieren Sie die [Aspose.Note für .NET](https://releases.aspose.com/words/net/) Bibliothek.
- Programmierkenntnisse: Grundlegende Kenntnisse in C#.

## Importieren der erforderlichen Namespaces

Fügen Sie Ihrem Projekt diese Namespaces für grundlegende Funktionen hinzu:

```csharp
using System.IO;
using Aspose.Note;
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
```

Nachfolgend finden Sie die detaillierte Schritt-für-Schritt-Implementierung.

## Schritt 1: Erstellen Sie ein neues OneNote-Dokument

Initialisieren Sie ein neues OneNote-Dokument mit dem `Document` Klasse.

```csharp
Document doc = new Document();
```

## Schritt 2: Eine neue Seite hinzufügen

Fügen Sie dem Dokument eine Seite hinzu, um Ihre Notizen und Anhänge zu organisieren.

```csharp
Aspose.Note.Page page = new Aspose.Note.Page(doc);
```

## Schritt 3: Erstellen Sie eine Gliederung

Erstellen Sie ein `Outline` Objekt, das als Container für Elemente auf Ihrer OneNote-Seite dient.

```csharp
Outline outline = new Outline(doc);
```

## Schritt 4: Initialisieren eines Gliederungselements

Ein `OutlineElement` enthält den Anhang und das zugehörige Symbol.

```csharp
OutlineElement outlineElem = new OutlineElement(doc);
```

## Schritt 5: Hängen Sie eine Datei an und geben Sie ihr Symbol an

Geben Sie die anzuhängende Datei an und geben Sie ein Symbol dafür an.

```csharp
string dataDir = "Your Document Directory";

using (var stream = File.OpenRead(dataDir + "icon.jpg"))
{
    AttachedFile attachedFile = new AttachedFile(doc, dataDir + "attachment.txt", stream, ImageFormat.Jpeg);
    outlineElem.AppendChildLast(attachedFile);
}
```

## Schritt 6: Erstellen Sie die Dokumentstruktur

Fügen Sie die `OutlineElement` zum `Outline`und die `Outline` zum `Page`.

```csharp
outline.AppendChildLast(outlineElem);
page.AppendChildLast(outline);
```

## Schritt 7: Fügen Sie die Seite zum Dokument hinzu

Fügen Sie die Seite abschließend in Ihr OneNote-Dokument ein.

```csharp
doc.AppendChildLast(page);
```

## Schritt 8: Speichern Sie das Dokument

Exportieren Sie Ihr aktualisiertes Dokument mit dem Dateianhang und dem Symbol.

```csharp
dataDir = dataDir + "AttachFileAndSetIcon_out.one";
doc.Save(dataDir);
```

## Abschluss

Mit den in dieser Anleitung beschriebenen Schritten können Sie mit Aspose.Note für .NET mühelos Dateien anhängen und benutzerdefinierte Symbole in OneNote-Dokumenten festlegen. Diese Funktionalität verbessert die Dokumentenorganisation und das Benutzererlebnis erheblich und macht Ihre Anwendungen robuster und funktionsreicher.

## Häufig gestellte Fragen

### Können einer einzelnen Notiz mehrere Dateien angehängt werden?
Ja, Sie können mehrere Dateien anhängen, indem Sie den Anhängevorgang für jede Datei wiederholen.

### Welche Bildformate werden für Symbole unterstützt?
Aspose.Note unterstützt die Formate JPEG, PNG, BMP und GIF für Anhangssymbole.

### Ist es möglich, Dateien dynamisch von externen URLs anzuhängen?
Sie können Dateien mit .NET-Bibliotheken herunterladen, wie `HttpClient` und hängen Sie sie dann mit Aspose.Note an.

### Gibt es Beschränkungen hinsichtlich der Dateigröße von Anhängen?
Es gibt keine explizite Größenbeschränkung durch Aspose.Note, aber stellen Sie sicher, dass Ihre Systemressourcen große Dateien verarbeiten können.

### Kann die Größe von Symbolen vor dem Festlegen geändert werden?
Ja, Sie können das Symbolbild mit .NET manipulieren. `System.Drawing` Bibliothek, bevor Sie sie anhängen.

Weitere Hilfe finden Sie im [Dokumentation](https://reference.aspose.com/words/net/) oder wenden Sie sich an [Aspose-Unterstützung](https://forum.aspose.com/c/words/8).