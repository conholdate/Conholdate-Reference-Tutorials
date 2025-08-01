---
"description": "Découvrez comment améliorer la navigation dans vos documents PDF en créant des hyperliens locaux avec Aspose.PDF pour .NET. Ce tutoriel vous guide pas à pas tout au long du processus."
"linktitle": "Création d'un lien hypertexte local dans un fichier PDF"
"second_title": "Référence de l'API Aspose.PDF pour .NET"
"title": "Création d'un lien hypertexte local dans un fichier PDF"
"url": "/fr/pdf/net/mastering-links-and-actions/creating-local-hyperlink/"
"weight": 40
---

## Introduction

Dans ce guide, nous vous expliquerons comment créer des hyperliens locaux dans un fichier PDF avec Aspose.PDF pour .NET. Chaque étape sera détaillée clairement, afin que même si vous débutez en manipulation de PDF, vous puissiez suivre le processus sans effort.

## Prérequis

Avant de plonger dans le code, assurez-vous de disposer des éléments suivants :

1. Visual Studio : Téléchargez-le depuis le [Site Web de Visual Studio](https://visualstudio.microsoft.com/).
2. Aspose.PDF pour .NET : Téléchargez la bibliothèque via le [Site Web d'Aspose](https://releases.aspose.com/pdf/net/)Cette bibliothèque fournit un riche ensemble de fonctionnalités pour la manipulation de PDF.
3. Connaissances de base de C# : une familiarité avec la programmation C# vous aidera, mais ne vous inquiétez pas ; nous vous expliquerons le code ligne par ligne.
4. .NET Framework : Assurez-vous que .NET Framework est installé sur votre ordinateur. Consultez la configuration requise sur le fichier Aspose.PDF. [documentation](https://reference.aspose.com/pdf/net/).

Avec ces prérequis en place, vous êtes prêt à apprendre à créer des hyperliens locaux dans vos documents PDF !

## Importation des packages requis

Maintenant que vous êtes tous configurés, il est temps d'importer les packages nécessaires dans votre projet C#.

### Ouvrez votre projet

Ouvrez votre projet .NET existant ou créez-en un nouveau dans Visual Studio. Si vous démarrez de zéro, sélectionnez « Créer un nouveau projet » dans l'écran de démarrage.

### Ajouter une référence à Aspose.PDF

Faites un clic droit sur « Dépendances » dans le dossier de votre projet dans l'Explorateur de solutions. Sélectionnez « Gérer les packages NuGet », puis recherchez `Aspose.PDF`et installez la dernière version disponible. Vous disposerez ainsi de tous les outils nécessaires à la création et à la manipulation de PDF.

### Importer des espaces de noms

En haut de votre fichier .cs, ajoutez les directives using suivantes :

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ces directives vous permettent d'accéder aux fonctionnalités de la bibliothèque de manière transparente.

Décomposons le processus de création d’hyperliens locaux en étapes simples.

## Étape 1 : Configurer l'instance de document

Créer une nouvelle instance du `Document` classe, représentant le fichier PDF avec lequel vous travaillerez.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Définissez votre répertoire de documents
Document doc = new Document(); // Créer une instance de document
```

Remplacer `"YOUR_DOCUMENT_DIRECTORY"` avec le chemin réel sur votre système où le PDF sera enregistré.

## Étape 2 : Ajouter une page au document

Ensuite, ajoutez une page à votre document PDF.

```csharp
Page page = doc.Pages.Add(); // Ajouter une nouvelle page
```

Cette ligne ajoute une nouvelle page au document, où tout votre contenu sera placé.

## Étape 3 : Créer un fragment de texte

Maintenant, créons un morceau de texte qui fera office de lien cliquable.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7"); // Créer un fragment de texte
```

Ce `TextFragment` affichera le texte sur lequel les utilisateurs peuvent cliquer.

## Étape 4 : Créer un lien hypertexte local

Créez maintenant un lien hypertexte local qui pointe vers la page 7.

```csharp
LocalHyperlink link = new LocalHyperlink(); // Créer un lien hypertexte local
link.TargetPageNumber = 7; // Définir la page cible pour le lien
text.Hyperlink = link; // Définir l'hyperlien pour le fragment de texte
```

Le `LocalHyperlink` la classe vous permet de spécifier le numéro de page cible pour l'hyperlien.

## Étape 5 : ajouter le fragment de texte à la page

Ajoutez le texte cliquable à la page que vous avez créée.

```csharp
page.Paragraphs.Add(text); // Ajouter le fragment de texte à la page
```

Cette ligne ajoute votre texte à la collection de paragraphes de la page.

## Étape 6 : Créer un autre fragment de texte (facultatif)

Ajoutons un autre lien hypertexte pour revenir à la page 1.

```csharp
TextFragment textBack = new TextFragment("Link to page 1"); // Créer un nouveau fragment de texte
textBack.IsInNewPage = true; // Indiquez qu'il doit être sur une nouvelle page
```

## Étape 7 : Configurer le deuxième lien hypertexte local

Créez un autre lien hypertexte local pour la page 1.

```csharp
Aspose.Pdf.LocalHyperlink linkBack = new Aspose.Pdf.LocalHyperlink(); // Créer un autre lien hypertexte local
linkBack.TargetPageNumber = 1; // Définir la page cible pour le deuxième lien hypertexte
textBack.Hyperlink = linkBack; // Définir l'hyperlien pour le deuxième fragment de texte
```

## Étape 8 : Ajouter le deuxième fragment de texte à la nouvelle page

Ajoutez le deuxième fragment de texte à sa page.

```csharp
Page newPage = doc.Pages.Add(); // Ajouter une nouvelle page pour le deuxième lien
newPage.Paragraphs.Add(textBack); // Ajouter le fragment de texte à la nouvelle page
```

## Étape 9 : Enregistrer le document

Enfin, enregistrez votre document.

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Spécifier le nom du fichier de sortie
doc.Save(dataDir); // Enregistrer le document mis à jour
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```

Cette ligne combine votre chemin de répertoire avec le nom du fichier et le `Save()` la méthode enregistre votre document.

## Conclusion

Créer des hyperliens locaux dans les fichiers PDF avec Aspose.PDF pour .NET est une fonctionnalité pratique qui améliore la navigation et l'expérience utilisateur. Vous disposez désormais des connaissances nécessaires pour guider vos lecteurs directement vers les informations dont ils ont besoin, rendant ainsi vos PDF plus interactifs et conviviaux.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et convertir des documents PDF par programmation à l'aide du framework .NET.

### Puis-je créer des hyperliens vers des pages Web externes ?
Oui, Aspose.PDF prend également en charge la création d'hyperliens vers des URL externes en plus des hyperliens locaux dans le PDF.

### Existe-t-il un essai gratuit pour Aspose.PDF ?
Absolument ! Vous pouvez accéder à l'essai gratuit depuis le [Site Web d'Aspose](https://releases.aspose.com/).

### Quels langages de programmation Aspose prend-il en charge ?
Aspose propose des bibliothèques pour divers langages de programmation, notamment Java, C++ et Python, entre autres.

### Comment obtenir de l'assistance pour les produits Aspose ?
Vous pouvez demander de l'aide via le [Forum Aspose](https://forum.aspose.com/c/pdf/10).