---
"description": "Lär dig hur du implementerar optisk teckenigenkänning (OCR) i dina .NET-applikationer med Aspose.OCR. Den här omfattande guiden guidar dig genom processen att extrahera rektanglar för igenkända linjer."
"linktitle": "Extrahera linjerektanglar från bildigenkänning"
"second_title": "Aspose.OCR .NET API"
"title": "Extrahera linjerektanglar från bildigenkänning"
"url": "/sv/ocr/net/master-image-and-drawing-recognition/line-rectangles-from-images-recognition/"
"weight": 10
---

## Introduktion

Välkommen till Aspose.OCR för .NET, ett imponerande verktyg utformat för att integrera optisk teckenigenkänning (OCR) i dina .NET-applikationer. Oavsett om du är en erfaren utvecklare eller en nyfiken nykomling, kommer den här guiden att guida dig genom stegen för att få rektanglar som representerar linjer från tolkad text i bilder.

## Förkunskapskrav

Innan du börjar, se till att du har följande på plats:

- Grundläggande kunskaper i C# och .NET-utveckling.
- En integrerad utvecklingsmiljö (IDE) som Visual Studio.
- Aspose.OCR för .NET-biblioteket är installerat. Du kan ladda ner det. [här](https://releases.aspose.com/ocr/net/).
- En exempelbild som innehåller text för igenkänning.

## Obligatoriska namnrymder

För att börja måste du lägga till nödvändiga namnrymder i ditt projekt. Inkludera dessa rader högst upp i din C#-fil:

```csharp
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using Aspose.OCR;
```

Följ dessa steg för att hämta rektanglar för linjer i en OCR-bild.

## Steg 1: Konfigurera din dokumentkatalog

Ange katalogen där din bildfil finns:

```csharp
// Definiera sökvägen till din dokumentkatalog
string dataDir = "Your Document Directory";
```

Se till att byta ut `"Your Document Directory"` med den faktiska vägen.

## Steg 2: Initiera Aspose.OCR

Skapa en instans av `AsposeOcr` klass för att komma åt dess funktioner:

```csharp
// Initiera Aspose.OCR API:et
AsposeOcr api = new AsposeOcr();
```

## Steg 3: Ange bildsökvägen

Definiera den fullständiga sökvägen till bildfilen du vill bearbeta:

```csharp
// Ange den fullständiga sökvägen till bilden
string fullPath = dataDir + "sample.png";
```

## Steg 4: Identifiera bilden och hämta rektanglar för linjer

Nu kan du använda `GetRectangles` metod för att extrahera rektanglar av igenkända textrader:

```csharp
// Hämta rektanglar för linjer i den angivna bilden
List<Rectangle> lines = api.GetRectangles(fullPath, AreasType.LINES, false);
```

## Steg 5: Skriv ut resultaten

Slutligen, skriv ut koordinaterna för varje detekterad linjerektangel till konsolen:

```csharp
// Visa koordinaterna för de detekterade rektanglarna
Console.WriteLine("Areas coordinates:");
lines.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
```

## Slutsats

Grattis! Du har lyckats hämta rektanglar för linjer i en OCR-bild med hjälp av Aspose.OCR för .NET. Denna teknik öppnar upp många möjligheter för textutvinning och bearbetning i dina applikationer.

## Vanliga frågor

### Kan jag använda Aspose.OCR för .NET med vilken typ av bild som helst?

Ja, Aspose.OCR stöder olika bildformat, vilket ger flexibilitet för dina OCR-applikationer.

### Vilken är noggrannheten för OCR-igenkänning?

Aspose.OCR använder avancerade algoritmer för att uppnå hög noggrannhet i textigenkänning, lämplig för olika scenarier.

### Finns en testversion tillgänglig?

Ja, du kan utforska funktionerna i Aspose.OCR för .NET genom att ladda ner [gratis provperiod](https://releases.aspose.com/).

### Var kan jag hitta detaljerad dokumentation?

Omfattande dokumentation finns [här](https://reference.aspose.com/ocr/net/), som erbjuder djupgående information och riktlinjer.

### Behöver du ytterligare hjälp eller har du frågor?

Delta i diskussionen på [Aspose.OCR-forum](https://forum.aspose.com/c/ocr/16) för samhällsstöd.