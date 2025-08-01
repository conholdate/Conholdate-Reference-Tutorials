---
"description": "Découvrez comment enrichir vos documents Word avec des propriétés personnalisées grâce à Aspose.Words pour .NET. Ce guide complet vous guide pas à pas."
"linktitle": "Ajout de propriétés de document personnalisées dans Word"
"second_title": "API de traitement de documents Aspose.Words"
"title": "Ajout de propriétés de document personnalisées dans Word"
"url": "/fr/words/net/mastering-document-properties/adding-custom-document-properties-in-word/"
"weight": 10
---

## Introduction

Bienvenue ! Si vous explorez Aspose.Words pour .NET et souhaitez apprendre à ajouter des propriétés de document personnalisées à vos fichiers Word, vous êtes au bon endroit. Les propriétés personnalisées sont précieuses pour stocker des métadonnées supplémentaires que les propriétés intégrées ne couvrent pas. Que vous ayez besoin de suivre l'autorisation d'un document, les numéros de révision ou des dates spécifiques, les propriétés personnalisées peuvent vous être utiles. Dans ce tutoriel, nous vous guiderons pas à pas pour ajouter ces propriétés facilement avec Aspose.Words pour .NET. C'est parti !

## Prérequis

Avant de plonger dans le code, assurez-vous de disposer des éléments suivants :

1. Bibliothèque Aspose.Words pour .NET : téléchargez-la [ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : un IDE tel que Visual Studio.
3. Connaissances de base de C# : une connaissance de C# et de .NET sera utile.
4. Exemple de document : Préparez un exemple de document Word nommé `Properties.docx` pour modification.

## Importation d'espaces de noms

Pour accéder aux fonctionnalités d'Aspose.Words, vous devrez importer les espaces de noms nécessaires au début de votre code :

```csharp
using System;
using Aspose.Words;
```

## Étape 1 : Configuration du chemin du document

Définissons ensuite le chemin d'accès à votre document Word. Cette étape est essentielle pour localiser et ouvrir votre document. `Properties.docx` déposer.

```csharp
// Spécifiez le chemin d’accès à votre répertoire de documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

Assurez-vous de remplacer `"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre document.

## Étape 2 : Accéder aux propriétés du document personnalisé

Maintenant, accédons aux propriétés personnalisées du document Word, où résideront vos métadonnées personnalisées.

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
```

Cette ligne vous donne accès à la collection de propriétés personnalisées avec lesquelles vous travaillerez.

## Étape 3 : Vérification des propriétés existantes

Avant d'ajouter de nouvelles propriétés, il est judicieux de vérifier si une propriété existe déjà pour éviter les doublons.

```csharp
if (customDocumentProperties["Authorized"] != null) return;
```

Ce code vérifie si la propriété « Authorized » existe déjà. Si c'est le cas, la méthode se termine prématurément, évitant ainsi les doublons.

## Étape 4 : Ajout d'une propriété booléenne

Ajoutons une propriété booléenne personnalisée pour indiquer si le document est autorisé.

```csharp
customDocumentProperties.Add("Authorized", true);
```

Cette ligne ajoute une propriété nommée « Autorisé » et définit sa valeur sur `true`.

## Étape 5 : Ajout d'une propriété de chaîne

Ensuite, nous allons spécifier qui a autorisé le document en ajoutant une propriété de chaîne.

```csharp
customDocumentProperties.Add("Authorized By", "John Smith");
```

N'hésitez pas à remplacer « John Smith » par le nom de votre choix.

## Étape 6 : Ajout d'une propriété de date

Pour suivre le moment où le document a été autorisé, ajoutons une propriété de date.

```csharp
customDocumentProperties.Add("Authorized Date", DateTime.Today);
```

Cette ligne ajoute une propriété appelée « Date autorisée » et lui attribue la date du jour en utilisant `DateTime.Today`.

## Étape 7 : Ajout d'un numéro de révision

Pour le contrôle de version, nous pouvons ajouter une propriété pour garder une trace du numéro de révision du document.

```csharp
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
```

Ici, nous ajoutons une propriété « Révision autorisée » qui contient le numéro de révision actuel du document.

## Étape 8 : Ajout d'une propriété numérique

Enfin, ajoutons une propriété numérique pour stocker un montant autorisé, comme un chiffre budgétaire.

```csharp
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Cette ligne ajoute une propriété nommée « Montant autorisé » avec une valeur de `123.45`Vous pouvez ajuster ce nombre selon vos besoins.

## Conclusion

Félicitations ! Vous avez ajouté des propriétés de document personnalisées à un document Word avec Aspose.Words pour .NET. Ces propriétés constituent un moyen puissant de stocker des métadonnées adaptées à vos besoins, qu'il s'agisse de suivre les détails d'autorisation, les numéros de révision ou des montants spécifiques.

## FAQ

### Que sont les propriétés de document personnalisées ?
Les propriétés de document personnalisées sont des métadonnées que vous pouvez ajouter à un document Word pour stocker des informations supplémentaires non couvertes par les propriétés intégrées.

### Puis-je ajouter des propriétés autres que des chaînes et des nombres ?
Oui, vous pouvez ajouter différents types de propriétés, notamment des valeurs booléennes, des dates et même des objets personnalisés.

### Comment puis-je accéder à ces propriétés dans un document Word ?
Vous pouvez accéder aux propriétés personnalisées par programmation à l’aide d’Aspose.Words ou les afficher directement dans Word via les propriétés du document.

### Est-il possible de modifier ou de supprimer des propriétés personnalisées ?
Absolument ! Vous pouvez facilement modifier ou supprimer des propriétés personnalisées grâce aux méthodes fournies par Aspose.Words.

### Les propriétés personnalisées peuvent-elles être utilisées pour filtrer des documents ?
Oui ! Les propriétés personnalisées sont idéales pour catégoriser et filtrer des documents en fonction de métadonnées spécifiques.