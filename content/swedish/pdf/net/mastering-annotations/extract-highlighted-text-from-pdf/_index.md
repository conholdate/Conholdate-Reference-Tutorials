---
"description": "Frigör potentialen i dina PDF-dokument genom att lära dig hur du extraherar markerad text med Aspose.PDF för .NET. Den här omfattande guiden guidar dig genom varje steg, från installation till implementering."
"linktitle": "Extrahera markerad text från PDF-filer med Aspose.PDF för .NET"
"second_title": "Aspose.PDF för .NET API-referens"
"title": "Extrahera markerad text från PDF-filer med Aspose.PDF för .NET"
"url": "/sv/pdf/net/mastering-annotations/extract-highlighted-text-from-pdf/"
"weight": 60
---

## Introduktion

När man arbetar med PDF-filer kan det vara viktigt att extrahera markerad text för dataanalys, innehållsgranskning eller organisering av anteckningar. Om du använder Aspose.PDF för .NET har du tur. Den här handledningen ger tydliga steg-för-steg-instruktioner om hur man effektivt extraherar markerad text från ett PDF-dokument.

## Förkunskapskrav

Innan du börjar, se till att du har följande på plats:

- Aspose.PDF för .NET-biblioteket: Ladda ner biblioteket från [släppsida](https://releases.aspose.com/pdf/net/).
- Utvecklingsmiljö: En arbetsmiljö som Visual Studio.
- Grundläggande kunskaper i C#: Bekantskap med C# och objektorienterad programmering är nödvändig.
- Aspose-licens: Även om du kan börja med en gratis provperiod, a [tillfällig licens](https://purchase.aspose.com/temporary-license/) eller en fullständig licens från [här](https://purchase.aspose.com/buy) kommer att ge obegränsad åtkomst.

## Importera nödvändiga namnrymder

Börja med att importera de namnrymder som krävs i ditt C#-projekt:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dessa namnrymder ger åtkomst till de klasser och metoder som behövs för att hantera PDF-dokument och anteckningar.

## Steg 1: Konfigurera din projektkatalog

Ange katalogen där din PDF-fil finns:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Se till att ersätta sökvägen med den faktiska katalogen för din PDF-fil.

## Steg 2: Ladda PDF-dokumentet

Ladda PDF-dokumentet med följande kod:

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

Se till att den angivna filen finns i den angivna katalogen.

## Steg 3: Få åtkomst till anteckningar på sidan

För att komma åt anteckningarna, bläddra igenom anteckningarna på önskad sida (i det här fallet den första sidan):

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
    if (annotation is TextMarkupAnnotation)
    {
        TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

Den här koden filtrerar efter `TextMarkupAnnotation` typer, som representerar höjdpunkter.

## Steg 4: Extrahera den markerade texten

Extrahera och visa nu texten från de markerade annoteringarna:

```csharp
        TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
        foreach (TextFragment tf in collection)
        {
            Console.WriteLine(tf.Text);
        }
    }
}
```

Detta hämtar alla markerade textfragment som är associerade med markeringen och skriver ut dem till konsolen.

## Slutsats

Att extrahera markerad text från en PDF med Aspose.PDF för .NET är enkelt och kan avsevärt förbättra din dokumenthanteringsprocess. Genom att följa stegen som beskrivs ovan kan du effektivt samla in markerad text för olika tillämpningar, till exempel rapportförberedelse eller dataanalys.

## Vanliga frågor

### Kan jag extrahera andra typer av annoteringar?
Ja, justera bara `if` villkor för att inkludera olika annoteringstyper som `TextAnnotation` eller `StampAnnotation`.

### Hur kan jag extrahera markerad text från alla PDF-sidor?
Du kan gå igenom alla sidor med hjälp av:
```csharp
for (int i = 1; i <= doc.Pages.Count; i++)
{
    foreach (Annotation annotation in doc.Pages[i].Annotations) { ... }
}
```

### Krävs en licens för Aspose.PDF för .NET?
En gratis provperiod är tillgänglig, men överväg en [tillfällig licens](https://purchase.aspose.com/temporary-license/) eller en fullständig licens för fullständig åtkomst.

### Kan jag spara den extraherade texten till en fil?
Absolut! Du kan modifiera koden för att skriva extraherad text till en textfil.

### Stöder Aspose.PDF andra plattformar?
Ja, Aspose.PDF stöder även Java och andra plattformar, vilket ger liknande funktioner.