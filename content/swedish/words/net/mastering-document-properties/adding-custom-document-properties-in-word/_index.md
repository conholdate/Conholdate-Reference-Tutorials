---
"description": "Lär dig hur du förbättrar dina Word-dokument med anpassade dokumentegenskaper med Aspose.Words för .NET. Den här omfattande guiden guidar dig genom processen."
"linktitle": "Lägga till anpassade dokumentegenskaper i Word"
"second_title": "Aspose.Words dokumentbehandlings-API"
"title": "Lägga till anpassade dokumentegenskaper i Word"
"url": "/sv/words/net/mastering-document-properties/adding-custom-document-properties-in-word/"
"weight": 10
---

## Introduktion

Välkommen! Om du utforskar Aspose.Words för .NET och vill lära dig hur du lägger till anpassade dokumentegenskaper i dina Word-filer har du kommit rätt. Anpassade egenskaper är ovärderliga för att lagra ytterligare metadata som inbyggda egenskaper inte täcker. Oavsett om du behöver spåra dokumentauktorisering, revisionsnummer eller specifika datum kan anpassade egenskaper hjälpa till. I den här handledningen guidar vi dig genom stegen för att lägga till dessa egenskaper sömlöst med Aspose.Words för .NET. Nu sätter vi igång!

## Förkunskapskrav

Innan du går in i koden, se till att du har följande:

1. Aspose.Words för .NET-biblioteket: Ladda ner det [här](https://releases.aspose.com/words/net/).
2. Utvecklingsmiljö: En IDE som Visual Studio.
3. Grundläggande kunskaper i C#: Bekantskap med C# och .NET är meriterande.
4. Exempeldokument: Förbered ett exempeldokument i Word med namnet `Properties.docx` för modifiering.

## Importera namnrymder

För att komma åt funktionerna i Aspose.Words måste du importera nödvändiga namnrymder i början av din kod:

```csharp
using System;
using Aspose.Words;
```

## Steg 1: Konfigurera dokumentsökvägen

Nu ska vi definiera sökvägen till ditt Word-dokument. Det här steget är viktigt för att hitta och öppna ditt `Properties.docx` fil.

```csharp
// Ange sökvägen till din dokumentkatalog.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

Se till att byta ut `"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till ditt dokument.

## Steg 2: Åtkomst till anpassade dokumentegenskaper

Nu ska vi komma åt egenskaperna för det anpassade dokumentet i Word-dokumentet, där dina anpassade metadata kommer att finnas.

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
```

Den här raden ger dig tillgång till samlingen av anpassade egenskaper som du kommer att arbeta med.

## Steg 3: Kontrollera befintliga egenskaper

Innan du lägger till nya egenskaper är det klokt att kontrollera om en egenskap redan finns för att undvika dubbelarbete.

```csharp
if (customDocumentProperties["Authorized"] != null) return;
```

Den här koden kontrollerar om egenskapen "Authorized" redan finns. Om den gör det avslutas metoden tidigt, vilket förhindrar dubbletter.

## Steg 4: Lägga till en boolesk egenskap

Låt oss lägga till en anpassad boolesk egenskap för att ange om dokumentet är auktoriserat.

```csharp
customDocumentProperties.Add("Authorized", true);
```

Den här raden lägger till en egenskap med namnet "Auktoriserad" och ställer in dess värde på `true`.

## Steg 5: Lägga till en strängegenskap

Nästa steg är att ange vem som godkände dokumentet genom att lägga till en sträng-egenskap.

```csharp
customDocumentProperties.Add("Authorized By", "John Smith");
```

Du kan gärna ersätta "John Smith" med vilket namn du vill.

## Steg 6: Lägga till en datumegenskap

För att spåra när dokumentet godkändes, låt oss lägga till en datum-egenskap.

```csharp
customDocumentProperties.Add("Authorized Date", DateTime.Today);
```

Den här raden lägger till en egenskap som heter "Auktoriserat datum" och tilldelar den dagens datum med hjälp av `DateTime.Today`.

## Steg 7: Lägga till ett revisionsnummer

För versionshantering kan vi lägga till en egenskap för att hålla reda på dokumentets revisionsnummer.

```csharp
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
```

Här lägger vi till egenskapen "Auktoriserad revision" som innehåller dokumentets aktuella revisionsnummer.

## Steg 8: Lägga till en numerisk egenskap

Slutligen, låt oss lägga till en numerisk egenskap för att lagra ett auktoriserat belopp, till exempel ett budgetbelopp.

```csharp
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Den här raden lägger till en egenskap med namnet "Auktoriserat belopp" med värdet `123.45`Du kan justera detta nummer efter behov.

## Slutsats

Grattis! Du har lagt till anpassade dokumentegenskaper i ett Word-dokument med Aspose.Words för .NET. Dessa egenskaper är ett kraftfullt sätt att lagra metadata anpassade efter dina behov, oavsett om det gäller att spåra auktoriseringsdetaljer, revisionsnummer eller specifika belopp.

## Vanliga frågor

### Vad är anpassade dokumentegenskaper?
Anpassade dokumentegenskaper är metadata som du kan lägga till i ett Word-dokument för att lagra ytterligare information som inte täcks av inbyggda egenskaper.

### Kan jag lägga till andra egenskaper än strängar och tal?
Ja, du kan lägga till olika typer av egenskaper, inklusive booleska värden, datum och till och med anpassade objekt.

### Hur kan jag komma åt dessa egenskaper i ett Word-dokument?
Du kan komma åt anpassade egenskaper programmatiskt med hjälp av Aspose.Words eller visa dem direkt i Word via dokumentegenskaperna.

### Är det möjligt att redigera eller ta bort anpassade egenskaper?
Absolut! Du kan enkelt redigera eller ta bort anpassade egenskaper med hjälp av metoder som tillhandahålls av Aspose.Words.

### Kan anpassade egenskaper användas för att filtrera dokument?
Ja! Anpassade egenskaper är utmärkta för att kategorisera och filtrera dokument baserat på specifika metadata.