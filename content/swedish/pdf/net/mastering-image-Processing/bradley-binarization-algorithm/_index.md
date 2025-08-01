---
"description": "Lär dig hur du konverterar PDF-sidor till högkvalitativa binära TIFF-bilder med hjälp av Bradleys binäriseringsalgoritm i Aspose.PDF för .NET. Den här steg-för-steg-guiden innehåller ett kodexempel."
"linktitle": "Bradley binariseringsalgoritm"
"second_title": "Aspose.PDF för .NET API-referens"
"title": "Bradley binariseringsalgoritm"
"url": "/sv/pdf/net/mastering-image-Processing/bradley-binarization-algorithm/"
"weight": 30
---

## Introduktion

I den här handledningen guidar vi dig genom processen att konvertera en PDF-sida till en TIFF-bild med hjälp av Bradley Binarization Algorithm. Aspose.PDF för .NET förenklar denna uppgift och låter dig automatisera och effektivisera dina dokumentarbetsflöden med lätthet.

## Förkunskapskrav

Innan vi börjar, se till att du har följande:

- Aspose.PDF för .NET: Ladda ner biblioteket från [här](https://releases.aspose.com/pdf/net/).
- Visual Studio (eller valfri C# IDE).
- Grundläggande kunskaper i C#.
- En giltig licens eller en [tillfällig licens](https://purchase.aspose.com/temporary-license/) från Aspose.

## Steg 1: Konfigurera ditt projekt

Skapa först ett nytt C#-projekt i din IDE och importera de nödvändiga namnrymderna:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

## Steg 2: Definiera dokumentkatalogen

Ange sökvägen till katalogen där ditt PDF-dokument finns, samt utdatasökvägarna för TIFF-bilderna:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Sökväg till din PDF-fil
```

Den här katalogen lagrar både käll-PDF-filen och de konverterade TIFF-filerna.

## Steg 3: Ladda PDF-dokumentet

Öppna PDF-dokumentet du vill konvertera:

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

Ersätta `PageToTIFF.pdf` med namnet på din PDF-fil.

## Steg 4: Ange utdatavägar

Definiera utdatasökvägarna för de genererade TIFF-filerna:

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Steg 5: Ställ in bildupplösning

Ställ in upplösningen för TIFF-bilderna. En högre DPI ger bättre bildkvalitet:

```csharp
Resolution resolution = new Resolution(300);
```

## Steg 6: Konfigurera TIFF-inställningar

Konfigurera inställningarna för TIFF-bilden, inklusive komprimering och färgdjup:

```csharp
TiffSettings tiffSettings = new TiffSettings
{
    Compression = CompressionType.LZW,
    Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp
};
```

Genom att använda 1 bpp (1 bit per pixel) förbereds bilden för binär utdata.

## Steg 7: Skapa TIFF-enheten

Skapa en TIFF-enhet som hanterar konverteringen:

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Steg 8: Konvertera PDF-sidan till TIFF

Konvertera den första sidan av PDF-filen till en TIFF-bild:

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Steg 9: Tillämpa Bradleys binäriseringsalgoritm

Använd nu Bradley-algoritmen för att konvertera gråskale-TIFF-bilden till en binär bild:

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

De `BinarizeBradley` Metoden tar två filströmmar (indata och utdata) och ett tröskelvärde. Justera tröskelvärdet efter behov för optimala resultat.

## Steg 10: Bekräfta lyckad konvertering

Bekräfta slutligen att konverteringen lyckades:

```csharp
Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

## Slutsats

Grattis! Du har framgångsrikt konverterat en PDF-sida till en TIFF-bild och tillämpat Bradley Binarization Algorithm med Aspose.PDF för .NET. Denna process är avgörande för dokumentarkivering, OCR och andra professionella tillämpningar. Med hög upplösning och effektiv komprimering kommer dina dokumentbilder att vara tydliga och hanterbara i storlek.

## Vanliga frågor

### Vad är Bradley-algoritmen?
Bradley-algoritmen är en binäriseringsteknik som omvandlar gråskalebilder till binära bilder genom att bestämma ett adaptivt tröskelvärde för varje pixel baserat på dess omgivning.

### Kan jag konvertera flera PDF-sidor till TIFF med den här metoden?
Ja, du kan ändra `Process` metod för att loopa igenom alla sidor i dokumentet för konvertering.

### Vilken är den optimala upplösningen för att konvertera PDF-filer till TIFF?
En upplösning på 300 DPI rekommenderas generellt för bilder av hög kvalitet, men du kan justera detta baserat på dina specifika behov.

### Vad betyder 1 bpp i färgdjup?
bpp (1 bit per pixel) indikerar att bilden kommer att vara i svartvitt, där varje pixel antingen är helt svart eller helt vit.

### Är Bradley-algoritmen lämplig för OCR?
Ja, Bradley-algoritmen används ofta i OCR-förbehandling eftersom den förbättrar textkontrasten i skannade dokument, vilket förbättrar igenkänningsnoggrannheten.