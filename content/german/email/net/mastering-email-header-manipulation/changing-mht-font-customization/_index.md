---
"description": "Erfahren Sie, wie Sie Schriftarten während der MHT-Konvertierung mit Aspose.Email für .NET ändern. Folgen Sie dieser Schritt-für-Schritt-Anleitung für eine einfache Anpassung."
"linktitle": "Ändern der MHT-Schriftartanpassung mit C#"
"second_title": "Aspose.Email .NET E-Mail-Verarbeitungs-API"
"title": "Ändern der MHT-Schriftartanpassung mit C#"
"url": "/de/email/net/mastering-email-header-manipulation/changing-mht-font-customization/"
"weight": 11
---

## Einführung

In der Welt der Webkommunikation sind MHT-Dateien (MHTML) eine praktische Möglichkeit, Webinhalte inklusive Bildern, Links und Stilen zu speichern und zu teilen. Doch was passiert, wenn Sie diese MHT-Dateien durch Ändern der Schriftarten aufpeppen müssen? Dank Aspose.Email für .NET wird diese Aufgabe zum Kinderspiel. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Schriftartenänderung während der MHT-Konvertierung. Egal, ob Sie eine Anwendung zur E-Mail-Formatierung entwickeln oder einfach nur Dokumente für Ihr Unternehmen anpassen möchten – dieser Leitfaden vermittelt Ihnen das nötige Wissen.

## Voraussetzungen

Bevor Sie sich in den Code vertiefen, sollten Sie einige wichtige Dinge vorbereitet haben:

1. Visual Studio: Sie benötigen eine integrierte Entwicklungsumgebung (IDE), um an Ihrem C#-Projekt zu arbeiten.
2. Aspose.Email für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Bibliothek installiert haben. Sie können sie von der [Link](https://releases.aspose.com/email/net/).
3. .NET Framework: Ihr Projekt sollte mit .NET Framework kompatibel sein; normalerweise funktionieren .NET Core oder spätere Versionen gut.

Hast du alles vorbereitet? Super! Lass uns anfangen.

## Pakete importieren

Stellen Sie zunächst sicher, dass Ihr Projekt die erforderlichen Namespaces verwendet. Fügen Sie am Anfang Ihrer C#-Datei Folgendes ein:

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Tools;
```

Diese Pakete geben Ihnen Zugriff auf die Funktionen, die Sie zum Arbeiten mit MHT-Dateien und zum Ändern ihrer Inhalte benötigen.

Lassen Sie uns nun die Schritte zum Ändern von Schriftarten während der MHT-Konvertierung aufschlüsseln.

## Schritt 1: Laden Sie die MHT-Datei

Als erstes müssen Sie Ihre MHT-Datei in ein `MailMessage` Objekt. Hier können Sie auf den Inhalt zugreifen und ihn bearbeiten.

```csharp
MailMessage message = MailMessage.Load("input.mht", new MhtmlLoadOptions());
```

Erklärung: Hier, `"input.mht"` ist der Pfad zu Ihrer MHT-Datei. Die `MhtmlLoadOptions()` ermöglicht Ihnen die Konfiguration des Ladens der Datei, beispielsweise die unterschiedliche Behandlung von Anhängen oder verknüpften Ressourcen.

## Schritt 2: Durch alternative Ansichten iterieren

MHT-Dateien verfügen häufig über mehrere alternative Ansichten, insbesondere wenn sie HTML-Inhalte enthalten. Sie müssen diese Ansichten durchlaufen, um die Ansicht zu finden, die Sie ändern möchten.

```csharp
foreach (var alternateView in message.AlternateViews)
{
    if (alternateView.ContentType.MediaType == "text/html")
    {
        var htmlView = (AlternateView)alternateView;
        var linkedResources = htmlView.LinkedResources;
```

Erklärung: Sie überprüfen jedes `AlternateView` um zu sehen, ob es vom Typ HTML ist. Wenn ja, können Sie darauf zugreifen `LinkedResources`, wo normalerweise alle im HTML verknüpften Schriftarten gespeichert werden.

## Schritt 3: Schriftarten identifizieren und anpassen

Da Sie nun Zugriff auf die verknüpften Ressourcen haben, können Sie ermitteln, bei welchen Ressourcen es sich um Schriftarten handelt, und diese nach Bedarf anpassen.

```csharp
foreach (var linkedResource in linkedResources)
{
    if (linkedResource.ContentType.MediaType == "application/x-font-ttf")
    {
        linkedResource.ContentType.Name = "Arial";  // Zur gewünschten Schriftart wechseln
        linkedResource.TransferEncoding = TransferEncoding.Base64;  // Stellen Sie sicher, dass es richtig codiert ist
    }
}
```

Erklärung: Diese Schleife prüft, ob der Inhaltstyp der verknüpften Ressource eine TrueType-Schriftart ist. Wenn dies zutrifft, können Sie den Namen der Schriftart nach Belieben ändern (wie in diesem Beispiel "Arial"). Die `TransferEncoding` sollte auch eingestellt werden, um sicherzustellen, dass die Schriftdaten beim Speichern des Dokuments richtig codiert werden.

## Schritt 4: Speichern Sie die aktualisierte MHT-Datei

Nachdem Sie die Schriftarten angepasst haben, speichern Sie Ihre geänderte MHT-Datei. Achten Sie darauf, die richtigen Speicheroptionen zu verwenden, um die Integrität Ihrer Datei zu gewährleisten.

```csharp
message.Save("output.mht", SaveOptions.DefaultMhtml);
```

Erklärung: In dieser Codezeile `"output.mht"` ist der Name der Datei, in der Sie den aktualisierten Inhalt speichern möchten. Mit `SaveOptions.DefaultMhtml` stellt sicher, dass die neue Datei das MHT-Format beibehält.

## Abschluss

Das Ändern von Schriftarten in MHT-Dateien kann das Erscheinungsbild Ihrer Dokumente deutlich verbessern. Mit Aspose.Email für .NET können Sie MHT-Dateien einfach laden, ihren Inhalt ändern und die Änderungen mit nur wenigen Codezeilen speichern. Ob Sie an einem persönlichen Projekt oder einer größeren Anwendung arbeiten – die Beherrschung dieser Fähigkeiten kann die Präsentation von Informationen verbessern.

## Häufig gestellte Fragen

### Was ist das MHT-Format?
MHT ist ein Archivformat für Webseiten, das HTML-Dokumente, Bilder und andere Ressourcen in einer einzigen Datei speichert.

### Kann ich mit Aspose andere Aspekte von MHT-Dateien ändern?
Absolut! Mit Aspose.Email können Sie nahezu jeden Aspekt von MHT-Dateien ändern, einschließlich Anhängen, Kopfzeilen und mehr.

### Ist Aspose.Email für .NET kostenlos?
Aspose bietet eine kostenlose Testversion an, für die Vollversion ist jedoch eine Lizenz erforderlich. Sie erhalten eine temporäre Lizenz von [Hier](https://purchase.aspose.com/temporary-license/).

### Wo finde ich weitere Dokumentation zu Aspose.Email?
Ausführliche Dokumentationen und Beispiele finden Sie unter [Aspose Email-Dokumentationsseite](https://reference.aspose.com/email/net/).

### Was ist, wenn bei der Verwendung von Aspose Probleme auftreten?
Wenn Sie auf Probleme stoßen, können Sie sich an den Support wenden unter [Aspose-Supportforum](https://forum.aspose.com/c/email/12/).