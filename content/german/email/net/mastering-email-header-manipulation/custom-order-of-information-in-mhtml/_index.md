---
"description": "Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Email für .NET eine benutzerdefinierte Informationsreihenfolge in MHTML definieren."
"linktitle": "Benutzerdefinierte Reihenfolge von Informationen in MHTML mit Aspose.Email"
"second_title": "Aspose.Email .NET E-Mail-Verarbeitungs-API"
"title": "Benutzerdefinierte Reihenfolge von Informationen in MHTML mit Aspose.Email"
"url": "/de/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## Einführung

Die Erstellung umfangreicher E-Mail-Formate kann die Kommunikation erheblich verbessern, insbesondere beim Exportieren von E-Mails in verschiedene Dateiformate wie MHTML. Aspose.Email für .NET bietet Entwicklern ein leistungsstarkes Toolkit zur Bearbeitung von E-Mails, darunter die Definition einer benutzerdefinierten Reihenfolge für die Anzeige von Informationen beim Export in MHTML. In dieser Anleitung erklären wir die dafür erforderlichen Schritte und machen sie sowohl für erfahrene Entwickler als auch für Einsteiger leicht nachvollziehbar. Legen wir also gleich los!

## Voraussetzungen

Bevor Sie mit der Definition der benutzerdefinierten Reihenfolge der Informationen in MHTML beginnen, müssen Sie einige Voraussetzungen von Ihrer Liste abhaken:

1. .NET-Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine .NET-Entwicklungsumgebung eingerichtet haben. Sie können Visual Studio, Visual Studio Code oder eine andere kompatible IDE verwenden.

2. Aspose.Email-Bibliothek: Sie müssen die Aspose.Email für .NET-Bibliothek installiert haben. Sie können die neueste Version von der herunterladen [Aspose-Veröffentlichungsseite](https://releases.aspose.com/email/net/).

3. Grundlegende Kenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie den Code besser.

4. Beispiel-E-Mail-Datei: Sie benötigen ein Beispiel `.eml` Datei (zum Beispiel `Attachments.eml`) zu Testzwecken.

Sobald Sie diese Voraussetzungen erfüllen, können Sie dem Tutorial folgen!

## Pakete importieren

Um mit Ihrem Code zu beginnen, müssen Sie die erforderlichen Namespaces aus der Aspose.Email-Bibliothek importieren. Dies ist wichtig, um auf alle Klassen und Methoden zugreifen zu können, die für die Bearbeitung von E-Mail-Dateien erforderlich sind.

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

Fügen Sie diese am Anfang Ihrer C#-Datei ein. Jetzt können Sie mit dem Programmieren beginnen!

Nachdem Sie nun alles eingerichtet haben, unterteilen wir das Tutorial in überschaubare Schritte.

## Schritt 1: Legen Sie Ihr Datenverzeichnis fest

Als Erstes müssen Sie ein Verzeichnis einrichten, in dem Ihre E-Mail-Dateien gespeichert werden. Dies kann ein beliebiger Pfad auf Ihrem lokalen Computer sein.

```csharp
string dataDir = "Your Data Directory";
```

Ersetzen `"Your Data Directory"` mit dem tatsächlichen Pfad, wo Ihr `.eml` Datei befindet. Wenn Ihre Datei beispielsweise in `C:\Emails`würden Sie schreiben:

```csharp
string dataDir = @"C:\Emails\";
```

## Schritt 2: Laden Sie die E-Mail-Nachricht

Als nächstes müssen Sie die `.eml` Datei in eine `MailMessage` Objekt. Dadurch können Sie den Inhalt und die Metadaten der E-Mail bearbeiten.

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

Stellen Sie sicher, dass der Dateiname mit dem im angegebenen Verzeichnis übereinstimmt. Wenn Ihre Datei einen anderen Namen hat, aktualisieren Sie den Dateinamen entsprechend.

## Schritt 3: MHTML-Speicheroptionen einrichten

Nachdem Sie Ihre E-Mail geladen haben, können Sie festlegen, wie Sie sie als MHTML speichern möchten. Sie können mit den Standardoptionen beginnen.

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

Diese Zeile initialisiert die MHTML-Speicheroptionen und bereitet die Bühne für die spätere Anpassung der Kopfzeilen vor.

## Schritt 4: MHTML mit Standardreihenfolge speichern

Speichern wir die E-Mail im MHTML-Format und verwenden dabei die Standardreihenfolge. So erhalten Sie eine Vergleichsbasis nach der Anpassung.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

Führen Sie diese Zeile aus und überprüfen Sie das angegebene Verzeichnis. Sie sollten nun eine neue MHTML-Datei mit dem Namen `CustomOrderOfInformationInMHTML_1.mhtml`. Öffnen Sie es, um zu sehen, wie die Informationen standardmäßig angezeigt werden.

## Schritt 5: Kopfzeilenreihenfolge anpassen

Jetzt kommt der spannende Teil! Sie können festlegen, welche Header in der MHTML-Ausgabe enthalten sein sollen und in welcher Reihenfolge. Wir beginnen mit einigen gängigen Headern.

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

Durch das Hinzufügen dieser Kopfzeilen teilen Sie Aspose mit, wie die E-Mail angezeigt werden soll.

## Schritt 6: MHTML mit benutzerdefinierter Reihenfolge speichern

Nach der Anpassung der Header müssen Sie die E-Mail erneut als MHTML speichern, um zu sehen, wie sich die neue Reihenfolge auf die Ausgabe auswirkt.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

Führen Sie diesen Code aus und öffnen Sie ihn `CustomOrderOfInformationInMHTML_2.mhtml`Vergleichen Sie es mit dem ersten, um zu sehen, wie sich die Informationen aufgrund Ihrer Kopfreihenfolge geändert haben.

## Schritt 7: Löschen und Hinzufügen einer neuen Kopfzeilenreihenfolge

Was ist, wenn Sie eine ganz andere Reihenfolge wünschen? Sie können neu beginnen, indem Sie die vorhandenen Kopfzeileneinstellungen löschen.

```csharp
opt.RenderingHeaders.Clear();
```

Nun ist es an der Zeit, eine neue Reihenfolge für die Header festzulegen. Wenn Sie beispielsweise Anhänge priorisieren und Empfänger kopieren möchten:

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## Schritt 8: MHTML mit neuer benutzerdefinierter Reihenfolge speichern

Speichern Sie die E-Mail abschließend ein letztes Mal mit den neuen Header-Einstellungen.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

Nachdem Sie diese Zeile ausgeführt haben, öffnen Sie `CustomOrderOfInformationInMHTML_3.mhtml` und prüfen Sie, wie die Informationen basierend auf Ihrer neuen Anpassung dargestellt werden.

## Abschluss

Und hier ist sie – eine einfache Anleitung zum Definieren einer benutzerdefinierten Informationsreihenfolge in MHTML mit Aspose.Email für .NET. Mit diesen Schritten können Sie die Darstellung Ihrer E-Mails im MHTML-Format steuern und sicherstellen, dass die wichtigsten Informationen Ihren Anforderungen entsprechend präsentiert werden. 

## Häufig gestellte Fragen

### Was ist MHTML?
MHTML steht für „MIME HTML“, ein Archivformat für Webseiten, das HTML und andere Ressourcen wie Bilder kombiniert.

### Kann ich Aspose.Email kostenlos nutzen?
Ja, Aspose bietet Entwicklern eine kostenlose Testversion an. Sie finden sie [Hier](https://releases.aspose.com/).

### Was ist, wenn bei der Verwendung von Aspose.Email Probleme auftreten?
Unterstützung von der Community erhalten Sie über die [Aspose-Forum](https://forum.aspose.com/c/email/12/).

### Ist eine temporäre Lizenz für Aspose.Email verfügbar?
Ja, Sie können eine vorläufige Lizenz beantragen [Hier](https://purchase.aspose.com/temporary-license/).

### Wo kann ich Aspose.Email kaufen?
Sie können die Bibliothek hier erwerben [Link](https://purchase.aspose.com/buy).