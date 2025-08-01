---
"description": "Apprenez à convertir facilement des images SVG aux formats EMF ou WMF dans des documents Word avec Aspose.Words pour .NET. Guide étape par étape avec exemples de code pour des résultats précis et compatibles."
"linktitle": "Conversion de métafichiers en EMF ou WMF"
"second_title": "API de traitement de documents Aspose.Words"
"title": "Conversion de métafichiers en EMF ou WMF"
"url": "/fr/words/net/words-processing-with-htmlsaveoptions/converting-metafiles-to-emf-or-wmf/"
"weight": 10
---

## Introduction

Gérer et convertir efficacement les formats d'image est essentiel à la création de documents Word professionnels. Dans ce guide, nous explorons l'utilisation d'Aspose.Words pour .NET pour convertir des images SVG aux formats EMF (Enhanced Metafile) ou WMF (Windows Metafile) pour une intégration fluide. Ce tutoriel fournit des instructions claires et détaillées pour aider les développeurs à mettre en œuvre facilement la conversion.

## Conditions préalables à la conversion de SVG en EMF ou WMF

Pour garantir une expérience de développement fluide, vérifiez que les conditions préalables suivantes sont remplies :

- Aspose.Words pour .NET : obtenez la dernière version à partir du [Page de publication d'Aspose](https://releases.aspose.com/words/net/).
- .NET Framework : Vérifiez l’installation de .NET Framework (ou .NET Core/5/6 selon votre environnement).
- Environnement de développement : Visual Studio est recommandé pour ses fonctionnalités robustes.
- Compétence en C# : une connaissance de base de la programmation C# est essentielle.

## Importation des espaces de noms requis

Dans votre projet, importez les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.Words :

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Étape 1 : Définir le répertoire des documents

Définissez un chemin d'accès au répertoire où seront stockés vos documents Word. Ceci est essentiel pour gérer efficacement les fichiers de sortie.

```csharp
string dataDir = @"C:\MyDocuments\";
```

Remplacer `@"C:\MyDocuments\"` avec votre chemin souhaité.

## Étape 2 : préparer la chaîne HTML contenant le SVG

Composez une chaîne HTML intégrant votre contenu SVG. Cela permet à Aspose.Words de restituer et de traiter le SVG.

```csharp
string htmlContent = 
    @"<html>
        <body>
            <svg xmlns='http://www.w3.org/2000/svg' width='300' height='100' viewBox='0 0 300 100'>
                <rect x='10' y='10' width='280' height='80' fill='blue' stroke='black' stroke-width='2'/>
                <text x='20' y='60' fill='white' font-size='20'>Aspose SVG Example</text>
            </svg>
        </body>
    </html>";
```

## Étape 3 : Configurer les options de chargement HTML

Pour garantir une gestion correcte de la conversion SVG, configurez `HtmlLoadOptions` avec `ConvertSvgToEmf`.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions
{
    ConvertSvgToEmf = true
};
```

## Étape 4 : Charger du code HTML dans un document Word

Utilisez les options de chargement configurées pour créer un `Document` objet de la chaîne HTML.

```csharp
using (MemoryStream htmlStream = new MemoryStream(Encoding.UTF8.GetBytes(htmlContent)))
{
    Document document = new Document(htmlStream, loadOptions);
}
```

## Étape 5 : Configurer les options d’enregistrement pour EMF/WMF

Personnalisez les options d'enregistrement pour définir le format de métafichier souhaité. Ici, nous choisissons `HtmlMetafileFormat.Emf`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    MetafileFormat = HtmlMetafileFormat.Emf
};
```

## Étape 6 : Enregistrer le document

Enregistrez le document en utilisant les options d’enregistrement spécifiées.

```csharp
document.Save(dataDir + "ConvertedDocument.emf", saveOptions);
```

Le fichier résultant contiendra le contenu SVG converti au format EMF.

## Conclusion

Ce tutoriel explique comment convertir des images SVG aux formats EMF ou WMF avec Aspose.Words pour .NET. En suivant ces étapes, vous pouvez améliorer la compatibilité et la fidélité visuelle de vos documents Word. Que vous automatisiez la création de documents ou prépariez des rapports de haute qualité, cette méthode garantit des résultats impeccables.

## FAQ

### Puis-je utiliser cette méthode pour traiter par lots plusieurs SVG ?
Oui, vous pouvez parcourir plusieurs fichiers HTML contenant des SVG, en appliquant le même processus dans une boucle.

### Quelle est la différence entre EMF et WMF ?
EMF est une version améliorée de WMF, offrant une meilleure prise en charge des graphiques complexes et des tailles de données plus importantes.

### Aspose.Words est-il compatible avec .NET Core ?
Oui, Aspose.Words pour .NET prend en charge .NET Core et .NET 5/6, ce qui le rend adapté aux applications multiplateformes modernes.

### Puis-je conserver le format SVG d'origine dans la sortie ?
Non, cette méthode convertit spécifiquement le format SVG en EMF/WMF. Cependant, vous pouvez conserver le format SVG d'origine en l'intégrant directement au document sans conversion.

### Où puis-je télécharger une version d'essai gratuite d'Aspose.Words ?
Vous pouvez télécharger une version d'essai gratuite à partir du [Page de publication d'Aspose](https://releases.aspose.com/).