---
"description": "Upptäck hur du programmatiskt lägger till signaturrader i dina Word-dokument med Aspose.Words för .NET. Den här omfattande guiden täcker allt från att konfigurera din utvecklingsmiljö till att infoga signaturrader och signera dokument säkert."
"linktitle": "Skapa ny digital signaturrad och ange leverantörs-ID"
"second_title": "Aspose.Words dokumentbehandlings-API"
"title": "Skapa ny digital signaturrad och ange leverantörs-ID"
"url": "/sv/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Introduktion

Hej teknikentusiaster! Har ni någonsin velat automatisera inkluderingen av signaturrader i era Word-dokument? Idag ska vi titta på hur man gör detta med Aspose.Words för .NET. Den här steg-för-steg-guiden guidar er genom att skapa en signaturrad och ställa in leverantörs-ID, vilket gör era dokumenthanteringsuppgifter mer effektiva och strömlinjeformade.

## Förkunskapskrav

Innan vi sätter igång, låt oss se till att du har allt klart:

1. Aspose.Words för .NET: Om du inte har installerat det än, ladda ner det [här](https://releases.aspose.com/words/net/).
2. Utvecklingsmiljö: Använd Visual Studio eller valfri C#-utvecklingskonfiguration.
3. .NET Framework: Se till att du har .NET Framework installerat på din dator.
4. PFX-certifikat: Du behöver ett PFX-certifikat för att signera dokument, vilket kan erhållas från en betrodd certifikatutfärdare.

## Importera nödvändiga namnrymder

För att komma igång, importera de namnrymder som krävs till ditt C#-projekt:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Nu ska vi gå in på detaljerna kring att skapa en ny signaturrad och ställa in leverantörs-ID:t.

## Steg 1: Skapa ett nytt dokument

Först måste vi skapa ett nytt Word-dokument som kommer att fungera som arbetsyta för vår signaturrad:

```csharp
// Ange sökvägen till din dokumentkatalog.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Här initierar vi ett nytt `Document` och en `DocumentBuilder`, vilket gör att vi enkelt kan lägga till element.

## Steg 2: Definiera alternativ för signaturrad

Härnäst definierar vi alternativen för vår signaturrad, inklusive undertecknarens namn, titel, e-postadress och andra relevanta uppgifter:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Dessa alternativ hjälper till att anpassa signaturraden och göra den tydlig och professionell.

## Steg 3: Infoga signaturraden

Med våra alternativ redo kan vi nu infoga signaturraden i dokumentet:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

De `InsertSignatureLine` Metoden lägger till signaturraden, och vi tilldelar den ett unikt leverantörs-ID.

## Steg 4: Spara dokumentet

Efter att ha infogat signaturraden, låt oss spara dokumentet:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Detta sparar ditt dokument med den nyligen tillagda signaturraden.

## Steg 5: Konfigurera signeringsalternativ

Nu ska vi konfigurera signeringsalternativen, inklusive signaturrads-ID, leverantörs-ID, kommentarer och signeringstid:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Dessa inställningar säkerställer att dokumentet signeras med korrekta uppgifter.

## Steg 6: Skapa certifikatinnehavare

För att signera dokumentet måste vi skapa en certifikatinnehavare med hjälp av PFX-certifikatet:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Ersätta `"morzal.pfx"` med ditt faktiska certifikatfilnamn och `"aw"` med ditt certifikatlösenord.

## Steg 7: Signera dokumentet

Slutligen ska vi signera dokumentet med hjälp av verktyget för digital signatur:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Den här processen signerar dokumentet och sparar det som en ny fil.

## Slutsats

Grattis! Du har skapat en signaturrad och angett leverantörs-ID i ett Word-dokument med Aspose.Words för .NET. Detta kraftfulla bibliotek förenklar dokumentbehandling och effektiviserar ditt arbetsflöde. Testa det och se hur det kan förbättra dina projekt!

## Vanliga frågor

### Kan jag anpassa utseendet på signaturraden?
Absolut! Du kan justera olika alternativ i `SignatureLineOptions` för att passa din stil och dina behov.

### Vad händer om jag inte har ett PFX-certifikat?
Du måste skaffa ett från en betrodd certifikatutfärdare, eftersom det är viktigt för att signera dokument digitalt.

### Kan jag lägga till flera signaturrader i ett dokument?
Ja, du kan lägga till flera signaturrader genom att upprepa infogningsprocessen med olika alternativ.

### Är Aspose.Words för .NET kompatibelt med .NET Core?
Ja, Aspose.Words för .NET stöder .NET Core, vilket gör det mångsidigt för olika utvecklingsmiljöer.

### Hur säkra är de digitala signaturerna?
Digitala signaturer skapade med Aspose.Words är mycket säkra, förutsatt att du använder ett giltigt och pålitligt certifikat.