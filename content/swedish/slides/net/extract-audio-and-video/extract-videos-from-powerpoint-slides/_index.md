---
"description": "Upptäck hur du enkelt extraherar inbäddade videofiler från PowerPoint-presentationer med Aspose.Slides för .NET. Den här omfattande steg-för-steg-guiden täcker allt från att konfigurera din miljö till att spara de extraherade videorna."
"linktitle": "Extrahera videor från PowerPoint-bilder"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Extrahera videor från PowerPoint-bilder med Aspose.Slides"
"url": "/sv/slides/net/extract-audio-and-video/extract-videos-from-powerpoint-slides/"
"weight": 14
---

## Introduktion

Aspose.Slides för .NET är ett kraftfullt bibliotek som låter utvecklare interagera med PowerPoint-presentationer programmatiskt. I den här guiden går vi igenom processen att extrahera videor inbäddade i PowerPoint-bilder med hjälp av Aspose.Slides för .NET. 

## Förkunskapskrav

Innan du börjar, se till att du har följande:

- Aspose.Slides för .NET: Hämta och installera biblioteket från [Aspose webbplats](https://purchase.aspose.com/buy).
- PowerPoint-presentation: Förbered en PowerPoint-fil (t.ex. `Video.pptx`) med videon du vill extrahera.

## Nödvändiga namnrymder

För att arbeta med Aspose.Slides för .NET måste du importera lämpliga namnrymder. Inkludera följande i din kod:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

## Steg 1: Ange dokumentkatalogen

Först, definiera sökvägen till din PowerPoint-presentation:

```csharp
string dataDir = "Your Document Directory";
```

Ersätta `"Your Document Directory"` med den faktiska sökvägen till katalogen som innehåller din PowerPoint-fil.

## Steg 2: Ladda presentationen

Ladda PowerPoint-presentationen till en `Presentation` objekt:

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Detta initierar `Presentation` objektet med din angivna PowerPoint-fil.

## Steg 3: Iterera genom bilder och former

Gå sedan igenom varje bild i presentationen och kontrollera om det finns några bildrutor:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in slide.Shapes)
    {
        if (shape is VideoFrame videoFrame)
        {
            // Fortsätt med att extrahera videon
        }
    }
}
```

## Steg 4: Extrahera videodata

När du hittat en videobildruta, extrahera dess egenskaper och binära data:

```csharp
IVideoFrame vf = (IVideoFrame)shape;  // Lagra formen som en videobildruta
string contentType = vf.EmbeddedVideo.ContentType;
Byte[] buffer = vf.EmbeddedVideo.BinaryData;

// Hämta filändelsen
string fileExtension = contentType.Substring(contentType.LastIndexOf('/') + 1);
```

## Steg 5: Spara videon

Slutligen, skriv den extraherade videodatan till en fil:

```csharp
using (FileStream stream = new FileStream(dataDir + "ExtractedVideo." + fileExtension, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Den här koden skapar en ny fil i din angivna katalog och skriver videodatan till den.

## Slutsats

Med Aspose.Slides för .NET är det enkelt att extrahera videor från PowerPoint-bilder. Genom att följa den här guiden kan du enkelt hantera multimediainnehåll i dina .NET-applikationer, vilket berikar användarupplevelsen och funktionaliteten.

## Vanliga frågor

### Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett bibliotek utformat för att fungera med PowerPoint-presentationer, vilket gör det möjligt för användare att skapa, redigera och manipulera presentationsfiler programmatiskt.

### Var kan jag hitta dokumentationen för Aspose.Slides för .NET?
Du kan få tillgång till hela dokumentationen [här](https://reference.aspose.com/slides/net/).

### Finns Aspose.Slides för .NET tillgänglig för en gratis provperiod?
Ja, du kan ladda ner en gratis testversion från [den här länken](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Slides för .NET?
Ansökningar om tillfälliga licenser kan göras [här](https://purchase.aspose.com/temporary-license/).

### Var kan jag få support för Aspose.Slides för .NET?
Stöd finns tillgängligt via [Aspose.Slides-forum](https://forum.aspose.com/).