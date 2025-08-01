---
"description": "Upptäck hur du smidigt konverterar XPS-dokument (XML Paper Specification) till PDF (Portable Document Format) med hjälp av det kraftfulla Aspose.Page för .NET-biblioteket."
"linktitle": "Konvertera XPS till PDF"
"second_title": "Aspose.Page .NET API"
"title": "Konvertera XPS till PDF med Aspose.Page för .NET"
"url": "/sv/page/net/convert-document/converting-xps-to-pdf/"
"weight": 11
---

## Introduktion

I den här handledningen ska vi utforska hur man konverterar XPS-dokument (XML Paper Specification) till PDF (Portable Document Format) med hjälp av det mångsidiga Aspose.Page för .NET-biblioteket. Detta kraftfulla bibliotek förenklar dokumentkonvertering och erbjuder olika anpassningsalternativ, vilket gör det till ett utmärkt val för utvecklare.

## Förkunskapskrav

Innan vi börjar, se till att du har följande på plats:

- Aspose.Page för .NET-biblioteket: Ladda ner och installera Aspose.Page för .NET-biblioteket från [Aspose.Page-dokumentation](https://reference.aspose.com/page/net/).
  
- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö med Visual Studio eller en annan kompatibel IDE.

- XPS-dokument: Ha XPS-filen du vill konvertera redo, lagrad i en angiven katalog.

## Steg 1: Importera obligatoriska namnrymder

Börja med att importera det namnutrymme som krävs för att komma åt Aspose.Page-funktionerna:

```csharp
using Aspose.Page.XPS;
```

## Steg 2: Initiera dokumentkatalogen

Definiera sökvägen till katalogen där dina dokument lagras:

```csharp
string dataDir = "Your Document Directory";
```

Se till att byta ut `"Your Document Directory"` med den faktiska sökvägen till katalogen som innehåller ditt XPS-dokument.

### Steg 3: Öppna PDF- och XPS-strömmar

Initiera sedan strömmar för både inmatnings-XPS-filen och utmatnings-PDF-filen:

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Se till att du har angett rätt sökväg för dina filer.

### Steg 4: Ladda XPS-dokumentet

Ladda nu ditt XPS-dokument med hjälp av Aspose.Page-biblioteket:

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Steg 5: Konfigurera PDF-sparalternativ

Konfigurera sparalternativen för din PDF, inklusive bildkvalitet och komprimeringsparametrar:

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100, // Ställ in JPEG-kvalitetsnivån
    ImageCompression = PdfImageCompression.Jpeg, // Använd JPEG-komprimering för bilder
    TextCompression = PdfTextCompression.Flate, // Använd Flate-komprimering för text
    PageNumbers = new int[] { 1, 2, 6 } // Ange sidnummer som ska inkluderas
};
```

Justera gärna dessa parametrar efter dina behov.

### Steg 6: Skapa PDF-renderingsenheten

Skapa en renderingsenhet för PDF-formatet:

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Steg 7: Spara dokumentet som PDF

Slutligen, spara XPS-dokumentet till PDF med den angivna enheten och alternativen:

```csharp
document.Save(device, options);
```

## Slutsats

Grattis! Du har framgångsrikt konverterat ett XPS-dokument till PDF med Aspose.Page för .NET. Det här biblioteket förenklar inte bara dokumentkonvertering utan erbjuder också omfattande funktioner för att hantera olika format.

## Vanliga frågor

### Kan jag konvertera flera XPS-filer till en enda PDF?

Absolut! Du kan gå igenom flera XPS-filer och sammanfoga dem till ett enda PDF-dokument genom att följa samma konverteringssteg.

### Vilka andra utdataformat stöder Aspose.Page för .NET?

Förutom PDF stöder Aspose.Page för .NET en rad andra format, inklusive TIFF, JPEG och PNG.

### Hur kan jag anpassa utseendet på den konverterade PDF-filen?

Du kan justera parametrarna i `PdfSaveOptions` objekt, såsom JPEG-kvalitet och komprimeringsinställningar, för att uppnå önskat utseende.

### Finns det en testversion tillgänglig för Aspose.Page för .NET?

Ja, du kan prova Aspose.Page för .NET med en gratis provperiod tillgänglig [här](https://releases.aspose.com/).

### Var kan jag hitta community-support för Aspose.Page för .NET?

För diskussioner och stöd i samhället, besök [Aspose.Page-forum](https://forum.aspose.com/c/page/39).