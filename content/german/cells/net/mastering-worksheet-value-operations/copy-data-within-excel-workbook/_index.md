---
"description": "Erfahren Sie, wie Sie mit Aspose.Cells für .NET effizient Daten innerhalb einer Excel-Arbeitsmappe kopieren. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um Tabellenblätter einfach zu duplizieren, Daten zu übertragen und Excel-Dateien mühelos zu verwalten."
"linktitle": "Kopieren Sie Daten innerhalb einer Excel-Arbeitsmappe mit Aspose.Cells für .NET"
"second_title": "Aspose.Cells .NET Excel-Verarbeitungs-API"
"title": "Kopieren Sie Daten innerhalb einer Excel-Arbeitsmappe mit Aspose.Cells für .NET"
"url": "/de/cells/net/mastering-worksheet-value-operations/copy-data-within-excel-workbook/"
"weight": 12
---

## Einführung

In dieser ausführlichen Anleitung zeigen wir Ihnen, wie Sie Daten innerhalb derselben Arbeitsmappe mit Aspose.Cells für .NET kopieren. Folgen Sie den unten aufgeführten Schritt-für-Schritt-Anweisungen, um zu erfahren, wie Sie Tabellenblätter programmgesteuert duplizieren und dabei Inhalt und Formatierung beibehalten.

## Voraussetzungen für das Kopieren von Daten in Excel mit Aspose.Cells

Bevor wir mit dem Codierungsprozess beginnen, stellen wir sicher, dass alles bereit ist:

1. Aspose.Cells für .NET-Bibliothek: Sie müssen die Aspose.Cells für .NET-Bibliothek installiert haben. Sie können die neueste Version von der [Downloadseite für Aspose.Cells für .NET](https://releases.aspose.com/cells/net/).
2. Entwicklungsumgebung: Zum Schreiben und Ausführen Ihres Codes ist eine .NET-kompatible IDE wie Visual Studio erforderlich.
3. Aspose-Lizenz: Sie können entweder eine kostenlose Testversion oder eine gekaufte Lizenz verwenden. Weitere Informationen finden Sie unter [Hier](https://purchase.aspose.com/temporary-license/).

Sobald die Voraussetzungen erfüllt sind, können Sie mit der Arbeit mit der Bibliothek beginnen.

## Importieren der erforderlichen Pakete

Zunächst müssen Sie die entsprechenden Namespaces aus Aspose.Cells importieren. Dadurch können Sie mit Excel-Dateien unter Verwendung der von Aspose.Cells bereitgestellten Klassen und Methoden arbeiten.

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

Diese Namespaces geben Ihnen Zugriff auf die `Workbook` Klasse (für die Arbeit mit Excel-Dateien) und `WorksheetCollection` (für den Zugriff auf mehrere Blätter innerhalb einer Arbeitsmappe).

## Schritt 1: Dateipfade für Arbeitsmappe initialisieren

Um Ihren Code übersichtlich zu halten, müssen Sie die Dateipfade definieren, in denen sich Ihre Arbeitsmappe befindet und wo Sie die geänderte Datei speichern möchten. So können Sie die Pfade angeben:

```csharp
// Definieren Sie den Verzeichnispfad, in dem sich die Excel-Datei befindet.
string dataDir = "Your Directory Path";

// Definieren Sie den vollständigen Pfad zur Eingabearbeitsmappe.
string inputPath = dataDir + "book1.xls";
```

Ersetzen `"Your Directory Path"` durch den tatsächlichen Pfad zu Ihrem Verzeichnis, das die Arbeitsmappe enthält. Dadurch wird sichergestellt, dass der Code flexibel ist und Sie Pfade effektiv verwalten können.

## Schritt 2: Öffnen Sie die Arbeitsmappe, um auf die Daten zuzugreifen

Nachdem die Dateipfade festgelegt sind, besteht der nächste Schritt darin, die Excel-Arbeitsmappe in ein `Workbook` Objekt. Dadurch können Sie auf dessen Inhalt zugreifen und ihn bearbeiten.

```csharp
// Laden Sie die Excel-Datei in das Arbeitsmappenobjekt.
Workbook wb = new Workbook(inputPath);
```

Mit dieser Zeile haben Sie erfolgreich geladen `book1.xls` in die `wb` Objekt, wodurch seine Daten zugänglich gemacht werden.

## Schritt 3: Zugriff auf die Arbeitsblattsammlung

Sobald die Arbeitsmappe geladen ist, können Sie auf die darin enthaltenen Blätter zugreifen. Aspose.Cells bietet die `Worksheets` Sammlung, die Ihnen die Interaktion mit jedem Arbeitsblatt in der Arbeitsmappe ermöglicht.

```csharp
// Rufen Sie die Arbeitsblattsammlung aus der Arbeitsmappe ab.
WorksheetCollection sheets = wb.Worksheets;
```

Der `sheets` Objekt gibt Ihnen jetzt Zugriff auf alle Arbeitsblätter innerhalb `book1.xls`, und Sie können verschiedene Vorgänge damit ausführen, einschließlich des Kopierens von Daten von einem Blatt in ein anderes.

## Schritt 4: Daten von einem Blatt in ein anderes kopieren

Um Daten von einem Arbeitsblatt in ein anderes innerhalb derselben Arbeitsmappe zu kopieren, bietet Aspose.Cells eine benutzerfreundliche Methode namens `AddCopy`. Diese Methode erstellt ein Duplikat des angegebenen Arbeitsblatts und hängt es an die Arbeitsmappe an.

```csharp
// Kopieren Sie Daten aus „Sheet1“ in ein neues Blatt innerhalb der Arbeitsmappe.
sheets.AddCopy("Sheet1");
```

In diesem Beispiel kopieren wir Daten aus "Sheet1" in ein neues Sheet. Die `AddCopy` Die Methode dupliziert das gesamte Blatt und behält dabei alle Inhalte bei, einschließlich Formeln, Formatierungen und Werten.

## Schritt 5: Speichern der geänderten Arbeitsmappe

Nach dem Kopieren der Daten können Sie die geänderte Arbeitsmappe unter einem neuen Namen oder an einem neuen Speicherort speichern. Dies geschieht durch den Aufruf des `Save` Methode auf der `Workbook` Objekt.

```csharp
// Speichern Sie die geänderte Arbeitsmappe unter einem neuen Namen.
wb.Save(dataDir + "book1_copy.xls");
```

Dadurch wird die Arbeitsmappe mit dem kopierten Blatt gespeichert als `book1_copy.xls` im angegebenen Verzeichnis. Sie können den Dateinamen und den Pfad nach Ihren Wünschen ändern.

## Abschluss

Das Kopieren von Daten innerhalb einer Excel-Arbeitsmappe mit Aspose.Cells für .NET ist eine einfache Aufgabe. Diese Anleitung beschreibt die erforderlichen Schritte für eine effiziente Durchführung. Ob Sie ganze Tabellenblätter oder bestimmte Datenbereiche duplizieren, Aspose.Cells bietet eine robuste und flexible API, die die Excel-Automatisierung einfach und effektiv macht.

## Häufig gestellte Fragen

### Kann ich mehrere Blätter gleichzeitig kopieren?

Aspose.Cells unterstützt nicht das Kopieren mehrerer Blätter in einem einzigen Aufruf. Sie können jedoch die zu kopierenden Blätter in einer Schleife durchlaufen und einzeln kopieren.

### Wie kann ich das kopierte Blatt umbenennen?

Nachdem Sie das Blatt kopiert haben, können Sie es wie folgt umbenennen:

```csharp
sheets[sheets.Count - 1].Name = "NewSheetName";
```

### Ist Aspose.Cells mit .NET Core kompatibel?

Ja, Aspose.Cells ist vollständig mit .NET Framework- und .NET Core-Umgebungen kompatibel.

### Wie handhabt Aspose.Cells die Formatierung während des Kopierens?

Der `AddCopy` Die Methode behält beim Kopieren von Blättern sämtliche Inhalte und Formatierungen bei und stellt sicher, dass die kopierten Daten mit dem Original identisch aussehen.

### Kann ich ein Blatt in eine andere Arbeitsmappe kopieren?

Ja, Sie können ein Blatt in eine andere Arbeitsmappe kopieren, indem Sie das `Copy` -Methode mit einem Verweis auf die Zielarbeitsmappe.

```csharp
sheets.Add().Copy(wb.Worksheets["Sheet1"]);
```