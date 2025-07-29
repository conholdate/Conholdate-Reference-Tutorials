---
"description": "Apprenez à copier efficacement des données dans un classeur Excel avec Aspose.Cells pour .NET. Suivez ce guide étape par étape pour dupliquer facilement des feuilles, transférer des données et gérer des fichiers Excel."
"linktitle": "Copier des données dans un classeur Excel à l'aide d'Aspose.Cells pour .NET"
"second_title": "API de traitement Excel Aspose.Cells .NET"
"title": "Copier des données dans un classeur Excel à l'aide d'Aspose.Cells pour .NET"
"url": "/fr/cells/net/mastering-worksheet-value-operations/copy-data-within-excel-workbook/"
"weight": 12
---

## Introduction

Dans ce guide détaillé, nous vous montrerons comment copier des données au sein d'un même classeur avec Aspose.Cells pour .NET. En suivant les instructions détaillées ci-dessous, vous apprendrez à dupliquer des feuilles par programmation, tout en préservant leur contenu et leur mise en forme.

## Conditions préalables à la copie de données dans Excel avec Aspose.Cells

Avant de plonger dans le processus de codage, assurons-nous que tout est en place :

1. Bibliothèque Aspose.Cells pour .NET : La bibliothèque Aspose.Cells pour .NET doit être installée. Vous pouvez télécharger la dernière version sur le site. [Page de téléchargement d'Aspose.Cells pour .NET](https://releases.aspose.com/cells/net/).
2. Environnement de développement : un IDE compatible .NET tel que Visual Studio est nécessaire pour écrire et exécuter votre code.
3. Licence Aspose : vous pouvez utiliser une version d'essai gratuite ou une licence payante. Pour plus d'informations, consultez le site [ici](https://purchase.aspose.com/temporary-license/).

Une fois les prérequis définis, vous êtes prêt à commencer à travailler avec la bibliothèque.

## Importation des packages requis

Pour commencer, vous devrez importer les espaces de noms pertinents depuis Aspose.Cells. Cela vous permettra de travailler avec des fichiers Excel à l'aide des classes et méthodes fournies par Aspose.Cells.

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

Ces espaces de noms vous donneront accès à `Workbook` classe (pour travailler avec des fichiers Excel) et `WorksheetCollection` (pour accéder à plusieurs feuilles dans un classeur).

## Étape 1 : Initialiser les chemins d'accès aux fichiers du classeur

Pour organiser votre code, il est essentiel de définir les chemins d'accès à votre classeur et à l'emplacement où vous souhaitez enregistrer le fichier modifié. Voici comment spécifier ces chemins :

```csharp
// Définissez le chemin du répertoire où se trouve le fichier Excel.
string dataDir = "Your Directory Path";

// Définissez le chemin complet vers le classeur d’entrée.
string inputPath = dataDir + "book1.xls";
```

Remplacer `"Your Directory Path"` avec le chemin d'accès réel au répertoire contenant le classeur. Cela garantit la flexibilité du code et une gestion efficace des chemins.

## Étape 2 : Ouvrez le classeur pour accéder aux données

Maintenant que les chemins d'accès aux fichiers sont définis, l'étape suivante consiste à charger le classeur Excel dans un `Workbook` objet. Cela vous permet d'accéder à son contenu pour le manipuler.

```csharp
// Chargez le fichier Excel dans l’objet Classeur.
Workbook wb = new Workbook(inputPath);
```

Avec cette ligne, vous avez chargé avec succès `book1.xls` dans le `wb` objet, rendant ses données accessibles.

## Étape 3 : Accéder à la collection de feuilles de travail

Une fois le classeur chargé, vous pouvez accéder aux feuilles qu'il contient. Aspose.Cells fournit les `Worksheets` collection, qui vous permet d'interagir avec chaque feuille de calcul du classeur.

```csharp
// Récupérez la collection de feuilles de calcul du classeur.
WorksheetCollection sheets = wb.Worksheets;
```

Le `sheets` L'objet vous donne désormais accès à toutes les feuilles de calcul qu'il contient `book1.xls`, et vous pouvez effectuer diverses opérations sur eux, notamment la copie de données d'une feuille à une autre.

## Étape 4 : Copier les données d’une feuille à une autre

Pour copier des données d'une feuille de calcul à une autre dans le même classeur, Aspose.Cells propose une méthode simple à utiliser appelée `AddCopy`Cette méthode crée un duplicata de la feuille de calcul spécifiée et l'ajoute au classeur.

```csharp
// Copiez les données de « Feuille 1 » vers une nouvelle feuille du classeur.
sheets.AddCopy("Sheet1");
```

Dans cet exemple, nous copions des données de « Feuille 1 » vers une nouvelle feuille. `AddCopy` La méthode dupliquera la feuille entière, en préservant tout son contenu, y compris les formules, la mise en forme et les valeurs.

## Étape 5 : Enregistrer le classeur modifié

Après avoir copié les données, vous pouvez enregistrer le classeur modifié sous un nouveau nom ou un nouvel emplacement. Pour ce faire, appelez la commande `Save` méthode sur le `Workbook` objet.

```csharp
// Enregistrez le classeur modifié sous un nouveau nom.
wb.Save(dataDir + "book1_copy.xls");
```

Cela enregistrera le classeur avec la feuille copiée sous `book1_copy.xls` dans le répertoire spécifié. Vous pouvez modifier le nom et le chemin du fichier selon vos besoins.

## Conclusion

Copier des données dans un classeur Excel avec Aspose.Cells pour .NET est une tâche simple, et ce guide explique comment le faire efficacement. Que vous dupliquiez des feuilles entières ou des plages de données spécifiques, Aspose.Cells propose une API robuste et flexible qui simplifie et optimise l'automatisation d'Excel.

## FAQ

### Puis-je copier plusieurs feuilles à la fois ?

Aspose.Cells ne permet pas de copier plusieurs feuilles en un seul appel. Cependant, vous pouvez parcourir les feuilles à copier et les copier individuellement.

### Comment puis-je renommer la feuille copiée ?

Après avoir copié la feuille, vous pouvez la renommer comme suit :

```csharp
sheets[sheets.Count - 1].Name = "NewSheetName";
```

### Aspose.Cells est-il compatible avec .NET Core ?

Oui, Aspose.Cells est entièrement compatible avec les environnements .NET Framework et .NET Core.

### Comment Aspose.Cells gère-t-il le formatage pendant la copie ?

Le `AddCopy` La méthode préserve tout le contenu et le formatage lors de la copie des feuilles, garantissant que les données copiées sont identiques à l'original.

### Puis-je copier une feuille dans un autre classeur ?

Oui, vous pouvez copier une feuille dans un autre classeur en utilisant le `Copy` méthode avec une référence au classeur cible.

```csharp
sheets.Add().Copy(wb.Worksheets["Sheet1"]);
```