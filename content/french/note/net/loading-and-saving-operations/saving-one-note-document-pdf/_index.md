---
"description": "Découvrez comment enregistrer efficacement des documents Microsoft OneNote au format PDF avec Aspose.Note pour .NET. Ce guide vous explique les prérequis nécessaires et propose une FAQ utile."
"linktitle": "Enregistrement de documents OneNote au format PDF"
"second_title": "API .NET Aspose.Note"
"title": "Enregistrer des documents OneNote au format PDF avec Aspose.Note pour .NET"
"url": "/fr/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Introduction

Dans ce tutoriel, nous découvrirons comment enregistrer des documents au format PDF avec Aspose.Note pour .NET. Aspose.Note est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers Microsoft OneNote par programmation. Nous aborderons les prérequis, importerons des espaces de noms et fournirons des guides étape par étape pour enregistrer des documents au format PDF dans différentes mises en page.

## Prérequis
1. Visual Studio : assurez-vous qu’il est installé.
2. Aspose.Note pour .NET : téléchargez et installez la bibliothèque.
3. Connaissances C# : Une compréhension de base du langage est requise.

## Importation des espaces de noms nécessaires
Avant de continuer, importez les espaces de noms suivants dans votre code :

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Étape 1 : Enregistrer au format PDF avec les paramètres de page Lettre
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Mettre à jour ce chemin
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Charge le document OneNote et l’enregistre au format PDF en utilisant les paramètres de page au format lettre.

## Étape 2 : Enregistrer au format PDF avec les paramètres de page A4 (aucune limite de hauteur)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Mettre à jour ce chemin
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Similaire à l’étape 1 mais utilise les paramètres de page A4 sans limitations de hauteur.

## Conclusion
Ce tutoriel montre comment convertir des fichiers OneNote au format PDF avec Aspose.Note. L'utilisation de différents paramètres de page permet aux développeurs de gagner en flexibilité dans la gestion des documents.

## FAQ
### Aspose.Note peut-il gérer des fichiers OneNote complexes ?
Oui, il gère efficacement diverses fonctionnalités des fichiers OneNote complexes.

### Aspose.Note est-il adapté aux projets commerciaux ?
Oui, vous pouvez l'utiliser pour des applications commerciales après l'achat d'une licence.

### Aspose.Note propose-t-il un essai gratuit ?
Oui, un essai gratuit est disponible pour l'exploration.

### Où puis-je trouver la documentation pour Aspose.Note ?
Une documentation détaillée est disponible sur le site de référence Aspose.

### Besoin d'aide supplémentaire ?
Pour toute question ou assistance, reportez-vous au forum Aspose.Note.