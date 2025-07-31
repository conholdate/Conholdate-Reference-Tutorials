---
"description": "Upptäck hur du enkelt integrerar dokumentvisningsfunktioner i dina .NET-applikationer med GroupDocs.Viewer. Den här handledningen ger en omfattande steg-för-steg-guide."
"linktitle": "Ladda lösenordsskyddade dokument"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Läser in lösenordsskyddade dokument"
"url": "/sv/viewer/net/advanced-document-loading/loading-password-protected-document/"
"weight": 12
---

## Introduktion

det digitala landskapet är möjligheten att hantera och visa olika dokumentformat avgörande för företag och privatpersoner. GroupDocs.Viewer för .NET erbjuder en robust lösning för utvecklare för att enkelt integrera dokumentvisningsfunktioner i sina applikationer. Den här handledningen guidar dig genom processen att ladda lösenordsskyddade dokument steg för steg, vilket säkerställer att du kan implementera den här funktionen sömlöst i dina projekt.

## Förkunskapskrav

Innan vi börjar, se till att du har följande:

1. GroupDocs.Viewer för .NET installerat: Ladda ner det från [webbplats](https://releases.groupdocs.com/viewer/net/).
2. Lösenordsskyddat dokument: Ha ett lösenordsskyddat dokument redo för testning.

## Importera obligatoriska namnrymder

Börja med att importera de nödvändiga namnrymderna till ditt projekt:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Steg 1: Definiera utdatakatalogen

Ange var du vill att den renderade utdata ska sparas:

```csharp
string outputDirectory = "Your Document Directory";
```
Se till att byta ut `"Your Document Directory"` med den faktiska sökvägen du vill använda.

## Steg 2: Konfigurera sökvägsformat för sidfil

Definiera formatet för filsökvägarna för varje renderad sida:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Detta kommer att generera vägar som `"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`, etc.

## Steg 3: Konfigurera laddningsalternativ

Konfigurera inläsningsalternativen för ditt lösenordsskyddade dokument, inklusive lösenordet:

```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"  // Ersätt med ditt dokuments lösenord
};
```

## Steg 4: Initiera visaren

Skapa en instans av GroupDocs.Viewer med ditt dokument och laddningsalternativen:

```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // Kod för visningsalternativ läggs till i nästa steg.
}
```
Se till att byta ut `"Path_to_your_document"` med den faktiska sökvägen till ditt dokument.

## Steg 5: Konfigurera HTML-visningsalternativ

Konfigurera HTML-visningsalternativen för att rendera dokumentet med inbäddade resurser:

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Steg 6: Rendera dokumentet

Rendera nu dokumentet med hjälp av det konfigurerade visningsprogrammet och visningsalternativen:

```csharp
viewer.View(options);
```

## Steg 7: Visa ett meddelande om att det lyckades

Slutligen, informera användaren om att dokumentet har renderats:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats

den här handledningen utforskade vi hur man laddar lösenordsskyddade dokument med GroupDocs.Viewer för .NET. Genom att följa dessa steg kan utvecklare enkelt integrera den här funktionen i sina applikationer, vilket gör att användare enkelt kan visa skyddade dokument.

## Vanliga frågor

### Kan GroupDocs.Viewer hantera andra dokumentformat förutom lösenordsskyddade dokument?

Ja, GroupDocs.Viewer stöder ett brett utbud av format, inklusive PDF, DOCX, XLSX, PPTX och mer.

### Är GroupDocs.Viewer kompatibel med .NET Core?

Absolut! GroupDocs.Viewer är kompatibel med både .NET Framework- och .NET Core-miljöer.

### Kan jag anpassa renderingsalternativen för dokumenten?

Ja, GroupDocs.Viewer erbjuder olika renderingsalternativ, vilket gör att du kan skräddarsy visningsupplevelsen efter dina behov.

### Har GroupDocs.Viewer stöd för dokumentanteckningar?

Ja, det stöder dokumentanteckningar, vilket gör det möjligt för användare att lägga till kommentarer, markeringar och andra anteckningar.

### Finns det en testversion tillgänglig för GroupDocs.Viewer?

Ja, du kan få en gratis provperiod från [webbplats](https://releases.groupdocs.com/).