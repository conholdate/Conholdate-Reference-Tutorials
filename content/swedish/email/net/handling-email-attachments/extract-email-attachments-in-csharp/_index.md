---
"description": "Lär dig hur du extraherar e-postbilagor i C# med Aspose.Email för .NET. Steg-för-steg-guide med exempel för PDF-filer, bilder och mer."
"linktitle": "Extrahera e-postbilagor i C# - Aspose.Email handledning"
"second_title": "Aspose.Email .NET e-postbehandlings-API"
"title": "Extrahera e-postbilagor i C# - Aspose.Email handledning"
"url": "/sv/email/net/handling-email-attachments/extract-email-attachments-in-csharp/"
"weight": 14
---

## Introduktion

Har du någonsin upptäckt att du manuellt laddar ner e-postbilagor, en efter en? Det är inte bara tidskrävande utan också felbenäget. Som tur är erbjuder Aspose.Email för .NET ett kraftfullt och effektivt sätt att automatisera denna uppgift. Oavsett om du arbetar med PDF-filer, bilder eller någon annan filtyp kan du enkelt extrahera bilagor med C#.

I den här guiden guidar vi dig genom en komplett handledning, från förkunskapskraven till ett fullt fungerande exempel. Redo att spara timmar av manuellt arbete? Nu kör vi!

## Förkunskapskrav

Innan du börjar koda, se till att du har följande:

- Visual Studio installerat på din dator.
- Aspose.Email för .NET-biblioteket. Du kan [ladda ner den här](https://releases.aspose.com/email/net/) eller installera det via NuGet.
- Ett giltigt e-postkonto (stöds IMAP/POP3).
- Grundläggande förståelse för C#-programmering.

Om du inte använder Aspose.Email tidigare, överväg att begära en [gratis provperiod](https://releases.aspose.com/) eller en [tillfällig licens](https://purchase.aspose.com/temporary-license/) för att låsa upp alla funktioner.

## Importera paket

Innan du går in i koden, se till att du har importerat de nödvändiga namnrymderna. Lägg till följande högst upp i din C#-fil:

```csharp
using Aspose.Email;
using Aspose.Email.Clients.Imap;
using Aspose.Email.Clients.Pop3;
```

Låt oss dela upp processen i lättförståeliga steg. Följ varje steg noggrant för att säkerställa ett smidigt genomförande.


## Steg 1: Konfigurera din IMAP-klient

Det första steget är att ansluta till din e-postserver med hjälp av IMAP-protokollet. IMAP låter oss komma åt och hämta e-postmeddelanden från servern.

```csharp
ImapClient client = new ImapClient("imap.example.com", "username", "password");
client.SelectFolder(ImapFolderInfo.InBox);
```

- Ersätta `imap.example.com` med din e-postleverantörs IMAP-serveradress (t.ex. `imap.gmail.com` för Gmail).
- Använd din faktiska e-postadress `username` och `password`.
- `SelectFolder(ImapFolderInfo.InBox)` anger att vi vill arbeta med inkorgen.


## Steg 2: Hämta e-postmeddelanden från inkorgen

När du är ansluten behöver du hämta e-postmeddelanden från inkorgen. Aspose.Email erbjuder en enkel metod för att lista alla meddelanden.

```csharp
ImapMessageInfoCollection messages = client.ListMessages();
```

- `ListMessages()` hämtar metadata för alla e-postmeddelanden i inkorgen.
- De `ImapMessageInfoCollection` Objektet innehåller detaljer som avsändare, ämne och unika ID:n.


## Steg 3: Hämta varje e-postmeddelande

För att komma åt innehållet och bilagorna måste du hämta varje e-postmeddelande med hjälp av dess unika ID.


```csharp
foreach (ImapMessageInfo messageInfo in messages)
{
    MailMessage message = client.FetchMessage(messageInfo.UniqueId);
}
```

- De `foreach` loopar itererar genom alla meddelanden.
- `FetchMessage()` hämtar det faktiska e-postinnehållet för ett givet meddelande-ID.


## Steg 4: Loopa igenom bilagor

Nu när du har e-postinnehållet är det dags att extrahera bilagor. `MailMessage` Objektet innehåller en samling bilagor.

```csharp
foreach (Attachment attachment in message.Attachments)
{
    Console.WriteLine($"Attachment Name: {attachment.Name}");
}
```

- De `Attachments` egenskapen listar alla bilagor i e-postmeddelandet.
- Använda `attachment.Name` för att få filnamnet.


## Steg 5: Spara bilagor till disk

Slutligen sparar du bilagorna på din lokala dator. Du kan filtrera filer efter typ, storlek eller andra kriterier.

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

- Ersätta `"C:\\Attachments"` med önskad mappsökväg.
- De `attachment.Save()` Metoden skriver filen till disk.


## Steg 6: Bearbeta bilagor efter typ

Om du behöver hantera bilagor olika baserat på deras typ (t.ex. PDF kontra JPEG) gör Aspose.Email det enkelt.

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

- `ContentType.MediaType` identifierar filtypen (t.ex. `application/pdf` för PDF-filer, `image/jpeg` för bilder).
- Lägg till anpassad logik för olika filtyper efter behov.


## Slutsats

Och där har du det! Att extrahera bilagor från e-postmeddelanden är inte längre en mödosam uppgift. Med Aspose.Email för .NET kan du automatisera processen med bara några få rader kod. Från att konfigurera IMAP-klienten till att spara bilagor lokalt, har den här guiden täckt allt du behöver för att komma igång. 

Så, varför vänta? [Ladda ner Aspose.Email](https://releases.aspose.com/email/net/) och börja effektivisera dina e-postarbetsflöden idag!


## Vanliga frågor

### Kan jag använda den här koden med Gmail eller Outlook?
Ja! Ersätt `imap.example.com` med Gmails (`imap.gmail.com`) eller Outlooks (`outlook.office365.com`) IMAP-serveradress.

### Är Aspose.Email gratis att använda?
Aspose.Email kräver en licens för alla funktioner. Du kan begära en [gratis provperiod](https://releases.aspose.com/) eller en [tillfällig licens](https://purchase.aspose.com/temporary-license/).

### Hur kan jag hantera lösenordssäkerhet?
Överväg att använda miljövariabler eller säker lagring av autentiseringsuppgifter istället för hårdkodade lösenord.

### Kan jag extrahera bilagor från skickade objekt?
Ja, använd helt enkelt `SelectFolder(ImapFolderInfo.Sent)` istället för inkorgen.

### Stöder Aspose.Email POP3?
Absolut! Förutom IMAP stöder den även POP3 och SMTP.