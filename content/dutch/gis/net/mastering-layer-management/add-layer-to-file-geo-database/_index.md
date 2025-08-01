---
"description": "Leer hoe u een nieuwe laag toevoegt aan een File Geodatabase (GDB) met Aspose.GIS voor .NET. Deze uitgebreide handleiding behandelt de vereisten, naamruimte-import en gedetailleerde stappen voor het maken en valideren van lagen in uw GIS-datasets."
"linktitle": "Een laag toevoegen aan een bestandsgeodatabase"
"second_title": "Aspose.GIS .NET API"
"title": "Een laag toevoegen aan een bestandsgeodatabase met Aspose.GIS voor .NET"
"url": "/nl/gis/net/mastering-layer-management/add-layer-to-file-geo-database/"
"weight": 16
---

## Invoering

Geografische Informatie Systemen (GIS)-technologie speelt een cruciale rol in moderne data-analyse en -visualisatie. Aspose.GIS voor .NET is een uitzonderlijke bibliotheek waarmee ontwikkelaars geografische data efficiënt kunnen bewerken. Deze gedetailleerde handleiding legt uit hoe u een nieuwe laag toevoegt aan een File Geodatabase (GDB)-dataset met Aspose.GIS voor .NET. Volg deze uitgebreide stappen om lagen naadloos te integreren en uw GIS-mogelijkheden te verbeteren.

## Vereisten voor het toevoegen van lagen aan bestand-GDB

Voordat we verdergaan, zorg ervoor dat u het volgende heeft:

1. Aspose.GIS voor .NET-bibliotheek  
   Download en installeer de bibliotheek van de [Aspose.GIS voor .NET-pagina](https://reference.aspose.com/gis/net/).

2. Een File Geodatabase (GDB)-dataset  
   Zorg ervoor dat u over een bestaande GDB-dataset voor de bewerking beschikt.

3. Ontwikkelomgeving  
   Installeer en configureer uw favoriete IDE met .NET-ondersteuning (bijv. Visual Studio).

4. Tijdelijke licentie (optioneel)  
   Voor een volledige evaluatie van de functies kunt u een aanvraag indienen [tijdelijke licentie](https://purchase.conholdate.com/temporary-license/).

5. Gegevensdirectory  
   Maak een directory aan om uw invoer- en uitvoerdatasets te beheren.

## Vereiste naamruimten importeren

Voeg vóór het coderen de essentiële naamruimten toe voor toegang tot Aspose.GIS-functionaliteiten. Voeg het volgende codefragment toe aan het begin van uw project:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Stap 1: Dupliceer de GDB-dataset

Om de integriteit van uw originele dataset te behouden, maakt u een duplicaat. Gebruik de volgende code om de dataset naar een nieuwe locatie te kopiëren:

```csharp
string dataDir = "C:\\GISData\\"; // Map met uw datasets
string originalPath = dataDir + "ExistingDataset.gdb";
string newDatasetPath = dataDir + "ModifiedDataset.gdb";

// Functie om de directory te dupliceren
RunExamples.CopyDirectory(originalPath, newDatasetPath);
```

## Stap 2: Open de dataset en controleer de creatiemogelijkheden

Met Aspose.GIS kunnen ontwikkelaars datasets openen en controleren of er nieuwe lagen kunnen worden toegevoegd. Gebruik het volgende fragment om de aanmaakmogelijkheden van de dataset te bevestigen:

```csharp
using (var dataset = Dataset.Open(newDatasetPath, Drivers.FileGdb))
{
    Console.WriteLine($"Can Create Layers: {dataset.CanCreateLayers}"); // Moet True retourneren
}
```

## Stap 3: Een nieuwe laag in de dataset maken

Om een laag toe te voegen, moeten het ruimtelijke referentiesysteem en de attributen ervan worden gedefinieerd. Zo maakt en vult u een laag met voorbeeldgegevens:

```csharp
using (var dataset = Dataset.Open(newDatasetPath, Drivers.FileGdb))
{
    // Maak een nieuwe laag met het ruimtelijk referentiesysteem WGS 84
    using (var layer = dataset.CreateLayer("NewLayer", SpatialReferenceSystem.Wgs84))
    {
        // Voeg een kenmerkschema toe
        layer.Attributes.Add(new FeatureAttribute("LocationName", AttributeDataType.String));

        // Een functie maken en toevoegen
        var feature = layer.ConstructFeature();
        feature.SetValue("LocationName", "Sample Point");
        feature.Geometry = new Point(34.0522, -118.2437); // Lengtegraad en breedtegraad
        layer.Add(feature);
    }
}
```

## Stap 4: Open en valideer de nieuwe laag

Valideer na het aanmaken van een laag de inhoud om de nauwkeurigheid te garanderen. Gebruik het volgende codefragment:

```csharp
using (var dataset = Dataset.Open(newDatasetPath, Drivers.FileGdb))
{
    using (var layer = dataset.OpenLayer("NewLayer"))
    {
        Console.WriteLine($"Feature Count: {layer.Count}");
        Console.WriteLine($"Attribute Value: {layer[0].GetValue<string>("LocationName")}");
    }
}
```

## Conclusie

Het toevoegen van een laag aan een File Geodatabase-dataset met Aspose.GIS voor .NET is een eenvoudig proces wanneer u deze stappen volgt. Van het dupliceren van datasets tot het aanmaken en valideren van lagen, de bibliotheek biedt robuuste tools voor het beheren van GIS-data. Door deze technieken onder de knie te krijgen, kunt u uw GIS-workflows verbeteren en efficiënte geografische datamanipulatie bereiken.

## Veelgestelde vragen

### Waarvoor wordt Aspose.GIS voor .NET gebruikt?
Aspose.GIS voor .NET is een bibliotheek die is ontworpen om geografische gegevens te verwerken en te manipuleren. De bibliotheek ondersteunt verschillende bestandsindelingen, waaronder Shapefiles, GDB en meer.

### Kan ik meerdere lagen in één bewerking toevoegen?
Ja, met Aspose.GIS kunt u meerdere lagen binnen een dataset maken en beheren.

### Welke ruimtelijke referentiesystemen worden ondersteund?
De bibliotheek ondersteunt talrijke ruimtelijke referentiesystemen, waaronder WGS 84, NAD 83 en aangepaste CRS.

### Waar kan ik ondersteuning vinden?
Bezoek de [Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor discussies en ondersteuning in de gemeenschap.

### Is er een gratis proefperiode beschikbaar?
Ja, een [gratis proefperiode](https://releases.aspose.com/) is beschikbaar om de functies van de bibliotheek te testen.