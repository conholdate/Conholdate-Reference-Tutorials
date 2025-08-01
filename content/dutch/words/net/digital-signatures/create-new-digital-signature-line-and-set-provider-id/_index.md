---
"description": "Ontdek hoe u programmatisch handtekeningregels aan uw Word-documenten kunt toevoegen met Aspose.Words voor .NET. Deze uitgebreide handleiding behandelt alles van het instellen van uw ontwikkelomgeving tot het invoegen van handtekeningregels en het veilig ondertekenen van documenten."
"linktitle": "Nieuwe digitale handtekeningregel maken en provider-ID instellen"
"second_title": "Aspose.Words API voor documentverwerking"
"title": "Nieuwe digitale handtekeningregel maken en provider-ID instellen"
"url": "/nl/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Invoering

Hallo technologiefanaten! Heb je er ooit over nagedacht om de toevoeging van handtekeningregels aan je Word-documenten te automatiseren? Vandaag duiken we in hoe je dit kunt bereiken met Aspose.Words voor .NET. Deze stapsgewijze handleiding begeleidt je bij het maken van een handtekeningregel en het instellen van de provider-ID, waardoor je documentverwerking efficiënter en gestroomlijnder wordt.

## Vereisten

Voordat we beginnen, controleren we of alles klaar staat:

1. Aspose.Words voor .NET: Als u het nog niet hebt geïnstalleerd, download het dan [hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Gebruik Visual Studio of een andere C#-ontwikkelingsomgeving.
3. .NET Framework: Zorg ervoor dat .NET Framework op uw computer is geïnstalleerd.
4. PFX-certificaat: Voor het ondertekenen van documenten hebt u een PFX-certificaat nodig. U kunt dit certificaat verkrijgen bij een vertrouwde certificeringsinstantie.

## Noodzakelijke naamruimten importeren

Om te beginnen importeert u de vereiste naamruimten in uw C#-project:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Laten we nu dieper ingaan op de details van het maken van een nieuwe handtekeningregel en het instellen van de provider-ID.

## Stap 1: Een nieuw document maken

Eerst moeten we een nieuw Word-document maken, dat zal dienen als canvas voor onze handtekeningregel:

```csharp
// Geef het pad naar uw documentenmap op.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Hier initialiseren we een nieuwe `Document` en een `DocumentBuilder`, waardoor we eenvoudig elementen kunnen toevoegen.

## Stap 2: Definieer de opties voor de handtekeningregel

Vervolgens definiëren we de opties voor onze handtekeningregel, waaronder de naam, functie, e-mailadres en andere relevante gegevens van de ondertekenaar:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Met deze opties kunt u de handtekeningregel personaliseren, waardoor deze duidelijk en professioneel overkomt.

## Stap 3: De handtekeningregel invoegen

Nu we alle opties gereed hebben, kunnen we de handtekeningregel in het document invoegen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

De `InsertSignatureLine` methode voegt de handtekeningregel toe en wij wijzen er een unieke provider-ID aan toe.

## Stap 4: Sla het document op

Nadat u de handtekeningregel hebt ingevoegd, slaat u het document op:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Hiermee wordt uw document opgeslagen met de nieuw toegevoegde handtekeningregel.

## Stap 5: Ondertekeningsopties instellen

Nu configureren we de ondertekeningsopties, waaronder de handtekeningregel-ID, provider-ID, opmerkingen en de ondertekeningstijd:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Deze instellingen zorgen ervoor dat het document met de juiste gegevens wordt ondertekend.

## Stap 6: Certificaathouder aanmaken

Om het document te ondertekenen, moeten we een certificaathouder aanmaken met behulp van het PFX-certificaat:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Vervangen `"morzal.pfx"` met uw werkelijke certificaatbestandsnaam en `"aw"` met uw certificaatwachtwoord.

## Stap 7: Onderteken het document

Ten slotte ondertekenen we het document met behulp van het hulpprogramma voor digitale handtekeningen:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Dit proces ondertekent het document en slaat het op als een nieuw bestand.

## Conclusie

Gefeliciteerd! U hebt met succes een handtekeningregel gemaakt en de provider-ID ingesteld in een Word-document met Aspose.Words voor .NET. Deze krachtige bibliotheek vereenvoudigt documentverwerkingstaken en maakt uw workflow efficiënter. Probeer het eens uit en ontdek hoe het uw projecten kan verbeteren!

## Veelgestelde vragen

### Kan ik het uiterlijk van de handtekeningregel aanpassen?
Absoluut! Je kunt verschillende opties aanpassen in de `SignatureLineOptions` die bij uw stijl en wensen passen.

### Wat als ik geen PFX-certificaat heb?
U dient er een aan te vragen bij een vertrouwde certificeringsinstantie, omdat deze essentieel is voor het digitaal ondertekenen van documenten.

### Kan ik meerdere handtekeningregels aan een document toevoegen?
Ja, u kunt meerdere handtekeningregels toevoegen door het invoegproces te herhalen met verschillende opties.

### Is Aspose.Words voor .NET compatibel met .NET Core?
Ja, Aspose.Words voor .NET ondersteunt .NET Core, waardoor het veelzijdig is voor verschillende ontwikkelomgevingen.

### Hoe veilig zijn digitale handtekeningen?
Digitale handtekeningen die met Aspose.Words zijn gemaakt, zijn zeer veilig, mits u een geldig en vertrouwd certificaat gebruikt.