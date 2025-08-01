---
"description": "Lås upp kraften i PDF-manipulation med Aspose.PDF för .NET i den här steg-för-steg-handledningen. Lär dig hur du programmatiskt skapar visuellt tilltalande PDF-dokument genom att rita fyllda rektanglar."
"linktitle": "Skapa fylld rektangel"
"second_title": "Aspose.PDF för .NET API-referens"
"title": "Skapa fylld rektangel"
"url": "/sv/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## Introduktion

Har du någonsin velat skapa visuellt fantastiska PDF-filer programmatiskt? I så fall har du kommit rätt! I den här handledningen utforskar vi Aspose.PDF för .NET, ett kraftfullt bibliotek som förenklar hantering av PDF-dokument. Idag fokuserar vi på att skapa en fylld rektangel i en PDF-fil. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här guiden att guida dig genom varje steg på ett vänligt och engagerande sätt. Så ta din kodningshatt och låt oss sätta igång!

## Förkunskapskrav

Innan vi går in på koden, se till att du har följande:

1. Visual Studio: Installera Visual Studio på din dator, eftersom det är ett utmärkt IDE för .NET-utveckling.
2. Aspose.PDF för .NET: Ladda ner och installera Aspose.PDF-biblioteket från [här](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper i C#: Bekantskap med C#-programmering hjälper dig att förstå kodavsnitten bättre.

## Steg 1: Skapa ett nytt projekt

1. Öppna Visual Studio och skapa ett nytt konsolprogramprojekt.
2. Namnge ditt projekt på ett lämpligt sätt.

## Steg 2: Lägg till Aspose.PDF-referens

1. Högerklicka på ditt projekt i lösningsutforskaren.
2. Välj Hantera NuGet-paket.
3. Sök efter Aspose.PDF och installera den senaste versionen.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nu när vi har allt klart, låt oss dyka in i koden!

## Steg 3: Konfigurera din dokumentkatalog

Ange sökvägen där din PDF ska sparas:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersätta `"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen på din dator där du vill spara PDF-filen.

## Steg 4: Skapa en dokumentinstans

Initiera ett nytt PDF-dokument:

```csharp
// Skapa dokumentinstans
Document doc = new Document();
```

## Steg 5: Lägg till en sida i dokumentet

Varje PDF behöver minst en sida. Låt oss lägga till en:

```csharp
// Lägg till sida till sidsamling i PDF-filen
Page page = doc.Pages.Add();
```

## Steg 6: Skapa en grafinstans

En `Graph` instansen fungerar som en duk för att rita former:

```csharp
// Skapa Graph-instans
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## Steg 7: Lägg till grafen på sidan

Bifoga grafen till sidan:

```csharp
// Lägg till grafobjekt till styckesamlingen för sidans instans
page.Paragraphs.Add(graph);
```

## Steg 8: Skapa en rektangelinstans

Definiera rektangelns position och storlek:

```csharp
// Skapa Rectangle-instans
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## Steg 9: Ange fyllningsfärgen

Välj en färg för din rektangel. I det här exemplet använder vi rött:

```csharp
// Ange fyllningsfärg för Graph-objekt
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Steg 10: Lägg till rektangeln i grafen

Lägg till rektangeln till grafen:

```csharp
// Lägg till rektangelobjekt till grafobjektets formsamling
graph.Shapes.Add(rect);
```

## Steg 11: Spara PDF-dokumentet

Slutligen, spara ditt dokument i den angivna katalogen:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
```

## Steg 12: Bekräftelsemeddelande

Skriv ut ett bekräftelsemeddelande för att indikera att det lyckades:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har skapat en fylld rektangel i ett PDF-dokument med Aspose.PDF för .NET. Detta kraftfulla bibliotek öppnar upp en värld av möjligheter för PDF-manipulation, vilket gör att du kan generera fantastiska dokument programmatiskt. Oavsett om du skapar rapporter, fakturor eller någon annan typ av PDF, har Aspose.PDF det du behöver.

## Vanliga frågor

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument programmatiskt.

### Kan jag använda Aspose.PDF gratis?
Ja, Aspose erbjuder en gratis testversion som du kan använda för att utforska bibliotekets funktioner. Du kan ladda ner den. [här](https://releases.aspose.com/).

### Finns det något sätt att få support för Aspose.PDF?
Absolut! Du kan få support via Aspose-forumet. [här](https://forum.aspose.com/c/pdf/10).

### Hur kan jag köpa Aspose.PDF?
Du kan köpa Aspose.PDF genom att besöka köpsidan [här](https://purchase.aspose.com/buy).

### Vilka typer av former kan jag skapa med Aspose.PDF?
Du kan skapa olika former, inklusive rektanglar, cirklar, linjer och mer, med hjälp av Aspose.PDF-biblioteket.