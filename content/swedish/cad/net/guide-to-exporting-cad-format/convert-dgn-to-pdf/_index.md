---
"description": "Lär dig hur du enkelt konverterar DGN-filer till PDF med hjälp av det kraftfulla Aspose.CAD-biblioteket för .NET. Den här steg-för-steg-guiden är utformad för utvecklare på alla nivåer."
"linktitle": "Konvertera DGN till PDF i Aspose.CAD för .NET"
"second_title": "Aspose.CAD .NET - CAD- och BIM-filformat"
"title": "Konvertera DGN till PDF i Aspose.CAD för .NET"
"url": "/sv/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## Introduktion

Att navigera i CAD-filernas värld kan vara utmanande, men med Aspose.CAD för .NET kan utvecklare enkelt manipulera och konvertera olika CAD-format. Ett vanligt behov är att konvertera DGN-filer till PDF-filer, vilket vi kommer att utforska steg för steg i den här handledningen.

## Förkunskapskrav

För att följa med, se till att du har följande:

- Grundläggande kunskaper i C# och .NET framework.
- Aspose.CAD för .NET-biblioteket är installerat. Du kan ladda ner det. [här](https://releases.aspose.com/cad/net/).
- Ett exempel på DGN-fil (t.ex. Nikon_D90_Camera.dgn). 

## Steg 1: Importera obligatoriska namnrymder

Börja med att importera relevanta namnrymder i ditt C#-projekt:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Steg 2: Ladda DGN-filen

Ange katalogen för din DGN-fil och ladda den med följande kod:

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // Ytterligare bearbetning kommer att ske här...
}
```

## Steg 3: Konfigurera rasteriseringsalternativ

Konfigurera sedan rasteriseringsalternativen för att definiera hur ditt DGN ska renderas i PDF-filen:

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // Justera bredden efter behov
    PageHeight = 300, // Justera höjden efter behov
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## Steg 4: Skapa PDF-alternativ

Definiera PDF-alternativen och integrera de rasteriseringsinställningar som konfigurerats tidigare:

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Steg 5: Spara DGN-filen som PDF

Slutligen, spara DGN-filen som en PDF med de alternativ du har konfigurerat:

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## Slutsats

Grattis! Du har konverterat en DGN-fil till en PDF med Aspose.CAD för .NET. Den här enkla handledningen guidade dig genom att ladda DGN-filen, ställa in rasteriseringsalternativ och spara resultatet som en PDF.

## Vanliga frågor

### Behöver jag tidigare CAD-kunskaper för att använda Aspose.CAD?  
Absolut! Aspose.CAD är utformat för att förenkla komplexa CAD-uppgifter, vilket gör det tillgängligt för alla utvecklare, oavsett deras CAD-kunskaper.

### Var kan jag hitta fler resurser och dokumentation för Aspose.CAD?  
Du kan utforska omfattande guider och exempel i [Aspose.CAD-dokumentation](https://reference.aspose.com/cad/net/).

### Finns det en gratis provperiod för Aspose.CAD?  
Ja, en gratis provperiod kan erhållas [här](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.CAD?  
Du kan ansöka om tillfälliga licenser [här](https://purchase.conholdate.com/temporary-license/).

### Behöver du hjälp eller har du frågor?  
Delta i samtalet i [Aspose.CAD-forum](https://forum.aspose.com/c/cad/19) för samhällsstöd och förfrågningar.