---
"description": "Lär dig hur du smidigt lägger till en digital signatur i dina Word-dokument med Aspose.Words för .NET. Den här omfattande handledningen täcker allt från att konfigurera din miljö och infoga en signaturrad till att spara och verifiera dina signerade dokument."
"linktitle": "Skapa och signera en ny signaturrad"
"second_title": "Aspose.Words dokumentbehandlings-API"
"title": "Skapa och signera en ny signaturrad"
"url": "/sv/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## Introduktion

Vill du lägga till en digital signatur i ett Word-dokument? Med Aspose.Words för .NET är det enklare än du kanske tror! Den här handledningen guidar dig genom stegen för att konfigurera din miljö, lägga till en signaturrad och signera ditt dokument digitalt. Nu sätter vi igång!

## Förkunskapskrav

Innan du går in i koden, se till att du har följande:

1. Aspose.Words för .NET - [Ladda ner den här](https://releases.aspose.com/words/net/).
2. .NET-utvecklingsmiljön – Visual Studio är idealisk för den här uppgiften.
3. Dokument att signera – Du kan skapa ett nytt Word-dokument eller använda ett befintligt.
4. Certifikatfil - A `.pfx` filen är nödvändig för digitala signaturer.
5. Bild på signaturrad (valfritt) – Du kan inkludera en bildfil för signaturen.

## Importera obligatoriska namnrymder

För att använda funktionerna i Aspose.Words måste du importera följande namnrymder:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Steg 1: Konfigurera dokumentkatalogen

Börja med att definiera sökvägen till din dokumentkatalog. Det är här du sparar och hämtar dina dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ange sökvägen till dokumentkatalogen
```

## Steg 2: Skapa ett nytt dokument

Nu ska vi skapa ett nytt Word-dokument. Dokumentet kommer att fungera som arbetsyta för din signaturrad.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga signaturraden

Använd nu `DocumentBuilder` klass för att infoga en signaturrad i ditt dokument:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Steg 4: Spara dokumentet

När du har infogat signaturraden sparar du dokumentet. Detta är ett viktigt steg innan du signerar.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Steg 5: Konfigurera signeringsalternativ

Konfigurera alternativen för signeringsprocessen. Detta inkluderar att ange signaturrads-ID och den valfria bilden som ska visas med signaturen.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // Sökväg till din bild
};
```

## Steg 6: Ladda certifikatet

Ladda certifikatfilen som krävs för att signera dokumentet:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // Justera filnamn och lösenord
```

## Steg 7: Signera dokumentet

Slutligen, signera dokumentet med hjälp av `DigitalSignatureUtil` klass. Spara det signerade dokumentet med ett nytt namn för framtida referens.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## Slutsats

Grattis! Du har skapat ett Word-dokument, lagt till en signaturrad och signerat det digitalt med Aspose.Words för .NET. Detta kraftfulla verktyg förenklar dokumentautomation och säkerställer att dina kontrakt och formella dokument är säkert signerade och autentiserade.

## Vanliga frågor

### Kan jag använda andra bildformat för signaturraden?

Ja, du kan använda olika bildformat, inklusive PNG, JPG och BMP.

### Är det nödvändigt att använda en `.pfx` ansöka om certifikat?

Ja, en `.pfx` fil är ett standardformat för att lagra certifikat och privata nycklar för digitala signaturer.

### Kan jag lägga till flera signaturrader i ett enda dokument?

Absolut! Du kan infoga flera signaturrader genom att upprepa infogningssteget efter behov.

### Vad händer om jag inte har ett digitalt certifikat?

Du måste skaffa ett digitalt certifikat från en betrodd certifikatutfärdare eller generera ett med verktyg som OpenSSL.

### Hur verifierar jag den digitala signaturen i dokumentet?

Du kan verifiera den digitala signaturen genom att öppna det signerade dokumentet i Word och kontrollera signaturuppgifterna för att bekräfta dess äkthet och integritet.