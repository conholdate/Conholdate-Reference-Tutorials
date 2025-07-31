---
"description": "Upptäck hur du kan förbättra dina Excel-dokument genom att programmatiskt anpassa sidhuvuden och sidfot med Aspose.Cells för .NET. Den här omfattande guiden guidar dig genom varje steg – från att konfigurera din arbetsbok till att dynamiskt infoga kalkylbladets namn."
"linktitle": "Implementera sidhuvud och sidfot med Aspose.Cells för .NET"
"second_title": "Aspose.Cells .NET Excel-bearbetnings-API"
"title": "Implementera sidhuvud och sidfot med Aspose.Cells för .NET"
"url": "/sv/cells/net/mastering-worksheet-page-setup-features/implement-header-footer/"
"weight": 22
---

## Introduktion

Sidhuvuden och sidfot är viktiga element i Excel-kalkylblad och ger viktig kontextuell information som filnamn, datum och sidnummer. Oavsett om du automatiserar rapporter eller genererar dynamiska filer förenklar Aspose.Cells för .NET processen att anpassa sidhuvuden och sidfot programmatiskt. Den här guiden erbjuder en steg-för-steg-metod för att förbättra dina Excel-filer med polerade och professionella sidhuvuden och sidfot.

## Förkunskapskrav

Innan du dyker in, se till att du har följande:

1. Aspose.Cells för .NET: Ladda ner och installera det från [här](https://releases.aspose.com/cells/net/).
2. IDE-konfiguration: Använd Visual Studio eller din föredragna IDE med .NET Framework.
3. Licens: Börja med en gratis provperiod, men överväg att skaffa en fullständig eller tillfällig licens för fullständig funktionalitet. Du kan [få en tillfällig licens](https://purchase.aspose.com/temporary-license/).

## Importera nödvändiga paket

Börja med att importera de nödvändiga namnrymderna i ditt projekt:

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

Detta ger dig tillgång till de klasser och metoder som behövs för att arbeta med sidhuvuden, sidfot och andra Excel-funktioner i Aspose.Cells.

## Steg 1: Skapa en arbetsbok och få åtkomst till utskriftsformat

Börja med att skapa en ny arbetsbok och öppna arbetsbladets sidinställningar. Det är här du ändrar inställningarna för sidhuvud och sidfot.

```csharp
// Definiera sökvägen för att spara dokumentet
string dataDir = "Your Document Directory";

// Instansiera ett arbetsboksobjekt
Workbook excel = new Workbook();
```

Här, en `Workbook` objektet representerar din Excel-fil. `PageSetup` Med egenskapen "Sidhuvuden och sidfot" kan du anpassa kalkylbladet.

## Steg 2: Åtkomst till egenskaperna för kalkylblad och sidinställningar

Varje kalkylblad i Aspose.Cells har en `PageSetup` egenskap som styr layoutfunktioner, inklusive sidhuvuden och sidfot. Hämta `PageSetup` objekt för ditt kalkylblad:

```csharp
// Hämta referensen till sidinställningarna för det första kalkylbladet
PageSetup pageSetup = excel.Worksheets[0].PageSetup;
```

Nu, `pageSetup` innehåller de inställningar som krävs för att anpassa sidhuvuden och sidfot.

## Steg 3: Ställ in den vänstra delen av rubriken

Rubriker består av tre sektioner: vänster, mitten och höger. Låt oss börja med att ställa in den vänstra sektionen för att visa kalkylbladets namn.

```csharp
// Ange kalkylbladets namn i vänster del av sidhuvudet
pageSetup.SetHeader(0, "&A");
```

Användning `&A` visar dynamiskt kalkylbladets namn, vilket är särskilt användbart för arbetsböcker med flera ark.

## Steg 4: Lägg till datum och tid i mitten av rubriken

Lägg sedan till aktuellt datum och tid i mitten av sidhuvudet och använd ett anpassat teckensnitt för styling.

```csharp
// Ange datum och tid i mitten av rubriken med fetstil
pageSetup.SetHeader(1, "&\"Times New Roman,Bold\"&D-&T");
```

I den här raden:
- `&D` infogar aktuellt datum.
- `&T` infogar aktuell tid.
- `"Times New Roman,Bold"` använder ett fetstilsatt teckensnitt Times New Roman.

## Steg 5: Visa filnamnet i den högra delen av rubriken

För att komplettera rubriken, visa filnamnet på höger sida med en angiven teckenstorlek.

```csharp
// Visa filnamnet i högra delen av rubriken med anpassad teckenstorlek
pageSetup.SetHeader(2, "&\"Times New Roman,Bold\"&12&F");
```

Här, `&F` representerar filnamnet, och `&12` ställer in teckenstorleken till 12.

## Steg 6: Lägg till anpassad text i vänster sidfot

Nu ska vi ställa in vänster sidfotssektion med anpassad text och ett specifikt teckensnitt.

```csharp
// Lägg till anpassad text med teckensnittsstil i vänster del av sidfoten
pageSetup.SetFooter(0, "Hello World! &\"Courier New\"&14 123");
```

I det här exemplet, texten `123` är formaterad med teckensnittet "Courier New" i storlek 14, medan resten förblir med standardteckensnittet för sidfoten.

## Steg 7: Infoga sidnummer i mitten av sidfoten

Att inkludera sidnummer i sidfoten hjälper läsarna att spåra dokument med flera sidor.

```csharp
// Infoga sidnummer i mitten av sidfoten
pageSetup.SetFooter(1, "&P");
```

De `&P` Koden lägger till det aktuella sidnumret i sidfotens mittsektion.

## Steg 8: Visa totalt antal sidor i högersidfoten

Komplettera sidfoten genom att visa det totala sidantalet i den högra sektionen.

```csharp
// Visa totalt antal sidor i högra delen av sidfoten
pageSetup.SetFooter(2, "&N");
```

De `&N` Koden anger det totala antalet sidor och informerar läsarna om dokumentets längd.

## Steg 9: Spara arbetsboken

Spara slutligen arbetsboken för att generera en Excel-fil med de anpassade sidhuvudena och sidfötterna.

```csharp
// Spara arbetsboken
excel.Save(dataDir + "SetHeadersAndFooters_out.xls");
```

Den här raden sparar filen med dina anpassningar på plats.

## Slutsats

Att anpassa sidhuvuden och sidfot i Excel-kalkylblad förbättrar professionalismen i dina dokument. Med Aspose.Cells för .NET kan du enkelt kontrollera dessa element, från att visa kalkylbladsnamn till att infoga anpassad text, datum, tider och dynamiska sidnummer. Nu när du har lärt dig stegen kan du förbättra dina Excel-automatiseringsprojekt.

## Vanliga frågor

### Kan jag använda olika teckensnitt för olika delar av sidhuvuden och sidfoten?
Ja, Aspose.Cells låter dig ange unika teckensnitt för varje del av sidhuvudet och sidfoten.

### Hur tar jag bort sidhuvuden och sidfot?
Rensa sidhuvuden och sidfot genom att ställa in deras text som en tom sträng med hjälp av `SetHeader` eller `SetFooter`.

### Kan jag infoga bilder i sidhuvuden eller sidfoten med Aspose.Cells för .NET?
För närvarande stöder Aspose.Cells främst text i sidhuvuden och sidfot. Bilder kan kräva alternativa metoder, som att infoga dem direkt i kalkylbladet.

### Stöder Aspose.Cells dynamisk data i sidhuvuden och sidfot?  
Ja, du kan använda olika dynamiska koder (som `&D` för datum eller `&P` för sidnummer) för att lägga till dynamiskt innehåll.

### Hur kan jag justera höjden på sidhuvudet eller sidfoten?  
Aspose.Cells erbjuder alternativ inom `PageSetup` klass för att justera marginalerna för sidhuvud och sidfot, vilket ger dig kontroll över avståndet.