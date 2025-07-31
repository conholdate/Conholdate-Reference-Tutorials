---
"description": "Découvrez comment définir l’ordre des informations personnalisées dans MHTML à l’aide d’Aspose.Email pour .NET dans ce didacticiel étape par étape."
"linktitle": "Ordre personnalisé des informations en MHTML avec Aspose.Email"
"second_title": "API de traitement des e-mails Aspose.Email .NET"
"title": "Ordre personnalisé des informations en MHTML avec Aspose.Email"
"url": "/fr/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## Introduction

Créer des formats d'e-mail enrichis peut grandement améliorer la communication, notamment lors de l'exportation d'e-mails vers différents formats de fichier comme MHTML. Aspose.Email pour .NET offre aux développeurs une boîte à outils puissante pour manipuler les e-mails, notamment pour définir un ordre d'affichage personnalisé des informations lors de l'exportation vers MHTML. Dans ce guide, nous détaillons les étapes nécessaires pour y parvenir, afin que vous puissiez suivre facilement la procédure, que vous soyez un développeur expérimenté ou débutant. Alors, allons-y !

## Prérequis

Avant de vous lancer dans la définition de l'ordre personnalisé des informations dans MHTML, vous devez vérifier quelques conditions préalables dans votre liste :

1. Environnement de développement .NET : Assurez-vous de disposer d'un environnement de développement .NET. Vous pouvez utiliser Visual Studio, Visual Studio Code ou tout autre IDE compatible.

2. Bibliothèque Aspose.Email : La bibliothèque Aspose.Email pour .NET doit être installée. Vous pouvez télécharger la dernière version sur le site. [Page de publication d'Aspose](https://releases.aspose.com/email/net/).

3. Compréhension de base de C# : la familiarité avec la programmation C# vous aidera à mieux comprendre le code.

4. Exemple de fichier de courrier électronique : vous aurez besoin d'un échantillon `.eml` fichier (par exemple, `Attachments.eml`) à des fins de test.

Une fois ces prérequis réunis, vous êtes prêt à suivre le tutoriel !

## Importer des packages

Pour commencer votre code, vous devrez importer les espaces de noms nécessaires depuis la bibliothèque Aspose.Email. Ceci est essentiel pour accéder à toutes les classes et méthodes nécessaires à la manipulation des fichiers e-mail.

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

Ajoutez-les en haut de votre fichier C#. Vous êtes maintenant prêt à vous lancer dans le codage !

Maintenant que tout est configuré, décomposons le didacticiel en étapes faciles à gérer.

## Étape 1 : définissez votre répertoire de données

La première chose à faire est de créer un répertoire où seront stockés vos fichiers de courrier électronique. Il peut s'agir de n'importe quel chemin sur votre machine locale.

```csharp
string dataDir = "Your Data Directory";
```

Remplacer `"Your Data Directory"` avec le chemin réel où votre `.eml` fichier se trouve. Par exemple, si votre fichier se trouve dans `C:\Emails`, vous écririez :

```csharp
string dataDir = @"C:\Emails\";
```

## Étape 2 : Charger le message électronique

Ensuite, vous devez charger le `.eml` fichier dans un `MailMessage` objet. Cela vous permet de manipuler le contenu et les métadonnées de l'e-mail.

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

Assurez-vous que le nom du fichier correspond à celui du répertoire spécifié. Si votre fichier porte un nom différent, modifiez-le en conséquence.

## Étape 3 : Configurer les options d’enregistrement MHTML

Une fois votre e-mail chargé, il est temps de définir comment vous souhaitez l'enregistrer au format MHTML. Vous pouvez commencer avec les options par défaut.

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

Cette ligne initialise les options d'enregistrement MHTML, préparant le terrain pour la personnalisation ultérieure des en-têtes.

## Étape 4 : Enregistrer le fichier MHTML avec l'ordre par défaut

Enregistrons l'e-mail au format MHTML en respectant l'ordre par défaut. Cela vous donnera une base de comparaison après la personnalisation.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

Exécutez cette ligne et vérifiez le répertoire spécifié. Vous devriez alors voir un nouveau fichier MHTML nommé `CustomOrderOfInformationInMHTML_1.mhtml`Ouvrez-le pour voir comment les informations sont affichées par défaut.

## Étape 5 : Personnaliser l’ordre des en-têtes

Voici la partie amusante ! Vous pouvez spécifier les en-têtes à inclure dans la sortie MHTML et leur ordre. Commençons par quelques en-têtes courants.

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

En ajoutant ces en-têtes, vous indiquez à Aspose comment vous souhaitez que l'e-mail soit affiché.

## Étape 6 : Enregistrer MHTML avec une commande personnalisée

Après avoir personnalisé les en-têtes, vous devez enregistrer à nouveau l'e-mail au format MHTML pour voir comment le nouvel ordre affecte la sortie.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

Exécutez ce code, puis ouvrez `CustomOrderOfInformationInMHTML_2.mhtml`Comparez-le avec le premier pour voir comment les informations ont changé en fonction de l'ordre de votre en-tête.

## Étape 7 : Effacer et ajouter un nouvel ordre d’en-tête

Et si vous souhaitez un ordre complètement différent ? Vous pouvez repartir de zéro en effaçant les paramètres d'en-tête existants.

```csharp
opt.RenderingHeaders.Clear();
```

Il est maintenant temps de définir un nouvel ordre pour les en-têtes. Par exemple, si vous souhaitez prioriser les pièces jointes et les destinataires en copie :

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## Étape 8 : Enregistrer le fichier MHTML avec une nouvelle commande personnalisée

Enfin, enregistrez l’e-mail une dernière fois avec les nouveaux paramètres d’en-tête.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

Après avoir exécuté cette ligne, ouvrez `CustomOrderOfInformationInMHTML_3.mhtml` et vérifiez comment il présente les informations en fonction de votre nouvelle personnalisation.

## Conclusion

Et voilà : un guide simple pour définir un ordre personnalisé d'informations en MHTML avec Aspose.Email pour .NET. En suivant ces étapes, vous pouvez contrôler la représentation de vos e-mails au format MHTML et garantir que les informations les plus importantes soient présentées de manière adaptée à vos besoins. 

## FAQ

### Qu'est-ce que MHTML ?
MHTML signifie « MIME HTML », un format d'archive de pages Web qui combine HTML et d'autres ressources comme des images.

### Puis-je utiliser Aspose.Email gratuitement ?
Oui, Aspose propose une version d'essai gratuite pour les développeurs. Vous pouvez la trouver. [ici](https://releases.aspose.com/).

### Que faire si je rencontre des problèmes lors de l’utilisation d’Aspose.Email ?
Vous pouvez obtenir du soutien de la communauté via le [Forum Aspose](https://forum.aspose.com/c/email/12/).

### Une licence temporaire est-elle disponible pour Aspose.Email ?
Oui, vous pouvez demander un permis temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Où puis-je acheter Aspose.Email ?
Vous pouvez acheter la bibliothèque à ce [lien](https://purchase.aspose.com/buy).