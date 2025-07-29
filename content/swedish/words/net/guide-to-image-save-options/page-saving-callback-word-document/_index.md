---
"description": "Lär dig hur du enkelt konverterar varje sida i ett Word-dokument till individuella PNG-bilder med hjälp av Aspose.Words för .NET. Den här guiden innehåller steg-för-steg-instruktioner, inklusive kodexempel."
"linktitle": "Återuppringning av sidor i Word-dokument"
"second_title": "Aspose.Words dokumentbehandlings-API"
"title": "Återuppringning av sidor i Word-dokument"
"url": "/sv/words/net/guide-to-image-save-options/page-saving-callback-word-document/"
"weight": 10
---

## Introduktion

Har du någonsin behövt konvertera varje sida i ett Word-dokument till individuella bilder? Oavsett om du vill skapa miniatyrer för en förhandsvisning eller dela upp en lång rapport i lättförståeliga visuella element, gör Aspose.Words för .NET den här uppgiften enkel och effektiv. I den här guiden guidar vi dig genom processen att konfigurera en sidsparande återanrop för att spara varje sida i ditt dokument som en PNG-bild. Nu sätter vi igång!

## Förkunskapskrav

Innan du dyker in, se till att du har följande:

1. Aspose.Words för .NET: Ladda ner och installera det från [här](https://releases.aspose.com/words/net/).
2. Visual Studio: Alla versioner fungerar, men vi kommer att använda Visual Studio 2019 för den här guiden.
3. Grundläggande C#-kunskaper: Bekantskap med C# hjälper dig att följa processen smidigt.

## Steg 1: Importera nödvändiga namnrymder

Först måste vi importera de namnrymder som krävs. Detta gör att vi kan komma åt de nödvändiga klasserna och metoderna utan att behöva skriva hela namnrymden varje gång.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Steg 2: Definiera din dokumentkatalog

Ange sedan sökvägen till din dokumentkatalog. Det är här ditt Word-indatadokument finns och där utdatabilderna sparas.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Ladda ditt dokument

Nu ska vi ladda dokumentet du vill bearbeta. Se till att dokumentet, med namnet "Rendering.docx", finns i den angivna katalogen.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 4: Konfigurera alternativ för att spara bilder

Vi konfigurerar alternativen för att spara bilder och anger att vi vill spara sidorna som PNG-filer.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

Här, `PageSet` definierar sidintervallet som ska sparas, och `PageSavingCallback` pekar på vår anpassade callback-klass.

## Steg 5: Implementera återanropet för att spara sidan

Nu behöver vi implementera callback-klassen som hanterar hur varje sida sparas.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

Den här klassen implementerar `IPageSavingCallback` gränssnittet. I `PageSaving` Metoden anger vi namngivningsmönstret för varje sparad sida.

## Steg 6: Spara dokumentet som bilder

Slutligen sparar vi dokumentet med de konfigurerade alternativen.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Slutsats

Grattis! Du har konfigurerat en sidsparande återanropsfunktion för att spara varje sida i ett Word-dokument som en separat PNG-bild med hjälp av Aspose.Words för .NET. Den här tekniken är otroligt användbar för olika applikationer, från att skapa sidförhandsvisningar till att generera enskilda sidbilder för rapporter.

## Vanliga frågor

### Kan jag spara sidor i andra format än PNG?
Ja! Du kan spara sidor i format som JPEG, BMP och TIFF genom att ändra `SaveFormat` i `ImageSaveOptions`.

### Hur kan jag bara spara specifika sidor?
För att spara specifika sidor, justera `PageSet` parameter i `ImageSaveOptions` att endast inkludera de önskade sidorna.

### Är det möjligt att anpassa bildkvaliteten?
Absolut! Du kan styra bildkvaliteten genom att ställa in egenskaper som `ImageSaveOptions.JpegQuality`.

### Hur kan jag hantera stora dokument effektivt?
För stora dokument, överväg att bearbeta sidor i omgångar för att hantera minnesanvändningen effektivt.

### Var kan jag hitta mer information om Aspose.Words för .NET?
För omfattande guider och exempel, se [Aspose.Words-dokumentation](https://reference.aspose.com/words/net/).