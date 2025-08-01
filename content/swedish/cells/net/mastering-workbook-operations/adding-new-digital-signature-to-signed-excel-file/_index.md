---
"description": "Lär dig hur du lägger till en ny digital signatur till en befintlig signerad Excel-fil med Aspose.Cells för .NET. Den här omfattande guiden täcker alla förutsättningar, steg-för-steg-instruktioner och kodexempel."
"linktitle": "Lägga till en ny digital signatur till en signerad Excel-fil"
"second_title": "Aspose.Cells .NET Excel-bearbetnings-API"
"title": "Lägga till en ny digital signatur till en signerad Excel-fil"
"url": "/sv/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## Introduktion

dagens digitala landskap är det viktigare än någonsin att säkerställa dokumentens äkthet och integritet. Digitala signaturer ger ett tillförlitligt sätt att verifiera att ett dokument inte har ändrats och att det kommer från en legitim källa. Om du arbetar med Excel-filer i .NET och behöver lägga till en ny digital signatur till en fil som redan är signerad, är den här guiden för dig! Vi går igenom processen att lägga till en digital signatur till en befintlig signerad Excel-fil med hjälp av Aspose.Cells för .NET.

## Förkunskapskrav

Innan vi går in i implementeringen, se till att du har följande:

1. Aspose.Cells för .NET: Ladda ner och installera Aspose.Cells från [släppsida](https://releases.aspose.com/cells/net/).
2. .NET Framework: Se till att din dator har .NET Framework konfigurerat och att du är bekant med grundläggande .NET-programmeringskoncept.
3. Digitalt certifikat: Skaffa ett giltigt digitalt certifikat i .pfx-format. För testning kan du skapa ett självsignerat certifikat.
4. Utvecklingsmiljö: Använd en IDE som Visual Studio för att skriva och köra din C#-kod.
5. Exempel på Excel-fil: Ha en befintlig Excel-fil som redan är digitalt signerad, som kommer att vara målet för att lägga till en ny signatur.

Med dessa förutsättningar på plats, låt oss hoppa in i koden!

## Importera nödvändiga paket

Överst i din C#-fil, inkludera följande namnrymder för att komma åt de obligatoriska klasser och metoderna:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Steg 1: Definiera dina kataloger

Ange katalogerna för dina källfiler och var utdatafilen ska sparas:

```csharp
// Källkatalog
string sourceDir = "Your Document Directory"; // Ersätt med din faktiska katalog
// Utdatakatalog
string outputDir = "Your Document Directory"; // Ersätt med din faktiska katalog
```

## Steg 2: Läs in den befintliga signerade arbetsboken

Ladda Excel-arbetsboken som redan är signerad:

```csharp
// Ladda arbetsboken som redan är digitalt signerad
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## Steg 3: Skapa en digital signatursamling

Skapa en samling för att hantera dina digitala signaturer:

```csharp
// Skapa den digitala signatursamlingen
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## Steg 4: Ladda ditt certifikat

Ladda ditt digitala certifikat, som kommer att användas för att skapa den nya signaturen:

```csharp
// Certifikatfil och dess lösenord
string certFileName = sourceDir + "AsposeDemo.pfx"; // Din certifikatfil
string password = "aspose"; // Ditt certifikatlösenord

// Skapa nytt certifikat
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## Steg 5: Skapa en ny digital signatur

Skapa nu en ny digital signatur och lägg till den i din samling:

```csharp
// Skapa en ny digital signatur och lägg till den i samlingen
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## Steg 6: Lägg till signatursamlingen i arbetsboken

Lägg till samlingen digitala signaturer i arbetsboken:

```csharp
// Lägg till digitala signaturer i arbetsboken
workbook.AddDigitalSignature(dsCollection);
```

## Steg 7: Spara arbetsboken

Spara arbetsboken med den nya digitala signaturen inkluderad:

```csharp
// Spara arbetsboken
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## Steg 8: Bekräfta att det lyckades

Ge feedback vid lyckat utförande:

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## Slutsats

Grattis! Du har lagt till en ny digital signatur till en redan signerad Excel-fil med Aspose.Cells för .NET. Den här processen förbättrar säkerheten för dina dokument och säkerställer deras äkthet och integritet.

## Vanliga frågor

### Vad är en digital signatur?

En digital signatur är ett matematiskt schema som verifierar äktheten och integriteten hos digitala meddelanden eller dokument, säkerställer att de inte har ändrats och bekräftar undertecknarens identitet.

### Behöver jag ett särskilt certifikat för att skapa en digital signatur?

Ja, ett digitalt certifikat utfärdat av en betrodd certifikatutfärdare (CA) krävs för att skapa en giltig digital signatur.

### Kan jag använda ett självsignerat certifikat för testning?

Absolut! Du kan använda ett självsignerat certifikat för utvecklings- och teständamål, men för produktion är det lämpligt att använda ett certifikat från en betrodd certifikatutfärdare.

### Vad händer om jag försöker lägga till en signatur i ett dokument som inte är signerat?

Om du försöker lägga till en digital signatur i ett dokument som inte redan är signerat kommer det att fungera utan problem, men den ursprungliga signaturen kommer inte att finnas kvar.

### Var kan jag hitta mer information om Aspose.Cells?

För detaljerade guider och API-referenser, se [Aspose.Cells-dokumentation](https://reference.aspose.com/cells/net/).