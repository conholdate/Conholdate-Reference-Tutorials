---
"description": "Apprenez à convertir facilement des fichiers DGN en PDF grâce à la puissante bibliothèque Aspose.CAD pour .NET. Ce guide étape par étape est conçu pour les développeurs de tous niveaux."
"linktitle": "Convertir DGN en PDF dans Aspose.CAD pour .NET"
"second_title": "Aspose.CAD .NET - Format de fichier CAO et BIM"
"title": "Convertir DGN en PDF dans Aspose.CAD pour .NET"
"url": "/fr/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## Introduction

Naviguer dans l'univers des fichiers CAO peut s'avérer complexe, mais avec Aspose.CAD pour .NET, les développeurs peuvent facilement manipuler et convertir différents formats CAO. La conversion de fichiers DGN en PDF est un besoin courant, que nous aborderons étape par étape dans ce tutoriel.

## Prérequis

Pour suivre, assurez-vous d'avoir les éléments suivants :

- Maîtrise de base de C# et du framework .NET.
- Bibliothèque Aspose.CAD pour .NET installée. Vous pouvez la télécharger. [ici](https://releases.aspose.com/cad/net/).
- Un exemple de fichier DGN (par exemple, Nikon_D90_Camera.dgn). 

## Étape 1 : Importer les espaces de noms requis

Commencez par importer les espaces de noms pertinents dans votre projet C# :

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Étape 2 : charger le fichier DGN

Spécifiez le répertoire de votre fichier DGN et chargez-le à l'aide du code suivant :

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // Un traitement supplémentaire aura lieu ici...
}
```

## Étape 3 : Configurer les options de rastérisation

Ensuite, configurez les options de rastérisation pour définir comment votre DGN sera rendu dans le PDF :

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // Ajustez la largeur selon vos besoins
    PageHeight = 300, // Ajustez la hauteur selon vos besoins
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## Étape 4 : Créer des options PDF

Définissez les options PDF en intégrant les paramètres de rastérisation configurés précédemment :

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Étape 5 : Enregistrer le fichier DGN au format PDF

Enfin, enregistrez le fichier DGN au format PDF en utilisant les options que vous avez configurées :

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## Conclusion

Félicitations ! Vous avez réussi à convertir un fichier DGN en PDF avec Aspose.CAD pour .NET. Ce tutoriel simple vous guide pas à pas dans le chargement du fichier DGN, la définition des options de pixellisation et l'enregistrement du résultat au format PDF.

## FAQ

### Ai-je besoin de connaissances préalables en CAO pour utiliser Aspose.CAD ?  
Absolument ! Aspose.CAD est conçu pour simplifier les tâches de CAO complexes et le rendre accessible à tous les développeurs, quelles que soient leurs connaissances en CAO.

### Où puis-je trouver plus de ressources et de documentation pour Aspose.CAD ?  
Vous pouvez explorer des guides complets et des exemples dans le [Documentation d'Aspose.CAD](https://reference.aspose.com/cad/net/).

### Existe-t-il un essai gratuit disponible pour Aspose.CAD ?  
Oui, un essai gratuit peut être obtenu [ici](https://releases.aspose.com/).

### Comment puis-je obtenir une licence temporaire pour Aspose.CAD ?  
Vous pouvez demander des licences temporaires [ici](https://purchase.conholdate.com/temporary-license/).

### Besoin d'aide ou avez-vous des questions ?  
Rejoignez la conversation dans le [Forum Aspose.CAD](https://forum.aspose.com/c/cad/19) pour le soutien et les demandes de renseignements de la communauté.