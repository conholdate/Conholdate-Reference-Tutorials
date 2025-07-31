---
"description": "Apprenez à créer et personnaliser des modèles 3D primitifs, y compris des boîtes et des cylindres, et à les enregistrer au format FBX sans effort."
"linktitle": "Créer une modélisation 3D primitive"
"second_title": "API .NET Aspose.3D"
"title": "Créer une modélisation 3D primitive"
"url": "/fr/3d/net/guide-to-3d-modeling/create-primitive-3d-modeling/"
"weight": 10
---

## Introduction

Bienvenue dans le monde immersif de la modélisation 3D avec Aspose.3D pour .NET ! Dans ce tutoriel complet, nous vous guiderons pas à pas dans la création de modèles 3D primitifs. Que vous soyez un développeur expérimenté ou un débutant avide d'apprendre, ce guide vous permettra de créer des éléments 3D visuellement époustouflants pour vos projets.

## Prérequis

Avant de vous lancer dans la modélisation 3D, assurez-vous de disposer des prérequis suivants :

- Aspose.3D pour .NET : Téléchargez et installez la bibliothèque Aspose.3D pour .NET à partir du [page de téléchargement](https://releases.aspose.com/3d/net/).
  
- Environnement de développement .NET : configurez un environnement compatible avec Aspose.3D, tel que Visual Studio.

Avec tout préparé, embarquons-nous dans notre aventure de modélisation 3D !

## Importation des espaces de noms requis

Commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.3D :

```csharp
using System;
using System.IO;
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
```

Ces espaces de noms vous fourniront les outils nécessaires pour manipuler des modèles 3D et sauvegarder vos créations.

## Étape 1 : Initialiser un objet de scène

Créez un nouvel objet de scène qui agit comme toile pour vos modèles 3D :

```csharp
// Initialiser un objet Scene
Scene scene = new Scene();
```

Cette scène contiendra les formes primitives que vous êtes sur le point de créer.

## Étape 2 : Créer un modèle de boîte

Ensuite, ajoutons un modèle de boîte à votre scène :

```csharp
// Créer un modèle de boîte
scene.RootNode.CreateChildNode("box", new Box());
```

Vous pouvez personnaliser les dimensions et les propriétés de la boîte en fonction de votre vision créative.

## Étape 3 : Créer un modèle de cylindre

Maintenant, améliorez votre scène en ajoutant un cylindre :

```csharp
// Créer un modèle de cylindre
scene.RootNode.CreateChildNode("cylinder", new Cylinder());
```

Tout comme pour la boîte, n'hésitez pas à ajuster les paramètres du cylindre pour obtenir le look souhaité.

## Étape 4 : Enregistrer la scène au format FBX

Pour conserver votre modèle 3D, enregistrez-le au format FBX :

```csharp
// Enregistrer le dessin au format FBX
var output = Path.Combine("Your Output Directory", "test.fbx");
scene.Save(output, FileFormat.FBX7500ASCII);
```

Assurez-vous de choisir un répertoire de sortie et un nom de fichier appropriés pour votre modèle.

## Étape 5 : afficher un message de réussite

Enfin, célébrez votre succès en affichant un message :

```csharp
// Afficher un message de réussite
Console.WriteLine($"\nBuilding a scene from primitive 3D models was successful.\nFile saved at {output}");
```

Votre scène 3D composée de modèles primitifs est maintenant terminée et sauvegardée !

## Conclusion

Félicitations pour la création de superbes modèles 3D avec Aspose.3D pour .NET ! Ce tutoriel a abordé les bases de la modélisation primitive, mais les possibilités sont infinies. Découvrez les fonctionnalités et techniques avancées dans le [documentation](https://reference.aspose.com/3d/net/).

## FAQ

### Puis-je utiliser Aspose.3D pour .NET avec des langages de programmation autres que .NET ?

Aspose.3D prend principalement en charge .NET, mais il existe des versions disponibles pour Java et d'autres plates-formes.

### Un essai gratuit est-il disponible ?

Oui, vous pouvez tester les fonctionnalités d'Aspose.3D avec un [essai gratuit](https://releases.aspose.com/).

### Où puis-je trouver du support pour Aspose.3D pour .NET ?

Pour le soutien de la communauté, visitez le [Forum Aspose.3D](https://forum.aspose.com/c/3d/18).

### Comment puis-je obtenir un permis temporaire ?

Vous pouvez demander une licence temporaire [ici](https://purchase.conholdate.com/temporary-license/).

### Existe-t-il des tutoriels supplémentaires disponibles ?

Oui ! Découvrez plus de tutoriels et d'exemples dans le [documentation](https://reference.aspose.com/3d/net/).