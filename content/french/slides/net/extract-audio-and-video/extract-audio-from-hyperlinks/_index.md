---
"description": "Apprenez à extraire l'audio des hyperliens de vos présentations PowerPoint avec Aspose.Slides pour .NET. Ce guide étape par étape fournit des instructions claires."
"linktitle": "Extraire l'audio des hyperliens"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Extraire l'audio des hyperliens dans PowerPoint avec Aspose.Slides"
"url": "/fr/slides/net/extract-audio-and-video/extract-audio-from-hyperlinks/"
"weight": 12
---

## Introduction

Dans les présentations multimédias, l'audio renforce considérablement l'impact de vos diapositives. Si vous avez déjà vu une présentation PowerPoint contenant des liens audio et que vous vous demandez comment extraire ces données audio pour d'autres utilisations, vous êtes au bon endroit. Ce guide vous guidera pas à pas dans l'extraction de données audio à partir de liens hypertexte dans une présentation PowerPoint à l'aide de la bibliothèque Aspose.Slides pour .NET.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

### Bibliothèque Aspose.Slides pour .NET

Assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour .NET. Si ce n'est pas déjà fait, vous pouvez la télécharger depuis le [Documentation Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/).

### Présentation PowerPoint avec hyperliens audio

Vous aurez besoin d'une présentation PowerPoint (PPTX) contenant des hyperliens et des pistes audio associées. Cette présentation servira de source pour l'extraction audio.

## Importation des espaces de noms requis

Pour utiliser efficacement Aspose.Slides pour .NET, vous devrez importer les espaces de noms suivants dans votre projet C# :

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

Maintenant que tout est en place, décomposons le processus d’extraction en étapes simples.

## Étape 1 : Définir le répertoire des documents

Commencez par spécifier le répertoire où se trouve votre présentation PowerPoint. Remplacez `"Your Document Directory"` avec le chemin réel.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Charger la présentation PowerPoint

Ensuite, chargez la présentation PowerPoint (PPTX) contenant le lien audio. Remplacez `"HyperlinkSound.pptx"` avec le nom réel de votre fichier de présentation.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // Passez à l’étape suivante.
}
```

## Étape 3 : Accéder au son du lien hypertexte

Récupérez l'hyperlien de la première forme de la première diapositive. Si ce lien est associé à un son, nous pouvons procéder à son extraction.

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // Passez à l’étape suivante.
}
```

## Étape 4 : Extraire l'audio du lien hypertexte

Si l'hyperlien contient du son, nous pouvons l'extraire sous forme de tableau d'octets et l'enregistrer sous forme de fichier multimédia.

```csharp
// Extraire le son du lien hypertexte sous forme de tableau d'octets
byte[] audioData = link.Sound.BinaryData;

// Spécifiez le chemin où vous souhaitez enregistrer l'audio extrait
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// Enregistrez l'audio extrait dans un fichier multimédia
File.WriteAllBytes(outMediaPath, audioData);
```

Félicitations ! Vous avez réussi à extraire l'audio d'un lien hypertexte dans une présentation PowerPoint avec Aspose.Slides pour .NET. Vous pouvez désormais utiliser cet audio dans vos projets multimédias.

## Conclusion

Aspose.Slides pour .NET offre une solution puissante et conviviale pour extraire l'audio des hyperliens de vos présentations PowerPoint. Grâce aux étapes décrites dans ce guide, vous pourrez facilement réutiliser le contenu audio de vos présentations pour enrichir vos projets.

## FAQ

### Aspose.Slides pour .NET est-elle une bibliothèque gratuite ?
Non, Aspose.Slides pour .NET est une bibliothèque commerciale, mais vous pouvez télécharger une version d'essai gratuite pour explorer ses fonctionnalités à partir de [ici](https://releases.aspose.com/).

### Puis-je extraire l'audio d'anciens formats PowerPoint comme PPT ?
Oui, Aspose.Slides pour .NET prend en charge les formats PPTX et PPT pour l'extraction audio.

### Existe-t-il un forum communautaire pour le support d'Aspose.Slides ?
Absolument ! Vous pouvez obtenir de l'aide et partager vos expériences dans le [Forum communautaire Aspose.Slides](https://forum.aspose.com/).

### Puis-je acheter une licence temporaire pour Aspose.Slides pour un projet à court terme ?
Oui, vous pouvez obtenir une licence temporaire pour vos besoins de projet à court terme en visitant [ce lien](https://purchase.aspose.com/temporary-license/).

### Existe-t-il d’autres formats audio pris en charge pour l’extraction en dehors de MPG ?
Oui, Aspose.Slides pour .NET permet l'extraction de fichiers audio dans différents formats. Vous pouvez convertir l'audio au format de votre choix après l'extraction.