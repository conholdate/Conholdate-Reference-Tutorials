---
"description": "Lär dig hur du effektivt sparar Microsoft OneNote-dokument som PDF-filer med Aspose.Note för .NET. Den här guiden guidar dig genom de nödvändiga förutsättningarna och erbjuder användbara vanliga frågor."
"linktitle": "Spara OneNote-dokument i PDF-format"
"second_title": "Aspose.Note .NET API"
"title": "Spara OneNote-dokument i PDF med Aspose.Note för .NET"
"url": "/sv/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Introduktion

I den här handledningen utforskar vi hur man sparar dokument till PDF-format med Aspose.Note för .NET. Aspose.Note är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med Microsoft OneNote-filer programmatiskt. Vi går igenom förutsättningarna, importerar namnrymder och ger steg-för-steg-guider för att spara dokument till PDF i olika sidlayouter.

## Förkunskapskrav
1. Visual Studio: Se till att det är installerat.
2. Aspose.Note för .NET: Ladda ner och installera biblioteket.
3. C#-kunskaper: Grundläggande förståelse av språket krävs.

## Importera nödvändiga namnrymder
Innan du fortsätter, importera följande namnrymder i din kod:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Steg 1: Spara till PDF med brevsidans inställningar
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Uppdatera den här sökvägen
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Läser in OneNote-dokumentet och sparar det som en PDF med sidinställningar för Letter-storlek.

## Steg 2: Spara till PDF med A4-sidinställningar (ingen höjdgräns)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Uppdatera den här sökvägen
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Liknar steg 1 men använder A4-sidinställningar utan höjdbegränsningar.

## Slutsats
Handledningen visar framgångsrikt hur man konverterar OneNote-filer till PDF-format med Aspose.Note. Genom att använda olika sidinställningar får utvecklare flexibilitet i dokumenthanteringen.

## Vanliga frågor
### Kan Aspose.Note hantera komplexa OneNote-filer?
Ja, den hanterar effektivt olika funktioner i komplexa OneNote-filer.

### Är Aspose.Note lämplig för kommersiella projekt?
Ja, du kan använda den för kommersiella tillämpningar efter att du har köpt en licens.

### Erbjuder Aspose.Note en gratis provperiod?
Ja, en gratis provperiod är tillgänglig för utforskning.

### Var kan jag hitta dokumentation för Aspose.Note?
Detaljerad dokumentation finns tillgänglig på Asposes referenswebbplats.

### Behöver du ytterligare hjälp?
För frågor och support, se Aspose.Note-forumet.