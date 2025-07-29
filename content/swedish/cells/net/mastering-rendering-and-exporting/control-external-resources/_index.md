---
"description": "Frigör den fulla potentialen hos dina Excel-till-PDF-konverteringar med Aspose.Cells för .NET. I den här omfattande guiden lär du dig hur du hanterar externa resurser, till exempel bilder, och säkerställer att dina PDF-filer återspeglar dina exakta formateringskrav."
"linktitle": "Kontrollera externa resurser med Aspose.Cells för .NET"
"second_title": "Aspose.Cells .NET Excel-bearbetnings-API"
"title": "Kontrollera externa resurser med Aspose.Cells för .NET"
"url": "/sv/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## Introduktion

dagens digitala landskap är det en vanlig och viktig uppgift att konvertera Excel-kalkylblad till PDF-dokument. Oavsett om du förbereder rapporter, finansiell data eller presentationsmaterial är det avgörande att se till att dina PDF-filer återspeglar det avsedda formatet. Aspose.Cells för .NET tillhandahåller ett kraftfullt bibliotek som låter dig kontrollera denna konverteringsprocess i detalj, särskilt när du hanterar externa resurser som bilder. I den här guiden utforskar vi hur man effektivt hanterar externa resurser under konverteringsprocessen från Excel till PDF med Aspose.Cells. Nu kör vi!

## Förkunskapskrav

Innan vi börjar, se till att du har följande redo:

1. Visual Studio eller någon .NET-kompatibel IDE: Detta kommer att vara din utvecklingsmiljö.
2. Aspose.Cells för .NET: Om du inte har installerat det än, besök [Aspose-nedladdningar](https://releases.aspose.com/cells/net/) sidan för att få den senaste versionen.
3. Grundläggande kunskaper i C#: Bekantskap med C# är meriterande. Om du behöver förtydligande av några begrepp är du välkommen att slå upp dem.
4. Exempel på Excel-fil: Förbered en Excel-fil, till exempel "samplePdfSaveOptions_StreamProvider.xlsx", som innehåller externa resurser som du vill konvertera.
5. Bildfil för testning: Använd en bildfil som "newPdfSaveOptions_StreamProvider.png" som en extern resurs under konverteringen.

## Importera nödvändiga paket

För att börja måste du importera de namnrymder som krävs från Aspose.Cells-biblioteket. Lägg till följande med hjälp av direktiv högst upp i din C#-fil:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

Dessa namnrymder tillhandahåller de viktiga klasserna och metoderna för dina uppgifter.

## Steg 1: Skapa en strömleverantörsklass

Skapa först en strömleverantörsklass som implementerar `IStreamProvider` gränssnitt. Den här klassen låter dig styra hur externa resurser laddas.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // Ladda bilden till en minnesström
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: Den här metoden anropas när strömmen är stängd och för närvarande loggar ett felsökningsmeddelande.
- InitStream: Den här metoden läser den externa bildfilen som en byte-array, konverterar den till en minnesström och tilldelar den till `options.Stream` egendom.

## Steg 2: Konfigurera käll- och utdatakataloger

Definiera sedan katalogerna för din Excel-fil och den utgående PDF-filen.

```csharp
// Källkatalog
string sourceDir = "Your Document Directory";
// Utdatakatalog
string outputDir = "Your Document Directory";
```

Ersätta `"Your Document Directory"` med den faktiska sökvägen på ditt system där dina filer finns.

## Steg 3: Ladda din Excel-fil

Ladda nu in Excel-filen som du vill skapa PDF-filen från.

```csharp
// Ladda källfilen i Excel som innehåller externa bilder
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

De `Workbook` klassen från Aspose.Cells representerar din Excel-fil, som kan innehålla olika externa resurser som bilder.

## Steg 4: Ställ in alternativ för att spara PDF

Innan du sparar arbetsboken som en PDF, ange dina önskade sparalternativ.

```csharp
// Ange alternativ för att spara PDF - Stream Provider
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // Spara varje ark på en ny sida
};
```

Detta skapar en instans av `PdfSaveOptions`, så att du kan anpassa PDF-formatet. Den `OnePagePerSheet` Alternativet säkerställer att varje Excel-ark visas på en separat sida i den slutliga PDF-filen.

## Steg 5: Tilldela din streamingleverantör

Anslut din `Workbook` exempel med `MyStreamProvider` klass du skapade tidigare.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

Den här raden säkerställer att när externa resurser påträffas under konverteringen, kommer din anpassade leverantör att hantera dem i enlighet därmed.

## Steg 6: Spara arbetsboken som PDF

Spara nu din Excel-arbetsbok som en PDF.

```csharp
// Spara arbetsboken till PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

Genom att ringa `Save` Metoden på arbetsboksobjektet och skickar utdatakatalogen tillsammans med PDF-alternativen konverterar du Excel-filen till en välformaterad PDF.

## Steg 7: Bekräfta lyckad körning

Slutligen är det god praxis att bekräfta att processen har slutförts utan problem.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

Det här meddelandet informerar dig om statusen för din operation och ger användbar feedback.

## Slutsats

Du har nu bemästrat processen att kontrollera externa resurser under konverteringar från Excel till PDF med Aspose.Cells! Genom att följa dessa steg kan du säkerställa att dina dokument korrekt innehåller bilder och andra externa element, vilket resulterar i en polerad slutprodukt varje gång.

## Vanliga frågor

### Vad är Aspose.Cells?
Aspose.Cells är ett kraftfullt bibliotek för .NET-utvecklare som möjliggör skapande, manipulering, konvertering och rendering av Excel-filer i olika format.

### Hur laddar jag ner Aspose.Cells?
Du kan ladda ner den senaste versionen från [Nedladdningslänk](https://releases.aspose.com/cells/net/).

### Kan jag prova Aspose.Cells gratis?
Ja! Du kan få tillgång till en gratis provperiod genom att besöka [Gratis provsida](https://releases.aspose.com/).

### Var kan jag hitta support för Aspose.Cells?
För supportrelaterade frågor, besök [Aspose supportforum](https://forum.aspose.com/c/cells/9).

### Hur kan jag få en tillfällig licens för Aspose.Cells?
Du kan ansöka om ett tillfälligt körkort [här](https://purchase.aspose.com/temporary-license/).