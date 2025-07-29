---
"description": "Erfahren Sie, wie Sie E-Mail-Anhänge in C# mit Aspose.Email für .NET extrahieren. Schritt-für-Schritt-Anleitung mit Beispielen für PDFs, Bilder und mehr."
"linktitle": "E-Mail-Anhänge in C# extrahieren – Aspose.Email-Tutorial"
"second_title": "Aspose.Email .NET E-Mail-Verarbeitungs-API"
"title": "E-Mail-Anhänge in C# extrahieren – Aspose.Email-Tutorial"
"url": "/de/email/net/handling-email-attachments/extract-email-attachments-in-csharp/"
"weight": 14
---

## Einführung

Haben Sie schon einmal E-Mail-Anhänge manuell einzeln heruntergeladen? Das ist nicht nur zeitaufwändig, sondern auch fehleranfällig. Glücklicherweise bietet Aspose.Email für .NET eine leistungsstarke und effiziente Möglichkeit, diese Aufgabe zu automatisieren. Egal, ob Sie mit PDFs, Bildern oder anderen Dateitypen arbeiten – mit C# können Sie Anhänge mühelos extrahieren.

In diesem Leitfaden führen wir Sie durch ein komplettes Tutorial, angefangen von den Voraussetzungen bis hin zu einem voll funktionsfähigen Beispiel. Sind Sie bereit, stundenlange manuelle Arbeit zu sparen? Dann legen wir los!

## Voraussetzungen

Bevor Sie mit der Codierung beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio ist auf Ihrem Computer installiert.
- Aspose.Email für .NET-Bibliothek. Sie können [Laden Sie es hier herunter](https://releases.aspose.com/email/net/) oder installieren Sie es über NuGet.
- Ein gültiges E-Mail-Konto (IMAP/POP3 wird unterstützt).
- Grundlegende Kenntnisse der C#-Programmierung.

Wenn Sie neu bei Aspose.Email sind, sollten Sie eine [kostenlose Testversion](https://releases.aspose.com/) oder ein [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) um alle Funktionen freizuschalten.

## Pakete importieren

Bevor Sie mit dem Code beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces importiert haben. Fügen Sie oben in Ihrer C#-Datei Folgendes hinzu:

```csharp
using Aspose.Email;
using Aspose.Email.Clients.Imap;
using Aspose.Email.Clients.Pop3;
```

Lassen Sie uns den Prozess in verständliche Schritte unterteilen. Befolgen Sie jeden Schritt sorgfältig, um eine reibungslose Ausführung zu gewährleisten.


## Schritt 1: Richten Sie Ihren IMAP-Client ein

Der erste Schritt besteht darin, über das IMAP-Protokoll eine Verbindung zu Ihrem E-Mail-Server herzustellen. Mit IMAP können wir auf E-Mail-Nachrichten vom Server zugreifen und diese abrufen.

```csharp
ImapClient client = new ImapClient("imap.example.com", "username", "password");
client.SelectFolder(ImapFolderInfo.InBox);
```

- Ersetzen `imap.example.com` mit der IMAP-Serveradresse Ihres E-Mail-Anbieters (z. B. `imap.gmail.com` für Gmail).
- Verwenden Sie Ihre aktuelle E-Mail-Adresse `username` Und `password`.
- `SelectFolder(ImapFolderInfo.InBox)` gibt an, dass wir mit dem Posteingang arbeiten möchten.


## Schritt 2: E-Mails aus dem Posteingang abrufen

Sobald die Verbindung hergestellt ist, müssen Sie E-Mail-Nachrichten aus dem Posteingang abrufen. Aspose.Email bietet eine einfache Methode zum Auflisten aller Nachrichten.

```csharp
ImapMessageInfoCollection messages = client.ListMessages();
```

- `ListMessages()` Ruft Metadaten für alle E-Mails im Posteingang ab.
- Der `ImapMessageInfoCollection` Das Objekt enthält Details wie Absender, Betreff und eindeutige IDs.


## Schritt 3: Jede E-Mail-Nachricht abrufen

Um auf den Inhalt und die Anhänge zuzugreifen, müssen Sie jede E-Mail anhand ihrer eindeutigen ID abrufen.


```csharp
foreach (ImapMessageInfo messageInfo in messages)
{
    MailMessage message = client.FetchMessage(messageInfo.UniqueId);
}
```

- Der `foreach` Die Schleife durchläuft alle Nachrichten.
- `FetchMessage()` ruft den tatsächlichen E-Mail-Inhalt für eine bestimmte Nachrichten-ID ab.


## Schritt 4: Anhänge durchschleifen

Nachdem Sie nun den E-Mail-Inhalt haben, ist es Zeit, Anhänge zu extrahieren. Jeder `MailMessage` Objekt enthält eine Sammlung von Anhängen.

```csharp
foreach (Attachment attachment in message.Attachments)
{
    Console.WriteLine($"Attachment Name: {attachment.Name}");
}
```

- Der `Attachments` Die Eigenschaft listet alle Anhänge in der E-Mail auf.
- Verwenden `attachment.Name` um den Dateinamen zu erhalten.


## Schritt 5: Anhänge auf der Festplatte speichern

Speichern Sie die Anhänge abschließend auf Ihrem lokalen Computer. Sie können die Dateien nach Typ, Größe oder anderen Kriterien filtern.

```csharp
foreach (Attachment attachment in message.Attachments)
{
    string filePath = Path.Combine("C:\\Attachments", attachment.Name);
    using (var stream = new FileStream(filePath, FileMode.Create))
    {
        attachment.Save(stream);
    }
}
```

- Ersetzen `"C:\\Attachments"` mit Ihrem gewünschten Ordnerpfad.
- Der `attachment.Save()` Die Methode schreibt die Datei auf die Festplatte.


## Schritt 6: Anhänge nach Typ verarbeiten

Wenn Sie Anhänge je nach Typ unterschiedlich behandeln müssen (z. B. PDF oder JPEG), macht Aspose.Email dies einfach.

```csharp
if (attachment.ContentType.MediaType == "application/pdf")
{
    Console.WriteLine("Processing PDF...");
}
else if (attachment.ContentType.MediaType == "image/jpeg")
{
    Console.WriteLine("Processing JPEG...");
}
```

- `ContentType.MediaType` identifiziert den Dateityp (z. B. `application/pdf` für PDFs, `image/jpeg` für Bilder).
- Fügen Sie bei Bedarf benutzerdefinierte Logik für verschiedene Dateitypen hinzu.


## Abschluss

Und da haben Sie es! Das Extrahieren von Anhängen aus E-Mails ist keine mühsame Aufgabe mehr. Mit Aspose.Email für .NET automatisieren Sie diesen Prozess mit nur wenigen Codezeilen. Von der Einrichtung des IMAP-Clients bis zum lokalen Speichern von Anhängen – diese Anleitung deckt alles ab, was Sie für den Einstieg benötigen. 

Warum also warten? [Laden Sie Aspose.Email herunter](https://releases.aspose.com/email/net/) und beginnen Sie noch heute mit der Optimierung Ihrer E-Mail-Workflows!


## Häufig gestellte Fragen

### Kann ich diesen Code mit Gmail oder Outlook verwenden?
Ja! Ersetzen `imap.example.com` mit Gmails (`imap.gmail.com`) oder Outlooks (`outlook.office365.com`) IMAP-Serveradresse.

### Ist die Nutzung von Aspose.Email kostenlos?
Aspose.Email benötigt eine Lizenz für alle Funktionen. Sie können eine [kostenlose Testversion](https://releases.aspose.com/) oder ein [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).

### Wie kann ich die Passwortsicherheit handhaben?
Erwägen Sie die Verwendung von Umgebungsvariablen oder einer sicheren Speicherung von Anmeldeinformationen anstelle der Festcodierung von Kennwörtern.

### Kann ich Anhänge aus gesendeten Elementen extrahieren?
Ja, verwenden Sie einfach `SelectFolder(ImapFolderInfo.Sent)` anstelle des Posteingangs.

### Unterstützt Aspose.Email POP3?
Absolut! Neben IMAP unterstützt es auch POP3 und SMTP.