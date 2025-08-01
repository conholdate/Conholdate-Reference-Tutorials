---
"description": "Apprenez à convertir efficacement des mises en page CAO en différents formats d'images raster avec Aspose.CAD pour .NET. Ce guide complet vous guide pas à pas avec un code clair."
"linktitle": "Conversion d'images CAO en images raster"
"second_title": "Aspose.CAD .NET - Format de fichier CAO et BIM"
"title": "Exporter des fichiers CAO vers des images raster avec Aspose.CAD pour .NET"
"url": "/fr/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## Introduction

Vous souhaitez convertir facilement des mises en page CAO en images raster avec Aspose.CAD pour .NET ? Ce guide étape par étape vous guidera dans cette démarche, avec des extraits de code concis pour une expérience fluide. Que vous soyez un développeur expérimenté ou débutant, ce tutoriel vous fournira des informations précieuses pour tous les niveaux de compétence.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- Bibliothèque Aspose.CAD pour .NET : téléchargez et installez la bibliothèque à partir du [Site Web Aspose.CAD](https://releases.aspose.com/cad/net/).
- Fichier de dessin CAO : Ayez votre fichier de dessin CAO (par exemple, `conic_pyramid.dxf`) prêt pour la conversion.

## Importer les espaces de noms requis

Dans votre projet .NET, vous devrez importer les espaces de noms nécessaires pour utiliser les fonctions Aspose.CAD. Ajoutez ce qui suit en haut de votre code :

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Étape 1 : Chargez votre dessin CAO

Tout d’abord, spécifiez le répertoire et chargez votre fichier CAO dans une instance d’image :

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// Charger le dessin CAO
using (var image = Image.Load(sourceFilePath))
{
    // Passez aux étapes suivantes
}
```

## Étape 2 : Créer des options de pixellisation

Ensuite, configurez les options de rastérisation, en définissant les dimensions souhaitées pour l’image de sortie :

```csharp
// Initialiser les options de rastérisation Cad
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## Étape 3 : Spécifier les calques à convertir

Si vous souhaitez convertir des calques spécifiques, ajoutez-les à vos options de rastérisation :

```csharp
// Spécifiez le calque à convertir
rasterizationOptions.Layers = new [] { "LayerA" };
```

## Étape 4 : Configurer les options d’exportation JPEG

Créez maintenant des options pour le format d'image vers lequel vous souhaitez exporter (JPEG dans ce cas) :

```csharp
// Créer des options Jpeg pour l'exportation
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Étape 5 : Exporter au format JPEG

Enfin, enregistrez l’image convertie :

```csharp
// Définir le chemin du fichier de sortie et enregistrer l'image
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## Fonctionnalité supplémentaire : convertir tous les calques

Pour convertir tous les calques de votre dessin CAO, vous pouvez implémenter une méthode comme celle-ci :

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // Parcourez les calques et enregistrez chacun d'eux dans un fichier JPEG distinct
    // Votre code d'implémentation ici
}
```

## Conclusion

Félicitations ! Vous avez appris à convertir efficacement des mises en page CAO en formats d'image raster avec Aspose.CAD pour .NET. Ce guide propose une approche simple, adaptée aux développeurs souhaitant des conversions CAO efficaces.

## FAQ

### Puis-je exporter vers différents formats d’image ?

Absolument ! Il suffit d'échanger `JpegOptions` avec d'autres options de format, telles que `PngOptions` ou `BmpOptions`, selon vos besoins.

### Une version d'essai est-elle disponible ?

Oui, vous pouvez télécharger une version d'essai pour explorer les fonctionnalités en suivant ceci [lien](https://releases.aspose.com/cad/net/).

### Où puis-je trouver de l'aide pour Aspose.CAD ?

Pour le soutien de la communauté, consultez Aspose.CAD [forum](https://forum.aspose.com/c/cad/19), ou envisagez d'acheter une licence pour une assistance plus dédiée.

### Les licences temporaires sont-elles possibles ?

Oui, des licences temporaires sont disponibles ; vous pouvez en demander une [ici](https://purchase.conholdate.com/temporary-license/).

### Où puis-je accéder à une documentation détaillée ?

Visitez la documentation complète [ici](https://reference.aspose.com/cad/net/) pour plus d'informations.