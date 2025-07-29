---
"description": "Upptäck hur du säkerställer ett enhetligt utseende på dina Word-dokument på olika plattformar genom att utnyttja målmaskinens teckensnitt med Aspose.Words för .NET."
"linktitle": "Målmaskinens teckensnitt"
"second_title": "Aspose.Words dokumentbehandlings-API"
"title": "Målmaskinfonter med Aspose.Words för .NET"
"url": "/sv/words/net/html-fixed-save-options/target-machine-font/"
"weight": 10
---

## Introduktion

Välkommen till Aspose.Words fascinerande värld för .NET! Idag ger vi oss ut på en resa för att utforska hur man använder teckensnitt från måldatorn när man arbetar med Word-dokument. Den här funktionen säkerställer att dina dokument behåller sitt avsedda utseende, oavsett var de visas. Nu kör vi!

## Förkunskapskrav

Innan vi börjar, se till att du har följande:

1. Aspose.Words för .NET: Se till att du har biblioteket installerat. Om du inte redan har gjort det kan du ladda ner det. [här](https://releases.aspose.com/words/net/).
2. Utvecklingsmiljö: En .NET-utvecklingsmiljö som Visual Studio är avgörande.
3. Dokument att arbeta med: Ha ett Word-dokument redo för testning, till exempel "Punkter med alternativt teckensnitt.docx".

Med dessa förutsättningar på plats, låt oss hoppa in i koden!

## Importera nödvändiga namnrymder

För att komma igång behöver vi importera de namnrymder som krävs. Detta steg kopplar samman alla komponenter i vårt projekt.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Steg 1: Ladda Word-dokumentet

Det första steget är att ladda ditt Word-dokument med hjälp av `Document` klass från Aspose.Words-biblioteket.

### Steg 1.1: Definiera dokumentsökvägen

Börja med att definiera sökvägen till din dokumentkatalog:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Steg 1.2: Ladda dokumentet

Ladda nu dokumentet:

```csharp
// Ladda Word-dokumentet
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

## Steg 2: Konfigurera sparalternativ

Nästa steg är att konfigurera sparalternativen för att säkerställa att teckensnitten som används i dokumentet kommer från måldatorn. Vi skapar en instans av `HtmlFixedSaveOptions` och ställ in `UseTargetMachineFonts` egendom till `true`.

```csharp
// Konfigurera sparalternativ för att använda teckensnitt från måldatorn
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
{
    UseTargetMachineFonts = true
};
```

## Steg 3: Spara dokumentet

Nu ska vi spara dokumentet som en fixerad HTML-fil. Det är här magin händer!

```csharp
// Konvertera dokument till fast HTML
doc.Save(dataDir + "UsingTargetMachineFonts.html", saveOptions);
```

## Steg 4: Verifiera utdata

Slutligen är det viktigt att verifiera resultatet. Öppna den sparade HTML-filen i en webbläsare för att kontrollera om teckensnitten är korrekt tillämpade från måldatorn.

```csharp
// Öppna HTML-filen för att verifiera utdata
System.Diagnostics.Process.Start(dataDir + "UsingTargetMachineFonts.html");
```

Och där har du det! Du har framgångsrikt använt teckensnitt från måldatorn i ditt Word-dokument med Aspose.Words för .NET.

## Slutsats

Genom att utnyttja teckensnitt från måldatorn säkerställer du att dina Word-dokument ser konsekventa och professionella ut, oavsett var de visas. Aspose.Words för .NET förenklar processen och låter dig enkelt ladda dokument, konfigurera sparalternativ och spara dem med önskade teckensnittsinställningar.

## Vanliga frågor

### Kan jag använda den här metoden med andra dokumentformat?
Ja, Aspose.Words för .NET stöder olika dokumentformat, och du kan använda liknande sparalternativ för olika format.

### Vad händer om måldatorn inte har de typsnitt som krävs?
Om de nödvändiga teckensnitten saknas på måldatorn kanske dokumentet inte återges korrekt. Det är lämpligt att bädda in teckensnitt vid behov.

### Hur bäddar jag in teckensnitt i ett dokument?
Du kan bädda in teckensnitt med hjälp av `FontSettings` klassen i Aspose.Words för .NET. Se [dokumentation](https://reference.aspose.com/words/net/) för mer information.

### Finns det något sätt att förhandsgranska dokumentet innan man sparar det?
Ja, den `DocumentRenderer` klassen låter dig förhandsgranska dokumentet innan du sparar. Kontrollera Aspose.Words för .NET [dokumentation](https://reference.aspose.com/words/net/) för mer information.

### Kan jag anpassa HTML-utdata ytterligare?
Absolut! Den `HtmlFixedSaveOptions` klassen tillhandahåller olika egenskaper för att anpassa HTML-utdata. Utforska [dokumentation](https://reference.aspose.com/words/net/) för alla tillgängliga alternativ.