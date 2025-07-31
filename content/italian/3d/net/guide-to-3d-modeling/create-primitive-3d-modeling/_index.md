---
"description": "Scopri come creare e personalizzare modelli 3D primitivi, tra cui scatole e cilindri, e salvarli senza sforzo in formato FBX."
"linktitle": "Crea modelli 3D primitivi"
"second_title": "API .NET di Aspose.3D"
"title": "Crea modelli 3D primitivi"
"url": "/it/3d/net/guide-to-3d-modeling/create-primitive-3d-modeling/"
"weight": 10
---

## Introduzione

Benvenuti nel mondo immersivo della modellazione 3D con Aspose.3D per .NET! In questo tutorial completo, vi guideremo passo dopo passo attraverso il processo di creazione di modelli 3D primitivi. Che siate sviluppatori esperti o principianti desiderosi di imparare, questa guida vi aiuterà a creare elementi 3D visivamente sorprendenti per i vostri progetti.

## Prerequisiti

Prima di immergerti nella modellazione 3D, assicurati di disporre dei seguenti prerequisiti:

- Aspose.3D per .NET: Scarica e installa la libreria Aspose.3D per .NET da [pagina di download](https://releases.aspose.com/3d/net/).
  
- Ambiente di sviluppo .NET: configura un ambiente compatibile con Aspose.3D, come Visual Studio.

Ora che tutto è pronto, iniziamo la nostra avventura nella modellazione 3D!

## Importazione degli spazi dei nomi richiesti

Per iniziare, importare gli spazi dei nomi necessari per accedere alle funzionalità di Aspose.3D:

```csharp
using System;
using System.IO;
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
```

Questi namespace ti forniranno gli strumenti necessari per manipolare modelli 3D e salvare le tue creazioni.

## Passaggio 1: inizializzare un oggetto scena

Crea un nuovo oggetto scena che funga da tela per i tuoi modelli 3D:

```csharp
// Inizializza un oggetto Scena
Scene scene = new Scene();
```

Questa scena conterrà le forme primitive che stai per creare.

## Passaggio 2: creare un modello di scatola

Ora aggiungiamo un modello di scatola alla scena:

```csharp
// Crea un modello Box
scene.RootNode.CreateChildNode("box", new Box());
```

Puoi personalizzare le dimensioni e le proprietà della scatola in base alla tua visione creativa.

## Passaggio 3: creare un modello cilindrico

Ora, arricchisci la tua scena aggiungendo un cilindro:

```csharp
// Crea un modello Cilindro
scene.RootNode.CreateChildNode("cylinder", new Cylinder());
```

Proprio come per la scatola, sentiti libero di regolare i parametri del cilindro per ottenere l'aspetto desiderato.

## Passaggio 4: Salva la scena in formato FBX

Per conservare il tuo modello 3D, salvalo nel formato FBX:

```csharp
// Salva il disegno nel formato FBX
var output = Path.Combine("Your Output Directory", "test.fbx");
scene.Save(output, FileFormat.FBX7500ASCII);
```

Assicurati di scegliere una directory di output e un nome di file appropriati per il tuo modello.

## Passaggio 5: visualizzare un messaggio di successo

Infine, celebra il tuo successo mostrando un messaggio:

```csharp
// Visualizza messaggio di successo
Console.WriteLine($"\nBuilding a scene from primitive 3D models was successful.\nFile saved at {output}");
```

La tua scena 3D composta da modelli primitivi è ora completa e salvata!

## Conclusione

Congratulazioni per aver creato splendidi modelli 3D utilizzando Aspose.3D per .NET! Questo tutorial ha trattato le basi della modellazione primitiva, ma le possibilità sono infinite. Scopri di più sulle funzionalità e le tecniche avanzate in [documentazione](https://reference.aspose.com/3d/net/).

## Domande frequenti

### Posso utilizzare Aspose.3D per .NET con linguaggi di programmazione diversi da .NET?

Aspose.3D supporta principalmente .NET, ma sono disponibili versioni per Java e altre piattaforme.

### È disponibile una prova gratuita?

Sì, puoi provare le capacità di Aspose.3D con un [prova gratuita](https://releases.aspose.com/).

### Dove posso trovare supporto per Aspose.3D per .NET?

Per il supporto della comunità, visita il [Forum Aspose.3D](https://forum.aspose.com/c/3d/18).

### Come posso ottenere una licenza temporanea?

Puoi richiedere una licenza temporanea [Qui](https://purchase.conholdate.com/temporary-license/).

### Sono disponibili ulteriori tutorial?

Sì! Esplora altri tutorial ed esempi in [documentazione](https://reference.aspose.com/3d/net/).