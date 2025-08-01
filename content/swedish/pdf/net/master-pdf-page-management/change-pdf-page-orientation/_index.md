---
"description": "Upptäck hur du enkelt justerar sidorienteringen på PDF-filer med Aspose.PDF för .NET. Den här steg-för-steg-guiden ger tydliga instruktioner om hur du laddar, roterar och sparar dina dokument."
"linktitle": "Ändra PDF-sidorientering"
"second_title": "Aspose.PDF för .NET API-referens"
"title": "Ändra PDF-sidorientering"
"url": "/sv/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Introduktion

Har du någonsin stött på en PDF-fil där sidorienteringen är helt fel? Oavsett om det är ett dokument som har skannats felaktigt eller ett som helt enkelt behöver en annan layout, kan justering av orienteringen göra en enorm skillnad. Lyckligtvis erbjuder Aspose.PDF för .NET ett kraftfullt och användarvänligt sätt att manipulera PDF-filer, inklusive att ändra sidorienteringen. I den här guiden guidar vi dig genom processen steg för steg, oavsett om du vill växla från stående till liggande eller vice versa.

## Förkunskapskrav

Innan vi går in på detaljerna, se till att du har följande på plats:

- Aspose.PDF för .NET: Se till att du har Aspose.PDF-biblioteket installerat. Om du inte har gjort det än kan du [ladda ner den här](https://releases.aspose.com/pdf/net/).
- En .NET-utvecklingsmiljö: Du kan använda Visual Studio, JetBrains Rider eller någon annan IDE du föredrar för .NET-utveckling.
- Grundläggande kunskaper i C#: Bekantskap med C# gör att du lättare kan följa med.
- En PDF-fil: Ha en exempel-PDF-fil redo för testning. Du kan skapa en eller ladda ner ett exempel online.

Om du precis har börjat kan du överväga att prova Aspose.PDF med en [gratis tillfällig licens](https://purchase.aspose.com/temporary-license/) innan man bestämmer sig för att [köp den fullständiga versionen](https://purchase.aspose.com/buy).

## Importera namnrymder

För att manipulera PDF-sidor måste du först importera de nödvändiga namnrymderna i ditt C#-projekt. Lägg till följande rader högst upp i din kodfil:

```csharp
using System.IO;
using Aspose.Pdf;
```

Nu när vi har allt klart, låt oss börja!

## Steg 1: Ladda PDF-dokumentet

Det första steget är att ladda PDF-filen du vill ändra. Använd `Document` klass från Aspose.PDF-namnrymden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Se till att byta ut `"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din PDF-fil.

## Steg 2: Loopa igenom varje sida

Härnäst loopar vi igenom varje sida i PDF-dokumentet. Detta gör att vi kan tillämpa orienteringsändringen på alla sidor:

```csharp
foreach (Page page in doc.Pages)
{
    // Manipulera varje sida
}
```

## Steg 3: Gå till sidans mediabox

Varje PDF-sida har en `MediaBox` som definierar dess gränser. Vi behöver komma åt detta för att kontrollera den aktuella orienteringen och göra justeringar:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

De `MediaBox` anger sidans dimensioner, inklusive bredd och höjd.

## Steg 4: Byt bredd och höjd

För att ändra sidorienteringen byter vi ut bredd- och höjdvärdena. Denna justering ändrar sidans dimensioner:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Här beräknar vi de nya måtten och flyttar det nedre vänstra hörnet (`LLY`) i enlighet därmed.

## Steg 5: Uppdatera MediaBox och CropBox

Nu när vi har de nya dimensionerna kommer vi att tillämpa dessa ändringar på `MediaBox` och `CropBox` för att säkerställa att sidan visas korrekt:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Steg 6: Rotera sidan

För att slutföra ändringen av orienteringen roterar vi sidan. Detta är enkelt med Aspose.PDF:

```csharp
page.Rotate = Rotation.on90; // Rotera 90 grader
```

Den här linjen vänder effektivt sidan till önskad orientering.

## Steg 7: Spara utdata-PDF-filen

När du har ändrat orienteringen på alla sidor, spara det uppdaterade dokumentet till en ny fil:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Se till att ange ett nytt filnamn för att undvika att skriva över originaldokumentet.

## Slutsats

Och där har du det! Att ändra sidorienteringen på en PDF-fil med Aspose.PDF för .NET är en enkel process. Genom att läsa in dokumentet, loopa igenom sidorna, uppdatera MediaBox och spara filen kan du enkelt justera layouten efter dina behov. Oavsett om du korrigerar ett dåligt skannat dokument eller formaterar sidor för presentation, bör den här guiden hjälpa dig att få jobbet gjort effektivt.

## Vanliga frågor

### Kan jag rotera specifika sidor istället för alla sidor i PDF-filen?  
Ja, du kan modifiera loopen för att rikta in dig på specifika sidor efter deras index istället för att iterera igenom alla sidor.

### Vad är `MediaBox`?  
De `MediaBox` definierar sidans storlek och form i en PDF-fil och avgör var innehållet placeras.

### Fungerar Aspose.PDF för .NET med andra filformat?  
Ja, Aspose.PDF kan hantera olika filformat, inklusive HTML, XML, XPS och mer.

### Finns det en gratisversion av Aspose.PDF för .NET?  
Ja, du kan börja med en [gratis provperiod](https://releases.aspose.com/) eller begära en [tillfällig licens](https://purchase.aspose.com/temporary-license/).

### Kan jag ångra ändringarna när de har sparats?  
När du har sparat dokumentet är ändringarna permanenta. Det är lämpligt att arbeta med en kopia eller spara en säkerhetskopia av originalfilen.