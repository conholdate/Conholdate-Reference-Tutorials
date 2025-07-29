---
"description": "Haal het maximale uit uw PDF-documenten door te leren hoe u gemarkeerde tekst kunt extraheren met Aspose.PDF voor .NET. Deze uitgebreide handleiding begeleidt u bij elke stap, van installatie tot implementatie."
"linktitle": "Gemarkeerde tekst uit PDF's extraheren met Aspose.PDF voor .NET"
"second_title": "Aspose.PDF voor .NET API-referentie"
"title": "Gemarkeerde tekst uit PDF's extraheren met Aspose.PDF voor .NET"
"url": "/nl/pdf/net/mastering-annotations/extract-highlighted-text-from-pdf/"
"weight": 60
---

## Invoering

Bij het werken met PDF-bestanden kan het extraheren van gemarkeerde tekst essentieel zijn voor gegevensanalyse, inhoudsbeoordeling of het ordenen van notities. Als u Aspose.PDF voor .NET gebruikt, hebt u geluk. Deze tutorial biedt duidelijke, stapsgewijze instructies voor het efficiënt extraheren van gemarkeerde tekst uit een PDF-document.

## Vereisten

Zorg ervoor dat u het volgende geregeld hebt voordat u begint:

- Aspose.PDF voor .NET-bibliotheek: Download de bibliotheek van de [releasepagina](https://releases.aspose.com/pdf/net/).
- Ontwikkelomgeving: Een werkomgeving zoals Visual Studio.
- Basiskennis van C#: Kennis van C# en objectgeoriënteerd programmeren is noodzakelijk.
- Aspose-licentie: Hoewel u kunt beginnen met een gratis proefperiode, [tijdelijke licentie](https://purchase.aspose.com/temporary-license/) of een volledige licentie van [hier](https://purchase.aspose.com/buy) biedt onbeperkte toegang.

## Importeer noodzakelijke naamruimten

Begin met het importeren van de vereiste naamruimten in uw C#-project:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Deze naamruimten bieden toegang tot de klassen en methoden die nodig zijn voor het verwerken van PDF-documenten en -annotaties.

## Stap 1: Stel uw projectmap in

Geef de map op waar uw PDF-bestand zich bevindt:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Zorg ervoor dat u het pad vervangt door de werkelijke map van uw PDF-bestand.

## Stap 2: Het PDF-document laden

Laad het PDF-document met de volgende code:

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

Zorg ervoor dat het opgegeven bestand in de opgegeven map staat.

## Stap 3: Toegang tot annotaties op de pagina

Om toegang te krijgen tot de annotaties, bladert u door de annotaties op de gewenste pagina (in dit geval de eerste pagina):

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
    if (annotation is TextMarkupAnnotation)
    {
        TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

Deze code filtert op `TextMarkupAnnotation` typen, die hoogtepunten vertegenwoordigen.

## Stap 4: De gemarkeerde tekst extraheren

Haal nu de tekst uit de gemarkeerde annotaties en geef deze weer:

```csharp
        TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
        foreach (TextFragment tf in collection)
        {
            Console.WriteLine(tf.Text);
        }
    }
}
```

Hiermee worden alle gemarkeerde tekstfragmenten die aan de markering zijn gekoppeld, opgehaald en op de console afgedrukt.

## Conclusie

Het extraheren van gemarkeerde tekst uit een PDF met Aspose.PDF voor .NET is eenvoudig en kan uw documentverwerkingsproces aanzienlijk verbeteren. Door de bovenstaande stappen te volgen, kunt u efficiënt gemarkeerde tekst verzamelen voor diverse toepassingen, zoals rapportvoorbereiding of data-analyse.

## Veelgestelde vragen

### Kan ik andere typen annotaties extraheren?
Ja, pas eenvoudig de `if` voorwaarde om verschillende annotatietypen op te nemen, zoals `TextAnnotation` of `StampAnnotation`.

### Hoe kan ik gemarkeerde tekst uit alle PDF-pagina's halen?
U kunt door alle pagina's bladeren met behulp van:
```csharp
for (int i = 1; i <= doc.Pages.Count; i++)
{
    foreach (Annotation annotation in doc.Pages[i].Annotations) { ... }
}
```

### Is een licentie nodig voor Aspose.PDF voor .NET?
Er is een gratis proefperiode beschikbaar, maar overweeg een [tijdelijke licentie](https://purchase.aspose.com/temporary-license/) of een volledige licentie voor volledige toegang.

### Kan ik de geëxtraheerde tekst in een bestand opslaan?
Absoluut! Je kunt de code aanpassen om geëxtraheerde tekst naar een tekstbestand te schrijven.

### Ondersteunt Aspose.PDF andere platforms?
Ja, Aspose.PDF ondersteunt ook Java en andere platforms en biedt vergelijkbare functionaliteit.