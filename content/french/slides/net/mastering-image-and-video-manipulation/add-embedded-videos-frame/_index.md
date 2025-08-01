---
"description": "Exploitez le potentiel de vos présentations en apprenant à intégrer des vidéos avec Aspose.Slides pour .NET. Ce tutoriel complet vous guide pas à pas dans l'intégration d'éléments multimédias."
"linktitle": "Ajouter un cadre vidéo intégré dans les présentations .NET"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Ajouter un cadre vidéo intégré dans les présentations .NET"
"url": "/fr/slides/net/mastering-image-and-video-manipulation/add-embedded-videos-frame/"
"weight": 19
---

## Introduction

Dans le monde actuel des présentations, où tout se déroule à un rythme effréné, l'intégration d'éléments multimédias peut considérablement améliorer l'engagement et la fidélisation de l'audience. Aspose.Slides pour .NET offre une solution robuste pour intégrer des images vidéo à vos diapositives. Ce tutoriel vous guidera pas à pas, garantissant une expérience fluide du début à la fin.

## Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Bibliothèque Aspose.Slides pour .NET : téléchargez et installez la bibliothèque à partir du [page de sortie](https://releases.aspose.com/slides/net/).
- Contenu multimédia : un fichier vidéo (par exemple, « Wildlife.mp4 ») que vous souhaitez intégrer dans votre présentation.

## Importer les espaces de noms nécessaires

Commencez par importer les espaces de noms requis dans votre projet .NET :

```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Étape 1 : Configurez vos répertoires

Assurez-vous que votre projet inclut les répertoires nécessaires pour les fichiers de documents et de médias :

```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");

// Créer un répertoire s'il n'existe pas
if (!Directory.Exists(dataDir))
    Directory.CreateDirectory(dataDir);
```

## Étape 2 : instancier la classe de présentation

Créer une instance de `Presentation` classe pour représenter votre fichier PPTX :

```csharp
using (Presentation pres = new Presentation())
{
    // Obtenez la première diapositive
    ISlide sld = pres.Slides[0];
```

## Étape 3 : Intégrer la vidéo

Intégrez la vidéo dans votre présentation à l’aide du code suivant :

```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(Path.Combine(videoDir, "Wildlife.mp4"), FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```

## Étape 4 : ajouter une image vidéo

Ensuite, ajoutez une image vidéo à la diapositive :

```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```

## Étape 5 : Configurer les propriétés vidéo

Définissez les propriétés de la vidéo, y compris le mode de lecture et le volume :

```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto; // Lire automatiquement la vidéo
vf.Volume = AudioVolumeMode.Loud; // Régler le niveau de volume
```

## Étape 6 : Enregistrez votre présentation

Enfin, enregistrez le fichier PPTX modifié sur le disque :

```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```

Vous pouvez répéter ces étapes pour chaque vidéo que vous souhaitez intégrer dans votre présentation.

## Conclusion

Félicitations ! Vous avez intégré une image vidéo à votre présentation avec Aspose.Slides pour .NET. Cette fonctionnalité dynamique peut propulser vos présentations au niveau supérieur et captiver votre public grâce à des éléments multimédias parfaitement intégrés.

## FAQ

### Puis-je intégrer des vidéos dans n’importe quelle diapositive de la présentation ?

Oui, vous pouvez sélectionner n'importe quelle diapositive en ajustant l'index dans `pres.Slides[index]`.

### Quels formats vidéo sont pris en charge ?

Aspose.Slides prend en charge divers formats vidéo, notamment MP4, AVI et WMV.

### Puis-je personnaliser la taille et la position de l'image vidéo ?

Absolument ! Vous pouvez modifier les paramètres dans `AddVideoFrame(x, y, width, height, video)` pour répondre à vos besoins.

### Y a-t-il une limite au nombre de vidéos que je peux intégrer ?

La limite des vidéos intégrées dépend généralement de la capacité de votre logiciel de présentation.

### Où puis-je demander de l’aide supplémentaire ou partager mon expérience ?

N'hésitez pas à visiter le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.