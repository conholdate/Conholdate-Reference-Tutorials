---
"description": "Lär dig hur du använder Aspose.Words för .NET för att skriva alla CSS-regler till en enda fil när du sparar dokument med HtmlFixedSaveOptions. Följ den här detaljerade handledningen för steg-för-steg-vägledning."
"linktitle": "Skriv alla CSS-regler i en enda fil"
"second_title": "Aspose.Words dokumentbehandlings-API"
"title": "Spara alla CSS-regler i en enda fil"
"url": "/sv/words/net/html-fixed-save-options/save-all-css-rules-in-single-file/"
"weight": 10
---

## Introduktion

Har du någonsin kämpat med en rörig samling CSS-regler när du konverterar Word-dokument till HTML? Du är inte ensam! Som tur är erbjuder Aspose.Words för .NET en kraftfull funktion som låter dig konsolidera alla dina CSS-regler till en enda fil. Detta rensar inte bara upp din kod utan förenklar också ditt arbetsflöde. Låt oss ge oss ut på en resa mot renare och effektivare HTML-utdata!

## Förkunskapskrav

Innan vi går in i kodningen, se till att du har följande:

1. Aspose.Words för .NET: Hämta biblioteket från [här](https://releases.aspose.com/words/net/).
2. .NET-utvecklingsmiljö: En installation som Visual Studio är idealisk för utveckling.
3. Grundläggande C#-kunskaper: Bekantskap med C# hjälper dig att navigera i koden.
4. Word-dokument: Ha en .docx-fil redo för konvertering.

## Importera namnrymder

Först och främst, låt oss importera de nödvändiga namnrymderna i ditt C#-projekt. Detta gör att vi enkelt kan komma åt Aspose.Words-funktionerna.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Låt oss dela upp den här processen i hanterbara steg för att säkerställa en smidig konvertering.

## Steg 1: Konfigurera din dokumentkatalog

Först, fastställ katalogsökvägen där ditt Word-dokument finns och var den konverterade HTML-koden ska sparas.

```csharp
// Definiera sökvägen till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda Word-dokumentet

Ladda sedan Word-dokumentet med hjälp av `Document` klass från Aspose.Words-biblioteket.

```csharp
// Ladda Word-dokumentet
Document doc = new Document(dataDir + "Document.docx");
```

## Steg 3: Konfigurera HTML-sparalternativ

Nu ska vi konfigurera HTML-sparalternativen. Vi vill aktivera funktionen som konsoliderar alla CSS-regler till en enda fil genom att ställa in `SaveFontFaceCssSeparately` till `false`.

```csharp
// Konfigurera HTML-sparalternativ för att skriva alla CSS-regler i en fil
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions 
{ 
    SaveFontFaceCssSeparately = false 
};
```

## Steg 4: Konvertera dokument till HTML

Spara slutligen dokumentet som en HTML-fil med de angivna alternativen. Detta säkerställer att alla CSS-regler är prydligt organiserade i en enda fil.

```csharp
// Konvertera dokumentet till HTML
doc.Save(dataDir + "ConvertedDocument.html", saveOptions);
```

## Slutsats

Grattis! Med bara några få rader kod har du konverterat ditt Word-dokument till HTML, vilket säkerställer att alla CSS-regler är prydligt sammanställda i en enda fil. Denna metod förenklar CSS-hanteringen och förbättrar underhållbarheten för dina HTML-dokument. Nästa gång du behöver konvertera ett Word-dokument har du en effektiv process nära till hands!

## Vanliga frågor

### Varför ska jag använda en enda CSS-fil för min HTML-utdata?
En enda CSS-fil förenklar stilhanteringen, vilket gör din HTML renare och effektivare att underhålla.

### Kan jag separera CSS-regler för teckensnitt om det behövs?
Absolut! Genom att ställa in `SaveFontFaceCssSeparately` till `true`, kan du separera CSS-regler för teckensnitt i en annan fil.

### Är Aspose.Words för .NET gratis att använda?
Aspose.Words erbjuder en gratis provversion tillgänglig för nedladdning [här](https://releases.aspose.com/)För fortsatt användning, överväg att köpa en licens [här](https://purchase.aspose.com/buy).

### Vilka andra format kan Aspose.Words för .NET konvertera till?
Aspose.Words stöder olika format, inklusive PDF, TXT och bildformat som JPEG och PNG.

### Var kan jag hitta fler resurser om Aspose.Words för .NET?
För omfattande guider och API-referenser, kolla in [dokumentation](https://reference.aspose.com/words/net/).