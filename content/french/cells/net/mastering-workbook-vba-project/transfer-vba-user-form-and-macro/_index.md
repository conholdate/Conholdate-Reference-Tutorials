---
"description": "Exploitez toute la puissance de l'automatisation Excel grâce à ce guide complet sur le transfert de formulaires utilisateur VBA et de macros entre classeurs à l'aide d'Aspose.Cells pour .NET. Idéal pour les développeurs débutants comme expérimentés."
"linktitle": "Transférer des formulaires utilisateur VBA et des macros entre des classeurs Excel"
"second_title": "API de traitement Excel Aspose.Cells .NET"
"title": "Transférer des formulaires utilisateur VBA et des macros entre des classeurs Excel"
"url": "/fr/cells/net/mastering-workbook-vba-project/transfer-vba-user-form-and-macro/"
"weight": 11
---

## Introduction

Bienvenue dans votre guide ultime pour améliorer votre expérience Excel grâce aux macros VBA et aux formulaires utilisateur ! Dans ce tutoriel, nous allons découvrir comment transférer un concepteur de macros VBA UserForm d'un classeur à un autre grâce à la puissante bibliothèque Aspose.Cells pour .NET. Que vous soyez un développeur expérimenté ou débutant, ce guide étape par étape vous permettra d'acquérir les connaissances nécessaires pour gérer vos fichiers Excel par programmation. Prêt à vous lancer ? C'est parti !

## Prérequis
Avant de passer au codage, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1. Environnement de développement C# : un environnement de travail pour le développement C#, avec Visual Studio fortement recommandé.
2. Bibliothèque Aspose.Cells pour .NET : assurez-vous d'intégrer la bibliothèque Aspose.Cells à votre projet. Vous pouvez facilement [téléchargez-le ici](https://releases.aspose.com/cells/net/).
3. Connaissances de base de VBA et des macros Excel : la familiarité avec VBA et le fonctionnement des macros Excel améliorera votre compréhension de ce didacticiel.
4. Un fichier Excel avec un formulaire utilisateur : créez ou obtenez un classeur Excel contenant un formulaire utilisateur (de préférence avec des macros activées, comme `.xlsm` fichiers).

## Importation des packages requis
Pour utiliser les fonctionnalités fournies par Aspose.Cells, incluez les espaces de noms suivants en haut de votre fichier C# :

```csharp
using System;
using Aspose.Cells;
using Aspose.Cells.Vba;
```

Ces espaces de noms vous donneront accès aux puissants outils intégrés à la bibliothèque Aspose.Cells.

## Étape 1 : Définissez vos répertoires source et de sortie
Tout d’abord, définissez les emplacements de vos fichiers :

```csharp
// Définir les répertoires source et de sortie
string sourceDir = @"Your\Source\Directory\";
string outputDir = @"Your\Output\Directory\";
```

Remplacez les chemins d’espace réservé par les répertoires réels dans lesquels vos fichiers sont stockés.

## Étape 2 : créer un classeur cible vide
Ensuite, créez un nouveau classeur dans lequel vous copierez le formulaire utilisateur et les macros :

```csharp
// Créer un classeur cible vide
Workbook target = new Workbook();
```

Cela initialise un classeur vierge, servant de toile pour le transfert de données à venir.

## Étape 3 : Chargez votre classeur modèle
Chargez le classeur contenant votre formulaire utilisateur et vos macros :

```csharp
// Charger le fichier Excel contenant le formulaire utilisateur VBA-Macro Designer
Workbook templateFile = new Workbook(sourceDir + "sampleDesignerForm.xlsm");
```

Ajuster `"sampleDesignerForm.xlsm"` au nom de votre fichier actuel.

## Étape 4 : Copier les feuilles de calcul dans le classeur cible
Maintenant, copions les feuilles de calcul du modèle vers le classeur cible :

```csharp
// Copiez toutes les feuilles de calcul du modèle dans le classeur cible
foreach (Worksheet ws in templateFile.Worksheets)
{
    if (ws.Type == SheetType.Worksheet)
    {
        Worksheet s = target.Worksheets.Add(ws.Name);
        s.Copy(ws);
        // Ajouter un message dans la cellule A2 de la feuille de calcul cible
        s.Cells["A2"].PutValue("VBA Macro and User Form copied from template to target.");
    }
}
```

Ce code parcourt chaque feuille de calcul du modèle et la copie dans le classeur cible, garantissant ainsi que toutes vos données sont transférées de manière transparente.

## Étape 5 : Copier les macros VBA à partir du modèle
Ensuite, nous allons copier les macros VBA, y compris les modules UserForm Designer, dans le nouveau classeur :

```csharp
// Copier l'UserForm du concepteur de macros VBA du modèle vers la cible
foreach (VbaModule vbaItem in templateFile.VbaProject.Modules)
{
    if (vbaItem.Name == "ThisWorkbook")
    {
        // Copier le code du module ThisWorkbook
        target.VbaProject.Modules["ThisWorkbook"].Codes = vbaItem.Codes;
    }
    else
    {
        // Copier le code et les données d'autres modules
        int vbaMod = target.VbaProject.Modules.Add(vbaItem.Type, vbaItem.Name);
        target.VbaProject.Modules[vbaMod].Codes = vbaItem.Codes;

        if (vbaItem.Type == VbaModuleType.Designer)
        {
            // Obtenir le stockage du concepteur de formulaires utilisateur
            byte[] designerStorage = templateFile.VbaProject.Modules.GetDesignerStorage(vbaItem.Name);
            // Ajoutez le stockage du concepteur au projet VBA cible
            target.VbaProject.Modules.AddDesignerStorage(vbaItem.Name, designerStorage);
        }
    }
}
```

Ce code garantit que non seulement le code mais également la conception du formulaire utilisateur sont copiés, préservant ainsi la fonctionnalité de vos macros.

## Étape 6 : Enregistrer le classeur cible
Une fois le processus de copie terminé, enregistrez votre nouveau classeur :

```csharp
// Enregistrer le classeur cible
target.Save(outputDir + "outputDesignerForm.xlsm", SaveFormat.Xlsm);
```

Modifiez le nom du fichier de sortie selon vos besoins. Cette étape crée votre classeur personnalisé, rempli de macros et de formulaires utilisateur.

## Étape 7 : Confirmer le succès
Enfin, imprimez un message de réussite sur la console :

```csharp
Console.WriteLine("CopyVBAMacroUserFormDesignerStorageToWorkbook executed successfully.\r\n");
```

Cette simple ligne vous rassure que votre processus s’est bien déroulé, une confirmation essentielle de votre travail acharné !

## Conclusion
Félicitations ! Vous avez appris à copier un concepteur de formulaires utilisateur VBA d'un classeur à un autre avec Aspose.Cells pour .NET. Même si cela peut paraître intimidant au début, la pratique vous permettra de maîtriser les manipulations dans les classeurs. N'oubliez pas que le codage est une question d'expérimentation ; n'hésitez donc pas à explorer les différentes fonctionnalités de vos fichiers Excel. Si vous avez des questions ou besoin d'aide, les forums et la documentation Aspose sont d'excellentes ressources.

## FAQ

### Quelles versions d'Excel Aspose.Cells prend-il en charge ?
Aspose.Cells prend en charge divers formats Excel, notamment XLSX, XLSM, CSV, etc.

### Puis-je utiliser Aspose.Cells gratuitement ?
Oui ! Vous pouvez commencer par un essai gratuit pour évaluer la bibliothèque : [Essai gratuit](https://releases.aspose.com/).

### Ai-je besoin de Visual Studio pour exécuter ce code ?
Bien que Visual Studio soit recommandé pour ses fonctionnalités conviviales, tout IDE C# prenant en charge le développement .NET suffira.

### Où puis-je trouver plus d'exemples et de documentation ?
Vous pouvez explorer le [Documentation d'Aspose.Cells](https://reference.aspose.com/cells/net/) pour plus d'exemples et d'explications approfondies.

### Comment résoudre les problèmes lors de l’utilisation d’Aspose.Cells ?
Vous devriez visiter le [Forum d'assistance Aspose](https://forum.aspose.com/c/cells/9) pour l'aide de la communauté et du personnel de soutien d'Aspose.