---
"description": "Nutzen Sie das Potenzial Ihrer PDF-Dokumente, indem Sie lernen, wie Sie mit Aspose.PDF für .NET markierten Text extrahieren. Diese umfassende Anleitung führt Sie durch jeden Schritt, von der Einrichtung bis zur Implementierung."
"linktitle": "Extrahieren Sie hervorgehobenen Text aus PDFs mit Aspose.PDF für .NET"
"second_title": "Aspose.PDF für .NET API-Referenz"
"title": "Extrahieren Sie hervorgehobenen Text aus PDFs mit Aspose.PDF für .NET"
"url": "/de/pdf/net/mastering-annotations/extract-highlighted-text-from-pdf/"
"weight": 60
---

## Einführung

Beim Arbeiten mit PDF-Dateien kann das Extrahieren von markiertem Text für die Datenanalyse, Inhaltsprüfung oder das Organisieren von Notizen unerlässlich sein. Wenn Sie Aspose.PDF für .NET verwenden, haben Sie Glück. Dieses Tutorial bietet klare, schrittweise Anweisungen zum effizienten Extrahieren von markiertem Text aus einem PDF-Dokument.

## Voraussetzungen

Stellen Sie vor dem Start sicher, dass Folgendes vorhanden ist:

- Aspose.PDF für .NET-Bibliothek: Laden Sie die Bibliothek von der [Release-Seite](https://releases.aspose.com/pdf/net/).
- Entwicklungsumgebung: Eine Arbeitsumgebung wie Visual Studio.
- Grundkenntnisse in C#: Kenntnisse in C# und objektorientierter Programmierung sind erforderlich.
- Aspose-Lizenz: Sie können zwar mit einer kostenlosen Testversion beginnen, aber [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) oder eine Volllizenz von [Hier](https://purchase.aspose.com/buy) bietet uneingeschränkten Zugriff.

## Importieren Sie die erforderlichen Namespaces

Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr C#-Projekt:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die für die Handhabung von PDF-Dokumenten und Anmerkungen erforderlich sind.

## Schritt 1: Richten Sie Ihr Projektverzeichnis ein

Geben Sie das Verzeichnis an, in dem sich Ihre PDF-Datei befindet:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Stellen Sie sicher, dass Sie den Pfad durch das tatsächliche Verzeichnis Ihrer PDF-Datei ersetzen.

## Schritt 2: Laden Sie das PDF-Dokument

Laden Sie das PDF-Dokument mit dem folgenden Code:

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

Stellen Sie sicher, dass die angegebene Datei im angegebenen Verzeichnis vorhanden ist.

## Schritt 3: Zugriff auf Anmerkungen auf der Seite

Um auf die Anmerkungen zuzugreifen, durchlaufen Sie die Anmerkungen auf der gewünschten Seite (in diesem Fall der ersten Seite):

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
    if (annotation is TextMarkupAnnotation)
    {
        TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

Dieser Code filtert nach `TextMarkupAnnotation` Typen, die Highlights darstellen.

## Schritt 4: Extrahieren Sie den markierten Text

Extrahieren und zeigen Sie nun den Text aus den hervorgehobenen Anmerkungen an:

```csharp
        TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
        foreach (TextFragment tf in collection)
        {
            Console.WriteLine(tf.Text);
        }
    }
}
```

Dadurch werden alle markierten Textfragmente abgerufen, die mit der Hervorhebung verknüpft sind, und auf der Konsole gedruckt.

## Abschluss

Das Extrahieren von markiertem Text aus einer PDF-Datei mit Aspose.PDF für .NET ist unkompliziert und kann Ihren Dokumentenverarbeitungsprozess erheblich verbessern. Mit den oben beschriebenen Schritten können Sie markierten Text effizient für verschiedene Anwendungen, z. B. zur Berichterstellung oder Datenanalyse, erfassen.

## Häufig gestellte Fragen

### Kann ich andere Arten von Anmerkungen extrahieren?
Ja, passen Sie einfach die `if` Bedingung, um verschiedene Anmerkungstypen einzuschließen, wie `TextAnnotation` oder `StampAnnotation`.

### Wie kann ich markierten Text aus allen PDF-Seiten extrahieren?
Sie können alle Seiten durchlaufen, indem Sie Folgendes verwenden:
```csharp
for (int i = 1; i <= doc.Pages.Count; i++)
{
    foreach (Annotation annotation in doc.Pages[i].Annotations) { ... }
}
```

### Ist für Aspose.PDF für .NET eine Lizenz erforderlich?
Eine kostenlose Testversion ist verfügbar, aber überlegen Sie, [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) oder eine Volllizenz für vollständigen Zugriff.

### Kann ich den extrahierten Text in einer Datei speichern?
Absolut! Sie können den Code ändern, um extrahierten Text in eine Textdatei zu schreiben.

### Unterstützt Aspose.PDF andere Plattformen?
Ja, Aspose.PDF unterstützt auch Java und andere Plattformen und bietet ähnliche Funktionen.