---
"description": "Scopri come estrarre facilmente file video incorporati da presentazioni PowerPoint utilizzando Aspose.Slides per .NET. Questa guida completa e dettagliata copre ogni aspetto, dalla configurazione dell'ambiente al salvataggio dei video estratti."
"linktitle": "Estrarre video dalle diapositive di PowerPoint"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Estrai video dalle diapositive di PowerPoint con Aspose.Slides"
"url": "/it/slides/net/extract-audio-and-video/extract-videos-from-powerpoint-slides/"
"weight": 14
---

## Introduzione

Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di interagire con le presentazioni di PowerPoint a livello di codice. In questa guida, vi guideremo attraverso il processo di estrazione di video incorporati nelle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. 

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Slides per .NET: ottenere e installare la libreria da [Sito web Aspose](https://purchase.aspose.com/buy).
- Presentazione PowerPoint: preparare un file PowerPoint (ad esempio, `Video.pptx`) con il video che desideri estrarre.

## Spazi dei nomi necessari

Per utilizzare Aspose.Slides per .NET, è necessario importare gli spazi dei nomi appropriati. Includi quanto segue nel codice:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

## Passaggio 1: specificare la directory dei documenti

Per prima cosa, definisci il percorso della tua presentazione PowerPoint:

```csharp
string dataDir = "Your Document Directory";
```

Sostituire `"Your Document Directory"` con il percorso effettivo della directory contenente il file PowerPoint.

## Passaggio 2: caricare la presentazione

Caricare la presentazione di PowerPoint in un `Presentation` oggetto:

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Questo inizializza il `Presentation` oggetto con il file PowerPoint specificato.

## Passaggio 3: scorrere diapositive e forme

Quindi, scorrere ogni diapositiva della presentazione e controllare i fotogrammi video:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in slide.Shapes)
    {
        if (shape is VideoFrame videoFrame)
        {
            // Procedi all'estrazione del video
        }
    }
}
```

## Passaggio 4: estrai i dati video

Una volta trovato un fotogramma video, estraine le proprietà e i dati binari:

```csharp
IVideoFrame vf = (IVideoFrame)shape;  // Memorizza la forma come fotogramma video
string contentType = vf.EmbeddedVideo.ContentType;
Byte[] buffer = vf.EmbeddedVideo.BinaryData;

// Ottieni l'estensione del file
string fileExtension = contentType.Substring(contentType.LastIndexOf('/') + 1);
```

## Passaggio 5: salva il video

Infine, scrivi i dati video estratti in un file:

```csharp
using (FileStream stream = new FileStream(dataDir + "ExtractedVideo." + fileExtension, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Questo codice crea un nuovo file nella directory specificata e vi scrive i dati video.

## Conclusione

Con Aspose.Slides per .NET, estrarre video dalle diapositive di PowerPoint è un processo semplice. Seguendo questa guida, puoi gestire facilmente i contenuti multimediali all'interno delle tue applicazioni .NET, arricchendo l'esperienza utente e le funzionalità.

## Domande frequenti

### Che cos'è Aspose.Slides per .NET?
Aspose.Slides per .NET è una libreria progettata per funzionare con le presentazioni PowerPoint, consentendo agli utenti di creare, modificare e manipolare i file di presentazione a livello di programmazione.

### Dove posso trovare la documentazione per Aspose.Slides per .NET?
Puoi accedere alla documentazione completa [Qui](https://reference.aspose.com/slides/net/).

### Aspose.Slides per .NET è disponibile per una prova gratuita?
Sì, puoi scaricare una versione di prova gratuita da [questo collegamento](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Slides per .NET?
Le richieste di licenze temporanee possono essere effettuate [Qui](https://purchase.aspose.com/temporary-license/).

### Dove posso ottenere supporto per Aspose.Slides per .NET?
Il supporto è disponibile tramite [Forum Aspose.Slides](https://forum.aspose.com/).