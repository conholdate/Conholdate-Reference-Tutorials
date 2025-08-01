---
"description": "Découvrez comment ajouter des lignes de signature à vos documents Word par programmation avec Aspose.Words pour .NET. Ce guide complet couvre tout, de la configuration de votre environnement de développement à l'insertion de lignes de signature et à la signature sécurisée de documents."
"linktitle": "Créer une nouvelle ligne de signature numérique et définir l'ID du fournisseur"
"second_title": "API de traitement de documents Aspose.Words"
"title": "Créer une nouvelle ligne de signature numérique et définir l'ID du fournisseur"
"url": "/fr/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Introduction

Bonjour à tous les passionnés de technologie ! Avez-vous déjà rêvé d'automatiser l'inclusion de lignes de signature dans vos documents Word ? Aujourd'hui, nous vous expliquons comment y parvenir avec Aspose.Words pour .NET. Ce guide étape par étape vous guidera dans la création d'une ligne de signature et la définition de l'ID du fournisseur, rendant ainsi le traitement de vos documents plus efficace et simplifié.

## Prérequis

Avant de commencer, assurons-nous que tout est configuré :

1. Aspose.Words pour .NET : si vous ne l'avez pas encore installé, téléchargez-le [ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : utilisez Visual Studio ou toute configuration de développement C#.
3. .NET Framework : assurez-vous que .NET Framework est installé sur votre machine.
4. Certificat PFX : vous aurez besoin d'un certificat PFX pour signer des documents, qui peut être obtenu auprès d'une autorité de certification de confiance.

## Importation des espaces de noms nécessaires

Pour commencer, importez les espaces de noms requis dans votre projet C# :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Maintenant, plongeons dans les détails de la création d’une nouvelle ligne de signature et de la définition de l’ID du fournisseur.

## Étape 1 : Créer un nouveau document

Tout d’abord, nous devons créer un nouveau document Word, qui servira de canevas pour notre ligne de signature :

```csharp
// Spécifiez le chemin d’accès à votre répertoire de documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ici, nous initialisons un nouveau `Document` et un `DocumentBuilder`, ce qui nous permet d'ajouter des éléments facilement.

## Étape 2 : Définir les options de ligne de signature

Ensuite, nous définirons les options de notre ligne de signature, y compris le nom du signataire, son titre, son adresse e-mail et d'autres détails pertinents :

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Ces options permettent de personnaliser la ligne de signature, la rendant claire et professionnelle.

## Étape 3 : Insérer la ligne de signature

Avec nos options prêtes, nous pouvons maintenant insérer la ligne de signature dans le document :

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Le `InsertSignatureLine` La méthode ajoute la ligne de signature et nous lui attribuons un identifiant de fournisseur unique.

## Étape 4 : Enregistrer le document

Après avoir inséré la ligne de signature, enregistrons le document :

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Cela enregistre votre document avec la ligne de signature nouvellement ajoutée.

## Étape 5 : Configurer les options de signature

Nous allons maintenant configurer les options de signature, notamment l'ID de la ligne de signature, l'ID du fournisseur, les commentaires et l'heure de signature :

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Ces paramètres garantissent que le document est signé avec les détails corrects.

## Étape 6 : Créer un titulaire de certificat

Pour signer le document, nous devons créer un titulaire de certificat à l'aide du certificat PFX :

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Remplacer `"morzal.pfx"` avec le nom réel de votre fichier de certificat et `"aw"` avec votre mot de passe de certificat.

## Étape 7 : Signer le document

Enfin, nous signerons le document à l’aide de l’utilitaire de signature numérique :

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Ce processus signe le document et l’enregistre en tant que nouveau fichier.

## Conclusion

Félicitations ! Vous avez créé une ligne de signature et défini l'identifiant du fournisseur dans un document Word avec Aspose.Words pour .NET. Cette puissante bibliothèque simplifie le traitement des documents et optimise votre flux de travail. Essayez-la et découvrez comment elle peut améliorer vos projets !

## FAQ

### Puis-je personnaliser l’apparence de la ligne de signature ?
Absolument ! Vous pouvez ajuster différentes options dans le `SignatureLineOptions` pour s'adapter à votre style et à vos exigences.

### Que faire si je n’ai pas de certificat PFX ?
Vous devrez en obtenir un auprès d’une autorité de certification de confiance, car il est essentiel pour signer numériquement des documents.

### Puis-je ajouter plusieurs lignes de signature à un document ?
Oui, vous pouvez ajouter plusieurs lignes de signature en répétant le processus d’insertion avec différentes options.

### Aspose.Words pour .NET est-il compatible avec .NET Core ?
Oui, Aspose.Words pour .NET prend en charge .NET Core, ce qui le rend polyvalent pour divers environnements de développement.

### Dans quelle mesure les signatures numériques sont-elles sécurisées ?
Les signatures numériques créées avec Aspose.Words sont hautement sécurisées, à condition d'utiliser un certificat valide et fiable.