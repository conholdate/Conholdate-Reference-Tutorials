---
"description": "Den här guiden innehåller steg-för-steg-instruktioner och exempelkod som hjälper dig att effektivt skapa 1Bpp-indexerade bilder för arkivering, utskrift eller utrymmesbesparande ändamål."
"linktitle": "Skapa 1Bpp indexerad"
"second_title": "Aspose.Words dokumentbehandlings-API"
"title": "Skapa 1Bpp indexerad"
"url": "/sv/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## Introduktion

Har du någonsin behövt konvertera ett Word-dokument till en svartvit bild? Oavsett om det gäller digital arkivering, utskrift eller helt enkelt för att spara utrymme kan det vara otroligt användbart att konvertera dina dokument till en indexerad bild med 1Bpp. I den här guiden går vi igenom en enkel metod för att uppnå detta med Aspose.Words för .NET. Nu sätter vi igång!

## Förkunskapskrav

Innan du går in i koden, se till att du har följande:

- Aspose.Words för .NET: Ladda ner och installera biblioteket från [här](https://releases.aspose.com/words/net/).
- .NET-utvecklingsmiljö: Visual Studio är ett populärt val, men alla IDE:er som stöder .NET fungerar.
- Grundläggande C#-kunskaper: Bekantskap med C# är bra, men vi kommer att hålla det enkelt.
- Exempel på Word-dokument: Ha ett dokument klart för konvertering.

## Steg 1: Importera nödvändiga namnrymder

För att använda Aspose.Words måste du importera relevanta namnrymder. Detta är viktigt för att komma åt de klasser och metoder som krävs för dokumenthantering.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Steg 2: Konfigurera din dokumentkatalog

Ange sökvägen till katalogen där ditt Word-dokument är lagrat och var du vill spara den konverterade bilden.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Steg 3: Ladda Word-dokumentet

Ladda in ditt Word-dokument i en `Aspose.Words.Document` objekt. Det här objektet låter dig manipulera dokumentet programmatiskt.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 4: Konfigurera alternativ för att spara bilder

Ställ sedan in `ImageSaveOptions` för att definiera hur dokumentet ska sparas som en bild. Vi konfigurerar det för att spara i PNG-format med 1Bpp indexerat färgläge.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // Konvertera endast den första sidan
    ImageColorMode = ImageColorMode.BlackAndWhite, // Ställ in på svartvitt
    PixelFormat = ImagePixelFormat.Format1bppIndexed // Använd 1Bpp indexerat format
};
```

- SaveFormat.Png: Anger att utdataformatet ska vara PNG.
- PageSet(1): Anger att endast den första sidan i dokumentet kommer att konverteras.
- ImageColorMode.BlackAndWhite: Säkerställer att bilden är i svartvitt.
- ImagePixelFormat.Format1bppIndexed: Ställer in pixelformatet till 1Bpp indexerat, vilket optimerar för utrymme.

## Steg 5: Spara dokumentet som en bild

Använd slutligen `Save` metod för `Document` objekt för att spara den konverterade bilden.

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## Slutsats

Grattis! Du har framgångsrikt konverterat ett Word-dokument till en indexerad bild på 1Bpp med hjälp av Aspose.Words för .NET. Den här metoden är inte bara effektiv utan hjälper dig också att skapa bilder med hög kontrast som är lämpliga för olika tillämpningar. Integrera gärna den här funktionen i dina projekt. Lycka till med kodningen!

## Vanliga frågor

### Vad är en 1Bpp indexerad bild?
En indexerad bild på 1Bpp (1 bit per pixel) är ett svartvitt bildformat där varje pixel representeras av en enda bit, antingen 0 eller 1. Detta format är mycket utrymmeseffektivt, vilket gör det idealiskt för arkivering.

### Kan jag konvertera flera sidor i ett Word-dokument samtidigt?
Ja! Ändra bara `PageSet` egendom i `ImageSaveOptions` för att inkludera flera sidor eller ställa in den så att hela dokumentet konverteras.

### Behöver jag en licens för att använda Aspose.Words för .NET?
Ja, en licens krävs för full funktionalitet. Du kan få en [tillfällig licens här](https://purchase.aspose.com/temporary-license/).

### Vilka andra bildformat kan jag konvertera mitt Word-dokument till?
Aspose.Words stöder olika format, inklusive JPEG, BMP och TIFF. Ändra bara `SaveFormat` i `ImageSaveOptions` till ditt önskade format.

### Var kan jag hitta mer dokumentation om Aspose.Words för .NET?
För omfattande dokumentation, besök [Dokumentationssida för Aspose.Words för .NET](https://reference.aspose.com/words/net/).