---
"description": "Lär dig hur du enkelt kan läsa av skapningstiden för trådade kommentarer i ett Excel-ark med hjälp av Aspose.Cells för .NET. Följ vår detaljerade guide med steg-för-steg-instruktioner."
"linktitle": "Läs skapandetid för trådade kommentarer med Aspose.Cells"
"second_title": "Aspose.Cells .NET Excel-bearbetnings-API"
"title": "Läs skapandetid för trådade kommentarer med Aspose.Cells"
"url": "/sv/cells/net/guide-worksheet-operations/read-created-time-of-threaded-comment/"
"weight": 21
---

## Introduktion

När man arbetar med Excel-filer kan det vara viktigt att hantera kommentarer för samarbete och feedbackspårning. I den här guiden guidar vi dig genom processen att läsa av skapandetiden för trådade kommentarer i ett Excel-ark med hjälp av Aspose.Cells för .NET. Detta kraftfulla verktyg ger ett effektivt sätt att interagera med Excel-filer, vilket gör det möjligt för utvecklare att extrahera detaljerad information från kommentarer, vilket är särskilt användbart för att spåra tidpunkten för feedback i samarbetsscenarier.

## Förkunskapskrav

Innan vi börjar är det viktigt att se till att din utvecklingsmiljö är korrekt konfigurerad för att använda Aspose.Cells för .NET. Här är vad du behöver:

1. Aspose.Cells för .NET: Du behöver Aspose.Cells-biblioteket installerat. Du kan hämta den senaste versionen från [Aspose webbplats](https://releases.aspose.com/cells/net/).
2. IDE: Visual Studio (eller valfri .NET IDE) för att skriva och exekvera din kod.
3. Grundläggande C#-kunskaper: Bekantskap med C#-programmering gör det lättare att följa exemplen.
4. Excel-fil: I den här handledningen använder vi en Excel-fil med namnet `ThreadedCommentsSample.xlsx`, vilket inkluderar några trådade kommentarer. Se till att din fil innehåller kommentarer att följa.

## Importera de nödvändiga paketen

Till att börja med behöver du importera de namnrymder som behövs för att arbeta med Aspose.Cells. Öppna ditt C#-projekt och lägg till följande med hjälp av direktiv högst upp i din kodfil:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

De `Aspose.Cells` namnrymden ger dig åtkomst till alla klasser och metoder som krävs för att manipulera Excel-filer, medan `System` behövs för allmän funktionalitet såsom utdata och undantagshantering.

## Steg 1: Ange katalogen för Excel-filen

Det första steget är att definiera sökvägen dit din Excel-fil lagras. Denna sökväg kommer att användas för att hitta filen programmatiskt.

```csharp
// Definiera katalogen för Excel-filen
string sourceDir = "Your Document Directory";
```

Ersätta `"C:\\YourDirectory\\"` med den faktiska sökvägen till din fil. Detta säkerställer att programmet vet var det hittar filen `ThreadedCommentsSample.xlsx`.

## Steg 2: Läs in arbetsboken

Med katalogen konfigurerad kan vi nu ladda Excel-arbetsboken. Detta görs genom att skapa en ny `Workbook` objektet och skickar filsökvägen till det.

```csharp
// Läs in Excel-arbetsboken
Workbook workbook = new Workbook(sourceDir + "ThreadedCommentsSample.xlsx");
```

Om filen inte hittas på den angivna sökvägen kommer ett undantag att utlösas, så se till att filsökvägen är korrekt innan du fortsätter.

## Steg 3: Få åtkomst till önskat arbetsblad

När arbetsboken har laddats behöver du komma åt kalkylbladet som innehåller de trådade kommentarerna. I det här exemplet hämtar vi det första kalkylbladet i arbetsboken.

```csharp
// Åtkomst till det första kalkylbladet i arbetsboken
Worksheet worksheet = workbook.Worksheets[0];
```

Om dina kommentarer finns i ett annat kalkylblad, ändra helt enkelt indexet därefter. Använd till exempel `Worksheets[1]` för det andra arbetsbladet, och så vidare.

## Steg 4: Hämta trådade kommentarer

För att hämta de trådade kommentarerna måste du ange cellen som innehåller kommentarerna. I det här fallet fokuserar vi på cell `A1`Metoden `GetThreadedComments` används för att hämta alla kommentarer som är kopplade till en specifik cell.

```csharp
// Hämta trådade kommentarer från cell A1
ThreadedCommentCollection threadedComments = worksheet.Comments.GetThreadedComments("A1");
```

Detta returnerar en samling trådade kommentarer för cell A1. Om det inte finns några kommentarer i den angivna cellen kommer samlingen att vara tom.

## Steg 5: Iterera igenom kommentarerna och extrahera skapad tid

När de trådade kommentarerna har hämtats är nästa steg att iterera igenom samlingen och extrahera relevant information, inklusive skapandet av varje kommentar. Vi kan enkelt uppnå detta genom att loopa igenom `ThreadedCommentCollection`.

```csharp
// Gå igenom varje trådad kommentar och visa detaljerna
foreach (ThreadedComment comment in threadedComments)
{
    Console.WriteLine("Comment: " + comment.Notes);
    Console.WriteLine("Author: " + comment.Author.Name);
    Console.WriteLine("Created Time: " + comment.CreatedTime);
}
```

Denna kod kommer att visa kommentarens innehåll, författarens namn och tidpunkten då kommentaren skapades. `CreatedTime` egenskapen returnerar tidsstämpeln när kommentaren ursprungligen skapades.

## Steg 6: Visa ett bekräftelsemeddelande

Efter att ha läst de trådade kommentarerna och visat informationen är det alltid en bra idé att inkludera ett bekräftelsemeddelande i din kod. Detta hjälper till att bekräfta att processen utfördes korrekt.

```csharp
// Bekräftelsemeddelande
Console.WriteLine("Successfully retrieved threaded comment created times.");
```

Det här meddelandet skrivs ut till konsolen när kodkörningen är klar, vilket bekräftar att processen kördes utan fel.

## Slutsats

Du har nu lärt dig hur du enkelt kan läsa av tiden då trådade kommentarer skapades i ett Excel-ark med hjälp av Aspose.Cells för .NET. Den här funktionen är ovärderlig för att spåra kommentarer och feedback i samarbetsmiljöer och ger viktiga tidsstämplar för dokumentgranskningsprocesser. Genom att följa den här guiden kan du effektivt extrahera och använda kommentardata i dina .NET-applikationer, vilket förbättrar ditt arbetsflöde och förbättrar samarbetet med teammedlemmar.

## Vanliga frågor

### Vad är Aspose.Cells för .NET?

Aspose.Cells för .NET är ett omfattande bibliotek som gör det möjligt för utvecklare att skapa, manipulera och hantera Excel-filer i .NET-applikationer. Det tillhandahåller robusta verktyg för att läsa, skriva och modifiera Excel-filer programmatiskt.

### Hur kan jag ladda ner Aspose.Cells för .NET?

Du kan ladda ner den senaste versionen av Aspose.Cells för .NET från [Aspose webbplats](https://releases.aspose.com/cells/net/).

### Finns det en gratis provperiod tillgänglig?

Ja, Aspose erbjuder en gratis testversion av Aspose.Cells för .NET. Du kan ladda ner testversionen från [gratis provsida](https://releases.aspose.com/).

### Kan jag komma åt kommentarer från andra celler?

Ja, du kan komma åt trådade kommentarer från vilken cell som helst i kalkylbladet genom att ändra cellreferensen i `GetThreadedComments` metod. Ändra helt enkelt `"A1"` till den önskade cellens referens.

### Var kan jag få support för Aspose.Cells?

Om du behöver stöd eller har frågor, besök [Aspose-forumet](https://forum.aspose.com/c/cells/9), där du kan hitta svar eller be om hjälp från samhället.