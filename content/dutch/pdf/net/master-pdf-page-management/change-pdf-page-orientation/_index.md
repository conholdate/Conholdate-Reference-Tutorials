---
"description": "Ontdek hoe u eenvoudig de pagina-oriëntatie van PDF-bestanden kunt aanpassen met Aspose.PDF voor .NET. Deze stapsgewijze handleiding biedt duidelijke instructies voor het laden, roteren en opslaan van uw documenten."
"linktitle": "Wijzig de PDF-pagina-oriëntatie"
"second_title": "Aspose.PDF voor .NET API-referentie"
"title": "Wijzig de PDF-pagina-oriëntatie"
"url": "/nl/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Invoering

Bent u ooit een PDF-bestand tegengekomen waarvan de pagina-oriëntatie helemaal verkeerd was? Of het nu gaat om een document dat verkeerd is gescand of een document dat gewoon een andere lay-out nodig heeft, het aanpassen van de oriëntatie kan een wereld van verschil maken. Gelukkig biedt Aspose.PDF voor .NET een krachtige en gebruiksvriendelijke manier om PDF-bestanden te bewerken, inclusief het wijzigen van de pagina-oriëntatie. In deze handleiding leiden we u stap voor stap door het proces, of u nu wilt overschakelen van staand naar liggend of andersom.

## Vereisten

Voordat we in de details duiken, zorg ervoor dat u het volgende geregeld heeft:

- Aspose.PDF voor .NET: Zorg ervoor dat de Aspose.PDF-bibliotheek is geïnstalleerd. Als u dit nog niet hebt gedaan, kunt u dit doen. [download het hier](https://releases.aspose.com/pdf/net/).
- Een .NET-ontwikkelomgeving: u kunt Visual Studio, JetBrains Rider of een andere IDE naar keuze gebruiken voor .NET-ontwikkeling.
- Basiskennis van C#: Als u bekend bent met C#, kunt u de cursus gemakkelijker volgen.
- Een PDF-bestand: Zorg dat je een PDF-voorbeeldbestand bij de hand hebt om te testen. Je kunt er zelf een maken of online een voorbeeld downloaden.

Als u net begint, overweeg dan om Aspose.PDF te proberen met een [gratis tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voordat u besluit om [koop de volledige versie](https://purchase.aspose.com/buy).

## Naamruimten importeren

Om PDF-pagina's te bewerken, moet u eerst de benodigde naamruimten in uw C#-project importeren. Voeg de volgende regels bovenaan uw codebestand toe:

```csharp
using System.IO;
using Aspose.Pdf;
```

Nu alles is ingesteld, kunnen we beginnen!

## Stap 1: laad het PDF-document

De eerste stap is het laden van het PDF-bestand dat u wilt wijzigen. Gebruik de `Document` klasse uit de Aspose.PDF-naamruimte:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Zorg ervoor dat u deze vervangt `"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw PDF-bestand.

## Stap 2: Door elke pagina bladeren

Vervolgens doorlopen we elke pagina in het PDF-document. Zo kunnen we de oriëntatiewijziging op alle pagina's toepassen:

```csharp
foreach (Page page in doc.Pages)
{
    // Manipuleer elke pagina
}
```

## Stap 3: Toegang tot de MediaBox van de pagina

Elke PDF-pagina heeft een `MediaBox` die de grenzen ervan definieert. We moeten hier toegang toe hebben om de huidige oriëntatie te controleren en aanpassingen te maken:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

De `MediaBox` geeft de afmetingen van de pagina aan, inclusief breedte en hoogte.

## Stap 4: Breedte en hoogte omwisselen

Om de pagina-oriëntatie te wijzigen, wisselen we de breedte- en hoogtewaarden om. Deze aanpassing verandert de afmetingen van de pagina:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Hier berekenen we de nieuwe afmetingen en verplaatsen we de linkerbenedenhoek (`LLY`) overeenkomstig.

## Stap 5: MediaBox en CropBox bijwerken

Nu we de nieuwe dimensies hebben, zullen we deze wijzigingen toepassen op de `MediaBox` En `CropBox` om ervoor te zorgen dat de pagina correct wordt weergegeven:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Stap 6: Draai de pagina

Om de oriëntatiewijziging te voltooien, draaien we de pagina. Dit is eenvoudig met Aspose.PDF:

```csharp
page.Rotate = Rotation.on90; // 90 graden draaien
```

Met deze lijn wordt de pagina effectief in de gewenste stand gedraaid.

## Stap 7: Sla de uitvoer-PDF op

Nadat u de oriëntatie van alle pagina's heeft gewijzigd, slaat u het bijgewerkte document op in een nieuw bestand:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Zorg ervoor dat u een nieuwe bestandsnaam opgeeft om te voorkomen dat het originele document wordt overschreven.

## Conclusie

En voilà! Het wijzigen van de pagina-oriëntatie van een PDF-bestand met Aspose.PDF voor .NET is een eenvoudig proces. Door het document te laden, de pagina's te doorlopen, de MediaBox bij te werken en het bestand op te slaan, kunt u de lay-out eenvoudig aanpassen aan uw behoeften. Of u nu een slecht gescand document corrigeert of pagina's opmaakt voor een presentatie, deze handleiding helpt u de klus efficiënt te klaren.

## Veelgestelde vragen

### Kan ik specifieke pagina's roteren in plaats van alle pagina's in het PDF-bestand?  
Ja, u kunt de lus aanpassen zodat deze op specifieke pagina's wordt gericht op basis van hun index, in plaats van door alle pagina's te itereren.

### Wat is de `MediaBox`?  
De `MediaBox` Definieert de grootte en vorm van de pagina in een PDF-bestand en bepaalt waar de inhoud wordt geplaatst.

### Werkt Aspose.PDF voor .NET met andere bestandsformaten?  
Ja, Aspose.PDF kan verschillende bestandsformaten verwerken, waaronder HTML, XML, XPS en meer.

### Bestaat er een gratis versie van Aspose.PDF voor .NET?  
Ja, je kunt beginnen met een [gratis proefperiode](https://releases.aspose.com/) of vraag een [tijdelijke licentie](https://purchase.aspose.com/temporary-license/).

### Kan ik de wijzigingen ongedaan maken nadat ik ze heb opgeslagen?  
Zodra u het document opslaat, zijn de wijzigingen permanent. Het is raadzaam om met een kopie te werken of een back-up van het originele bestand te bewaren.