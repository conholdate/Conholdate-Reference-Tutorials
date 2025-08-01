---
"description": "Ontdek de kracht van PDF-manipulatie met Aspose.PDF voor .NET in deze stapsgewijze tutorial. Leer hoe u programmatisch visueel aantrekkelijke PDF-documenten maakt door gevulde rechthoeken te tekenen."
"linktitle": "Een gevulde rechthoek maken"
"second_title": "Aspose.PDF voor .NET API-referentie"
"title": "Een gevulde rechthoek maken"
"url": "/nl/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## Invoering

Heb je ooit visueel verbluffende PDF's willen maken met behulp van programma's? Zo ja, dan ben je hier aan het juiste adres! In deze tutorial verkennen we Aspose.PDF voor .NET, een krachtige bibliotheek die het bewerken van PDF-documenten vereenvoudigt. Vandaag concentreren we ons op het maken van een gevulde rechthoek in een PDF-bestand. Of je nu een ervaren ontwikkelaar bent of net begint, deze handleiding leidt je op een vriendelijke en boeiende manier door elke stap. Dus, pak je programmeerhoed en laten we beginnen!

## Vereisten

Voordat we in de code duiken, moet u ervoor zorgen dat u het volgende hebt:

1. Visual Studio: Installeer Visual Studio op uw computer, want het is een uitstekende IDE voor .NET-ontwikkeling.
2. Aspose.PDF voor .NET: Download en installeer de Aspose.PDF-bibliotheek van [hier](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Kennis van C#-programmering helpt u de codefragmenten beter te begrijpen.

## Stap 1: Een nieuw project maken

1. Open Visual Studio en maak een nieuw Console Application-project.
2. Geef uw project een passende naam.

## Stap 2: Aspose.PDF-referentie toevoegen

1. Klik met de rechtermuisknop op uw project in Solution Explorer.
2. Selecteer NuGet-pakketten beheren.
3. Zoek naar Aspose.PDF en installeer de nieuwste versie.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nu we alles hebben ingesteld, kunnen we in de code duiken!

## Stap 3: Stel uw documentenmap in

Geef het pad op waar uw PDF moet worden opgeslagen:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Vervangen `"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad op uw computer waar u de PDF wilt opslaan.

## Stap 4: Een documentinstantie maken

Initialiseer een nieuw PDF-document:

```csharp
// Documentinstantie maken
Document doc = new Document();
```

## Stap 5: Een pagina toevoegen aan het document

Elke PDF heeft minimaal één pagina nodig. Laten we er één toevoegen:

```csharp
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Page page = doc.Pages.Add();
```

## Stap 6: Een grafiekinstantie maken

A `Graph` Het is een voorbeeld dat als canvas dient voor het tekenen van vormen:

```csharp
// Grafiekinstantie maken
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## Stap 7: Voeg de grafiek toe aan de pagina

Voeg de grafiek toe aan de pagina:

```csharp
// Grafiekobject toevoegen aan alineaverzameling van pagina-instantie
page.Paragraphs.Add(graph);
```

## Stap 8: Een rechthoekinstantie maken

Definieer de positie en grootte van de rechthoek:

```csharp
// Maak een rechthoekinstantie
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## Stap 9: Geef de vulkleur op

Kies een kleur voor je rechthoek. Voor dit voorbeeld gebruiken we rood:

```csharp
// Geef de vulkleur op voor het grafiekobject
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Stap 10: Voeg de rechthoek toe aan de grafiek

Voeg de rechthoek toe aan de grafiek:

```csharp
// Rechthoekig object toevoegen aan de vormencollectie van het grafiekobject
graph.Shapes.Add(rect);
```

## Stap 11: Sla het PDF-document op

Sla ten slotte uw document op in de opgegeven directory:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
```

## Stap 12: Bevestigingsbericht

Druk een bevestigingsbericht af om aan te geven dat de bewerking is geslaagd:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt met succes een gevulde rechthoek in een PDF-document gemaakt met Aspose.PDF voor .NET. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor PDF-bewerking, waardoor u programmatisch verbluffende documenten kunt genereren. Of u nu rapporten, facturen of andere PDF-bestanden maakt, Aspose.PDF biedt u de oplossing.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch PDF-documenten kunnen maken, bewerken en converteren.

### Kan ik Aspose.PDF gratis gebruiken?
Ja, Aspose biedt een gratis proefversie aan waarmee u de functies van de bibliotheek kunt verkennen. U kunt deze downloaden. [hier](https://releases.aspose.com/).

### Is er een manier om ondersteuning voor Aspose.PDF te krijgen?
Absoluut! Je kunt ondersteuning krijgen via het Aspose-forum. [hier](https://forum.aspose.com/c/pdf/10).

### Hoe kan ik Aspose.PDF kopen?
U kunt Aspose.PDF kopen door de aankooppagina te bezoeken [hier](https://purchase.aspose.com/buy).

### Welke soorten vormen kan ik maken met Aspose.PDF?
Met de Aspose.PDF-bibliotheek kunt u verschillende vormen maken, zoals rechthoeken, cirkels, lijnen en meer.