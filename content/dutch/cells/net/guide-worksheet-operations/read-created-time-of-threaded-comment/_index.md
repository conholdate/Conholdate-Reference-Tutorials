---
"description": "Leer hoe u eenvoudig de aanmaaktijd van opmerkingen in een Excel-werkblad kunt aflezen met Aspose.Cells voor .NET. Volg onze gedetailleerde handleiding met stapsgewijze instructies."
"linktitle": "Lees de aanmaaktijd van geneste opmerkingen met Aspose.Cells"
"second_title": "Aspose.Cells .NET Excel-verwerkings-API"
"title": "Lees de aanmaaktijd van geneste opmerkingen met Aspose.Cells"
"url": "/nl/cells/net/guide-worksheet-operations/read-created-time-of-threaded-comment/"
"weight": 21
---

## Invoering

Bij het werken met Excel-bestanden kan het beheren van opmerkingen essentieel zijn voor samenwerking en het bijhouden van feedback. In deze handleiding leiden we u door het proces van het aflezen van de aanmaaktijd van opmerkingen in een Excel-werkblad met behulp van Aspose.Cells voor .NET. Deze krachtige tool biedt een efficiënte manier om met Excel-bestanden te werken, waardoor ontwikkelaars gedetailleerde informatie uit opmerkingen kunnen halen, wat met name handig is voor het bijhouden van de timing van feedback in samenwerkingsscenario's.

## Vereisten

Voordat we beginnen, is het belangrijk om ervoor te zorgen dat je ontwikkelomgeving correct is ingesteld voor het gebruik van Aspose.Cells voor .NET. Dit heb je nodig:

1. Aspose.Cells voor .NET: Je hebt de Aspose.Cells-bibliotheek nodig. Je kunt de nieuwste versie downloaden via de [Aspose-website](https://releases.aspose.com/cells/net/).
2. IDE: Visual Studio (of een .NET IDE naar keuze) om uw code te schrijven en uit te voeren.
3. Basiskennis van C#: Kennis van C#-programmering maakt het gemakkelijker om de voorbeelden te volgen.
4. Excel-bestand: voor deze tutorial gebruiken we een Excel-bestand met de naam `ThreadedCommentsSample.xlsx`, die een aantal opmerkingen bevat. Zorg ervoor dat je bestand opmerkingen bevat om het te kunnen volgen.

## De vereiste pakketten importeren

Om te beginnen moet je de benodigde naamruimten importeren om met Aspose.Cells te kunnen werken. Open je C#-project en voeg de volgende instructies toe bovenaan je codebestand:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

De `Aspose.Cells` Met de naamruimte hebt u toegang tot alle klassen en methoden die nodig zijn voor het manipuleren van Excel-bestanden, terwijl `System` is nodig voor algemene functionaliteit, zoals uitvoer en uitzonderingsafhandeling.

## Stap 1: Geef de map van het Excel-bestand op

De eerste stap is het definiëren van het pad waar uw Excel-bestand is opgeslagen. Dit pad wordt gebruikt om het bestand programmatisch te lokaliseren.

```csharp
// Definieer de map van het Excel-bestand
string sourceDir = "Your Document Directory";
```

Vervangen `"C:\\YourDirectory\\"` met het daadwerkelijke pad naar uw bestand. Dit zorgt ervoor dat het programma weet waar het de `ThreadedCommentsSample.xlsx`.

## Stap 2: Laad de werkmap

Nu de map is ingesteld, kunnen we de Excel-werkmap laden. Dit doen we door een nieuwe map aan te maken. `Workbook` object en het bestandspad ernaartoe doorgeven.

```csharp
// De Excel-werkmap laden
Workbook workbook = new Workbook(sourceDir + "ThreadedCommentsSample.xlsx");
```

Als het bestand niet op het opgegeven pad wordt gevonden, wordt er een uitzondering gegenereerd. Controleer daarom of het bestandspad correct is voordat u verdergaat.

## Stap 3: Toegang tot het gewenste werkblad

Zodra de werkmap is geladen, moet u het werkblad met de gekoppelde opmerkingen openen. In dit voorbeeld halen we het eerste werkblad van de werkmap op.

```csharp
// Toegang tot het eerste werkblad in de werkmap
Worksheet worksheet = workbook.Worksheets[0];
```

Als uw opmerkingen zich in een ander werkblad bevinden, past u de index eenvoudig aan. Gebruik bijvoorbeeld `Worksheets[1]` voor het tweede werkblad, enzovoort.

## Stap 4: Geneste opmerkingen ophalen

Om de gegroepeerde opmerkingen op te halen, moet u de cel met de opmerkingen opgeven. In dit geval richten we ons op cel `A1`De methode `GetThreadedComments` wordt gebruikt om alle opmerkingen op te halen die aan een specifieke cel zijn gekoppeld.

```csharp
// Geneste opmerkingen ophalen uit cel A1
ThreadedCommentCollection threadedComments = worksheet.Comments.GetThreadedComments("A1");
```

Dit retourneert een verzameling van gekoppelde opmerkingen voor cel A1. Als er geen opmerkingen in de opgegeven cel staan, is de verzameling leeg.

## Stap 5: Loop door de opmerkingen en extraheer de gecreëerde tijd

Nadat de reacties met de thread zijn opgehaald, is de volgende stap het doorlopen van de verzameling en het extraheren van relevante details, inclusief de aanmaaktijd voor elke reactie. We kunnen dit eenvoudig bereiken door de `ThreadedCommentCollection`.

```csharp
// Doorloop elke commentaarreeks en geef de details weer
foreach (ThreadedComment comment in threadedComments)
{
    Console.WriteLine("Comment: " + comment.Notes);
    Console.WriteLine("Author: " + comment.Author.Name);
    Console.WriteLine("Created Time: " + comment.CreatedTime);
}
```

Deze code geeft de inhoud van de reactie, de naam van de auteur en het tijdstip waarop de reactie is gemaakt weer. `CreatedTime` eigenschap retourneert het tijdstempel van het moment waarop de opmerking oorspronkelijk is gemaakt.

## Stap 6: Een bevestigingsbericht weergeven

Nadat je de reacties succesvol hebt gelezen en de informatie hebt weergegeven, is het altijd verstandig om een bevestigingsbericht in je code op te nemen. Dit helpt te bevestigen dat het proces correct is uitgevoerd.

```csharp
// Bevestigingsbericht
Console.WriteLine("Successfully retrieved threaded comment created times.");
```

Zodra de uitvoering van de code is voltooid, wordt dit bericht op de console weergegeven. Hiermee wordt bevestigd dat het proces zonder fouten is uitgevoerd.

## Conclusie

U hebt nu geleerd hoe u eenvoudig de aanmaaktijd van opmerkingen in een Excel-werkblad kunt aflezen met Aspose.Cells voor .NET. Deze functionaliteit is van onschatbare waarde voor het bijhouden van opmerkingen en feedback in samenwerkingsomgevingen en biedt essentiële tijdstempels voor documentbeoordelingsprocessen. Door deze handleiding te volgen, kunt u efficiënt gegevens over opmerkingen extraheren en gebruiken in uw .NET-applicaties, waardoor uw workflow en de samenwerking met teamleden worden verbeterd.

## Veelgestelde vragen

### Wat is Aspose.Cells voor .NET?

Aspose.Cells voor .NET is een uitgebreide bibliotheek waarmee ontwikkelaars Excel-bestanden in .NET-applicaties kunnen maken, bewerken en beheren. Het biedt robuuste tools voor het programmatisch lezen, schrijven en wijzigen van Excel-bestanden.

### Hoe kan ik Aspose.Cells voor .NET downloaden?

U kunt de nieuwste versie van Aspose.Cells voor .NET downloaden van de [Aspose-website](https://releases.aspose.com/cells/net/).

### Is er een gratis proefperiode beschikbaar?

Ja, Aspose biedt een gratis proefversie aan voor Aspose.Cells voor .NET. U kunt de proefversie downloaden via de [gratis proefpagina](https://releases.aspose.com/).

### Kan ik opmerkingen uit andere cellen bekijken?

Ja, u kunt toegang krijgen tot geneste opmerkingen vanuit elke cel in het werkblad door de celverwijzing in de `GetThreadedComments` methode. Verander eenvoudig `"A1"` naar de gewenste celreferentie.

### Waar kan ik ondersteuning krijgen voor Aspose.Cells?

Als u ondersteuning nodig heeft of vragen heeft, bezoek dan de [Aspose-forum](https://forum.aspose.com/c/cells/9), waar u antwoorden kunt vinden of hulp kunt vragen aan de community.