---
"description": "Erfahren Sie, wie Sie den Status von Terminteilnehmern mit C# und Aspose.Email für .NET verwalten. Schritt-für-Schritt-Anleitung mit Quellcode."
"linktitle": "Teilnehmerstatus für Terminteilnehmer mit C# festlegen"
"second_title": "Aspose.Email .NET E-Mail-Verarbeitungs-API"
"title": "Teilnehmerstatus für Terminteilnehmer mit C# festlegen"
"url": "/de/email/net/handling-email-events-and-calendar/setting-participant-status-for-appointment-attendees/"
"weight": 16
---

## Einführung

Aspose.Email für .NET ist eine robuste und funktionsreiche Bibliothek zur Optimierung der E-Mail-Verarbeitung in .NET-Anwendungen. Diese Anleitung führt Sie Schritt für Schritt durch das Erstellen und Verwalten von Terminen, das Hinzufügen von Teilnehmern und das Festlegen von Teilnehmerstatus und gewährleistet so eine effiziente Integration in Ihre .NET-Projekte.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine funktionierende Installation von Visual Studio oder einer kompatiblen C#-IDE.
- Die neueste Version der Aspose.Email-Bibliothek für .NET.
- Grundkenntnisse in C# und objektorientierter Programmierung.

Informationen zur Bibliotheksinstallation finden Sie im [Download-Seite](https://releases.aspose.com/).

## Erforderliche Namespaces importieren

Um zu beginnen, schließen Sie die erforderlichen Namespaces ein, um auf die Funktionen zum Verwalten von Terminen und E-Mail-Komponenten zuzugreifen.

```csharp
using Aspose.Email;
using Aspose.Email.Calendar;
```

## Erstellen einer Termininstanz

Termine in Aspose.Email stellen geplante Ereignisse wie Besprechungen oder Aufgaben dar. So erstellen Sie einen Termin:

```csharp
var appointment = new Appointment(
    "Conference Room 101", 
    DateTime.Now, 
    DateTime.Now.AddHours(1), 
    new MailAddress("organizer@example.com"),
    new MailAddressCollection { "attendee1@example.com", "attendee2@example.com" }
);
```

- Ort: Gibt an, wo der Termin stattfinden wird.
- Startzeit und Endzeit: Definieren Sie die Dauer des Termins.
- Organisator und Teilnehmer: Definieren Sie Teilnehmer und ihre Rollen.

## Teilnehmer zu Terminen hinzufügen

Mit Aspose.Email können Sie Teilnehmer mit ihren E-Mail-Adressen und Teilnahmestatus programmgesteuert verwalten.

```csharp
appointment.Attendees.Add(new MailAddress("john@example.com", "John Doe"));
appointment.Attendees.Add(new MailAddress("jane@example.com", "Jane Smith"));
```

## Teilnehmerstatus verwalten

Der `ParticipantStatus` Mithilfe der Eigenschaft lässt sich feststellen, ob ein Teilnehmer eine Termineinladung angenommen, abgelehnt oder vorläufig angenommen hat. Verwenden Sie die folgenden Enumerationswerte:

- Akzeptiert
- Abgelehnt
- Vorläufig

Beispiel:

```csharp
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## Termine als Besprechungseinladungen versenden

Sobald der Termin vorbereitet ist, können Sie ihn als Einladungs-E-Mail versenden:

```csharp
var msg = new MailMessage();
msg.From = "organizer@example.com";
msg.To = new MailAddressCollection { "john@example.com", "jane@example.com" };
msg.Subject = "Team Meeting";
msg.AlternateViews.Add(appointment.RequestApointment());

var client = new SmtpClient("smtp.example.com", 587, "username", "password");
client.Send(msg);
```

## Abschluss

Aspose.Email für .NET vereinfacht die Terminverwaltung in .NET-Anwendungen und bietet Tools zum effizienten Erstellen, Anpassen und Verwalten geplanter Ereignisse. Mit der intuitiven API optimieren Sie Kommunikationsabläufe und sorgen für eine nahtlose Integration.

## Häufig gestellte Fragen

### Was ist Aspose.Email für .NET?

Aspose.Email für .NET ist eine umfassende Bibliothek zur Handhabung von E-Mail-Nachrichten, Terminen und anderen verwandten Funktionen in .NET-Anwendungen.

### Kann ich Termineigenschaften anpassen?

Ja, Eigenschaften wie Ort, Startzeit und Teilnehmer können vollständig angepasst werden.

### Unterstützt die Bibliothek wiederkehrende Termine?

Ja, Aspose.Email für .NET unterstützt wiederkehrende Termine mithilfe seiner API für Wiederholungsmuster.

### Wo erhalte ich Support für Aspose.Email für .NET?

Sie können auf ausführliche Dokumentation und Community-Support zugreifen unter [Support-Seite](https://forum.aspose.com/c/email/11).