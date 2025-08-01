---
"description": "Leer hoe u Microsoft OneNote-documenten efficiënt kunt opslaan als PDF-bestanden met Aspose.Note voor .NET. Deze handleiding leidt u door de vereiste vereisten en biedt nuttige antwoorden op veelgestelde vragen."
"linktitle": "OneNote-documenten opslaan in PDF"
"second_title": "Aspose.Note .NET API"
"title": "OneNote-documenten opslaan in PDF met Aspose.Note voor .NET"
"url": "/nl/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Invoering

In deze tutorial laten we zien hoe je documenten kunt opslaan in PDF-formaat met Aspose.Note voor .NET. Aspose.Note is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met Microsoft OneNote-bestanden kunnen werken. We bespreken de vereisten, importeren naamruimten en bieden stapsgewijze instructies voor het opslaan van documenten in PDF-formaat in verschillende pagina-indelingen.

## Vereisten
1. Visual Studio: Zorg ervoor dat dit is geïnstalleerd.
2. Aspose.Note voor .NET: Download en installeer de bibliotheek.
3. Kennis van C#: basiskennis van de taal is vereist.

## Noodzakelijke naamruimten importeren
Importeer de volgende naamruimten in uw code voordat u verdergaat:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Stap 1: Opslaan als PDF met Letterpagina-instellingen
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Dit pad bijwerken
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Laadt het OneNote-document en slaat het op als PDF met pagina-instellingen voor A4-formaat.

## Stap 2: Opslaan als PDF met A4-pagina-instellingen (geen hoogtelimiet)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Dit pad bijwerken
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Vergelijkbaar met stap 1, maar gebruikt A4-pagina-instellingen zonder hoogtebeperkingen.

## Conclusie
De tutorial laat zien hoe je OneNote-bestanden met Aspose.Note naar PDF-formaat kunt converteren. Door verschillende pagina-instellingen te gebruiken, krijgen ontwikkelaars meer flexibiliteit in documentbeheer.

## Veelgestelde vragen
### Kan Aspose.Note complexe OneNote-bestanden verwerken?
Ja, het kan verschillende functies van complexe OneNote-bestanden effectief verwerken.

### Is Aspose.Note geschikt voor commerciële projecten?
Ja, u kunt het voor commerciële toepassingen gebruiken nadat u een licentie hebt aangeschaft.

### Biedt Aspose.Note een gratis proefperiode aan?
Ja, u kunt het programma gratis uitproberen.

### Waar kan ik documentatie voor Aspose.Note vinden?
Gedetailleerde documentatie is beschikbaar op de Aspose-referentiesite.

### Heeft u nog meer hulp nodig?
Voor vragen en ondersteuning kunt u terecht op het Aspose.Note forum.