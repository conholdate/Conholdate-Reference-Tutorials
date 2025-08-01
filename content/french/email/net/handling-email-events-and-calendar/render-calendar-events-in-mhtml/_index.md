---
"description": "Affichez les événements de votre calendrier au format MHTML avec Aspose.Email pour .NET. Apprenez étape par étape à personnaliser et enregistrer des fichiers MSG avec C#."
"linktitle": "Afficher les événements du calendrier en MHTML avec Aspose.Email"
"second_title": "API de traitement des e-mails Aspose.Email .NET"
"title": "Afficher les événements du calendrier en MHTML avec Aspose.Email"
"url": "/fr/email/net/handling-email-events-and-calendar/render-calendar-events-in-mhtml/"
"weight": 15
---

## Introduction

Aspose.Email pour .NET est une bibliothèque puissante pour gérer les tâches liées aux e-mails dans les applications .NET. Un cas d'utilisation fascinant est le rendu programmatique des événements de calendrier en C#. Que vous développiez une fonctionnalité d'intégration de calendrier ou que vous créiez des visionneuses d'e-mails personnalisées, ce tutoriel vous guidera dans le rendu précis et personnalisé des événements de calendrier au format MHTML.

## Prérequis

Avant de plonger, assurons-nous que nous avons tout prêt pour suivre ce tutoriel :

1. Bibliothèque Aspose.Email pour .NET : téléchargez la dernière version de la bibliothèque à partir du [Page de téléchargement d'Aspose.Email pour .NET](https://releases.aspose.com/email/net/).
2. Environnement de développement : Visual Studio (ou votre IDE C# préféré) installé sur votre système.
3. Licence : Obtenez une licence valide pour Aspose.Email. À des fins d'évaluation, vous pouvez utiliser une licence. [permis temporaire](https://purchase.aspose.com/temporary-license/).
4. Exemple de fichier MSG : un fichier MSG d'événement de calendrier. Vous pouvez utiliser n'importe quel fichier. `.msg` fichier avec des événements de calendrier, tels que « Réunion avec occurrences récurrentes.msg ».

## Importer des packages

Pour commencer, incluez les espaces de noms nécessaires dans votre projet. 

```csharp
using System;
using Aspose.Email;
using Aspose.Email.Mht;
```

Passons maintenant au guide étape par étape !

## Étape 1 : Charger le fichier MSG de l'événement du calendrier

Nous commençons par charger le fichier MSG contenant l'événement de calendrier. Cette étape est essentielle car elle sert de base au rendu de l'événement au format MHTML.


```csharp
string dataDir = "Your Data Directory";
string fileName = "Meeting with Recurring Occurrences.msg";

// Charger le fichier MSG
MailMessage msg = MailMessage.Load(dataDir + fileName);
```

- `dataDir`: Spécifie le répertoire dans lequel votre fichier MSG est stocké.
- `fileName`: Nom du fichier d'événement du calendrier.
- `MailMessage.Load`: Lit le fichier et le charge dans un `MailMessage` objet.

## Étape 2 : Configurer les options d’enregistrement MHTML

Ensuite, nous configurons les options de rendu de l'événement de calendrier au format MHTML. Cela inclut l'activation de formats, d'en-têtes et d'autres propriétés spécifiques pour la personnalisation.

```csharp
MhtSaveOptions options = new MhtSaveOptions
{
    MhtFormatOptions = MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent
};
```

- `MhtSaveOptions`: Représente les paramètres d'enregistrement des fichiers MHTML.
- `MhtFormatOptions`: Configure des options telles que l'inclusion d'en-têtes et le rendu des événements du calendrier.

## Étape 3 : Personnaliser les modèles d’affichage

Ici, nous définissons comment certaines propriétés, comme l'heure de début de l'événement, doivent apparaître dans la sortie. Cette étape permet d'obtenir une sortie hautement personnalisable et lisible.


```csharp
if (options.FormatTemplates.ContainsKey(MhtTemplateName.Start))
    options.FormatTemplates[MhtTemplateName.Start] = @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>";
else
    options.FormatTemplates.Add(MhtTemplateName.Start, @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

- `MhtTemplateName.Start`: Fait référence à la propriété « Démarrer » de l'événement du calendrier.
- `options.FormatTemplates`: Personnalise le modèle d'affichage pour des propriétés spécifiques.

## Étape 4 : Enregistrer l’événement du calendrier au format MHTML

Enfin, enregistrez l’événement du calendrier dans un fichier MHTML avec les options configurées.


```csharp
msg.Save(dataDir + "Meeting with Recurring Occurrences.mhtml", options);
```

- `msg.Save`: Enregistre le message dans le format et l'emplacement spécifiés.
- `Meeting with Recurring Occurrences.mhtml`: Nom du fichier de sortie.

## Conclusion

Le rendu des événements de calendrier avec Aspose.Email pour .NET est à la fois efficace et hautement personnalisable. En suivant les étapes ci-dessus, vous pouvez facilement convertir les événements de calendrier en fichier MHTML, avec un formatage personnalisé.

## FAQ

### Qu'est-ce que MHTML ?
MHTML est un format de fichier d'archive Web qui contient du HTML et des ressources associées telles que des images, ce qui le rend adapté au rendu et au partage d'événements de calendrier.

### Puis-je restituer des événements récurrents ?
Oui ! Aspose.Email prend en charge le rendu des événements récurrents, garantissant que tous les détails sont capturés avec précision.

### Une licence est-elle requise ?
Oui, un permis valide est nécessaire. Vous pouvez en faire la demande. [permis temporaire](https://purchase.aspose.com/temporary-license/) pour évaluation.

### Puis-je ajouter des propriétés personnalisées à la sortie ?
Absolument ! Vous pouvez personnaliser des modèles pour des propriétés supplémentaires en utilisant le `FormatTemplates` collection.

### Comment résoudre les problèmes ?
Visitez le [Forum d'assistance par e-mail Aspose.](https://forum.aspose.com/c/email/12/) pour une assistance experte.