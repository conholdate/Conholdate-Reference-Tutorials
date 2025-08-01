---
"description": "Lär dig steg för steg hur du bifogar filer och ställer in anpassade ikoner i Microsoft OneNote-dokument med Aspose.Note för .NET. Förbättra din .NET-applikation med sömlös dokumenthantering och anpassningsfunktioner."
"linktitle": "Bifoga fil och ange ikon i Aspose.Note"
"second_title": "Aspose.Note .NET API"
"title": "Bifoga filer och ställa in ikoner i Aspose.Note för .NET"
"url": "/sv/note/net/manage-attachments/attaching-files-setting-icons/"
"weight": 10
---

## Introduktion

Aspose.Note för .NET är ett avancerat bibliotek utformat för utvecklare för att skapa, manipulera och konvertera Microsoft OneNote-filer programmatiskt. En utmärkt funktion i detta bibliotek är dess möjlighet att bifoga filer till OneNote-dokument och anpassa deras ikoner. I den här guiden utforskar vi hur du kan använda Aspose.Note för .NET för att sömlöst bifoga filer och ställa in anpassade ikoner, vilket berikar dina OneNote-dokumentfunktioner.

## Förkunskapskrav

Innan du implementerar lösningen, se till att du har följande:

- Utvecklingsmiljö: Visual Studio eller en liknande IDE konfigurerad för .NET-utveckling.
- Biblioteksinstallation: Installera [Aspose.Note för .NET](https://releases.aspose.com/words/net/) bibliotek.
- Programmeringskunskaper: Grundläggande förståelse för C#.

## Importera obligatoriska namnrymder

Lägg till dessa namnrymder i ditt projekt för viktig funktionalitet:

```csharp
using System.IO;
using Aspose.Note;
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
```

Nedan följer den detaljerade steg-för-steg-implementeringen.

## Steg 1: Skapa ett nytt OneNote-dokument

Initiera ett nytt OneNote-dokument med hjälp av `Document` klass.

```csharp
Document doc = new Document();
```

## Steg 2: Lägg till en ny sida

Lägg till en sida i dokumentet för att organisera dina anteckningar och bilagor.

```csharp
Aspose.Note.Page page = new Aspose.Note.Page(doc);
```

## Steg 3: Skapa en disposition

Skapa en `Outline` objekt, som fungerar som behållare för element på din OneNote-sida.

```csharp
Outline outline = new Outline(doc);
```

## Steg 4: Initiera ett outline-element

En `OutlineElement` kommer att innehålla bilagan och dess tillhörande ikon.

```csharp
OutlineElement outlineElem = new OutlineElement(doc);
```

## Steg 5: Bifoga en fil och ange dess ikon

Ange filen som ska bifogas och ange en ikon för den.

```csharp
string dataDir = "Your Document Directory";

using (var stream = File.OpenRead(dataDir + "icon.jpg"))
{
    AttachedFile attachedFile = new AttachedFile(doc, dataDir + "attachment.txt", stream, ImageFormat.Jpeg);
    outlineElem.AppendChildLast(attachedFile);
}
```

## Steg 6: Montera dokumentstrukturen

Lägg till `OutlineElement` till `Outline`, och den `Outline` till `Page`.

```csharp
outline.AppendChildLast(outlineElem);
page.AppendChildLast(outline);
```

## Steg 7: Lägg till sidan i dokumentet

Slutligen, inkludera sidan i ditt OneNote-dokument.

```csharp
doc.AppendChildLast(page);
```

## Steg 8: Spara dokumentet

Exportera ditt uppdaterade dokument med den bifogade filen och ikonen.

```csharp
dataDir = dataDir + "AttachFileAndSetIcon_out.one";
doc.Save(dataDir);
```

## Slutsats

Genom att följa stegen som beskrivs i den här guiden kan du enkelt bifoga filer och ange anpassade ikoner i OneNote-dokument med Aspose.Note för .NET. Den här funktionen kan avsevärt förbättra dokumentorganisationen och användarupplevelsen, vilket gör dina applikationer mer robusta och funktionsrika.

## Vanliga frågor

### Kan flera filer bifogas till en och samma anteckning?
Ja, du kan bifoga flera filer genom att upprepa bifogningsprocessen för varje fil.

### Vilka bildformat stöds för ikoner?
Aspose.Note stöder JPEG-, PNG-, BMP- och GIF-format för ikoner för bilagor.

### Är det möjligt att bifoga filer dynamiskt från externa URL:er?
Du kan ladda ner filer med hjälp av .NET-bibliotek som `HttpClient` och bifoga dem sedan med Aspose.Note.

### Finns det några begränsningar för filstorleken för bilagor?
Aspose.Note har ingen explicit storleksgräns, men se till att dina systemresurser kan hantera stora filer.

### Kan ikoner ändra storlek innan de ställs in?
Ja, du kan manipulera ikonbilden med hjälp av .NET:s `System.Drawing` biblioteket innan du ansluter det.

För ytterligare hjälp, utforska [dokumentation](https://reference.aspose.com/words/net/) eller kontakta [Aspose-stöd](https://forum.aspose.com/c/words/8).