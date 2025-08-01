---
"description": "Exploitez le potentiel de vos présentations PowerPoint en apprenant à récupérer les données d'un classeur à partir de graphiques avec Aspose.Slides pour .NET. Ce tutoriel vous guide pas à pas tout au long du processus, facilitant ainsi l'extraction et l'exploitation efficace des données des graphiques."
"linktitle": "Extraire les données du classeur à partir de graphiques avec Aspose.Slides pour .NET"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Extraire les données du classeur à partir de graphiques avec Aspose.Slides pour .NET"
"url": "/fr/slides/net/master-additional-chart-features/extract-workbook-data-from-charts/"
"weight": 12
---

## Introduction

Travailler avec des présentations PowerPoint peut s'avérer complexe, notamment pour extraire des données précieuses de graphiques intégrés. Heureusement, Aspose.Slides pour .NET offre une solution robuste qui simplifie ce processus. Dans ce tutoriel, nous vous guiderons étape par étape pour récupérer un classeur à partir d'un graphique dans une présentation PowerPoint.

## Prérequis

Avant de passer au code, assurez-vous d’avoir les éléments suivants prêts :

### Aspose.Slides pour .NET

Aspose.Slides pour .NET doit être installé dans votre environnement de développement. Si ce n'est pas encore fait, vous pouvez le télécharger depuis le site web :

[Télécharger Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/)

### Présentation PowerPoint

Ayez à portée de main votre fichier de présentation PowerPoint, en particulier celui qui contient un graphique avec les données associées que vous souhaitez récupérer.

## Étape 1 : Importer les espaces de noms nécessaires

Pour travailler efficacement avec Aspose.Slides, vous devez d'abord importer les espaces de noms requis :

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Étape 2 : Définir le répertoire des documents

Spécifiez le répertoire où se trouve votre fichier de présentation :

```csharp
string dataDir = "Your Document Directory"; // Ajustez ce chemin selon vos besoins
```

## Étape 3 : Charger la présentation

Vous pouvez charger la présentation PowerPoint tout en activant la récupération du classeur depuis le cache du graphique. Voici comment procéder :

```csharp
string pptxFile = Path.Combine(dataDir, "YourPresentation.pptx");
string outPptxFile = Path.Combine(RunExamples.OutPath, "RecoveredWorkbook.pptx");

LoadOptions lo = new LoadOptions();
lo.SpreadsheetOptions.RecoverWorkbookFromChartCache = true;

using (Presentation pres = new Presentation(pptxFile, lo))
{
    // Accéder et travailler avec les données du graphique
    // Votre code ira ici
    pres.Save(outPptxFile, SaveFormat.Pptx);
}
```

Dans cette étape, le `LoadOptions` L'objet vous permet d'activer la récupération du classeur à l'aide de l' `RecoverWorkbookFromChartCache` propriété.

## Étape 4 : Récupérer le graphique et accéder à son classeur

Il est maintenant temps de fouiller dans le graphique et de récupérer ses données associées :

```csharp
IChart chart = pres.Slides[0].Shapes[0] as IChart; // Ajustez l'index selon vos besoins
IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;

// Vous pouvez désormais travailler avec les données du classeur selon vos besoins
```

En accédant à la première forme de la première diapositive (qui devrait être un graphique), vous obtenez le classeur de données du graphique et pouvez manipuler ou extraire les données selon vos besoins.

## Conclusion

Dans ce tutoriel, nous avons montré comment récupérer efficacement un classeur à partir d'un graphique dans une présentation PowerPoint avec Aspose.Slides pour .NET. En suivant ces étapes, vous pourrez facilement extraire et exploiter les données d'un graphique pour vos besoins analytiques.

## FAQ

### Qu'est-ce qu'Aspose.Slides pour .NET ?

Aspose.Slides pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des présentations Microsoft PowerPoint par programmation.

### Puis-je essayer Aspose.Slides pour .NET avant d'acheter ?

Oui ! Aspose propose une version d'essai gratuite d'Aspose.Slides pour .NET. Vous pouvez évaluer ses fonctionnalités avant de l'acheter. [Obtenez l'essai gratuit ici](https://releases.aspose.com/).

### Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?

Vous pouvez accéder à la documentation complète d'Aspose.Slides pour .NET [ici](https://reference.aspose.com/slides/net/), qui comprend des exemples et des références API.

### Comment acheter une licence pour Aspose.Slides pour .NET ?

Pour acheter une licence, visitez le site Web d'Aspose et utilisez le lien suivant : [Acheter Aspose.Slides pour .NET](https://purchase.aspose.com/buy).