---
"description": "Scopri come convertire facilmente ogni pagina di un documento Word in singole immagini PNG utilizzando Aspose.Words per .NET. Questa guida fornisce istruzioni dettagliate, inclusi esempi di codice."
"linktitle": "Richiamo di salvataggio della pagina nei documenti Word"
"second_title": "API di elaborazione dei documenti Aspose.Words"
"title": "Richiamo di salvataggio della pagina nei documenti Word"
"url": "/it/words/net/guide-to-image-save-options/page-saving-callback-word-document/"
"weight": 10
---

## Introduzione

Hai mai avuto bisogno di convertire ogni pagina di un documento Word in singole immagini? Che tu voglia creare miniature per un'anteprima o scomporre un lungo report in elementi visivi comprensibili, Aspose.Words per .NET rende questo compito semplice ed efficiente. In questa guida, ti guideremo attraverso il processo di configurazione di una callback di salvataggio delle pagine per salvare ogni pagina del tuo documento come immagine PNG. Iniziamo!

## Prerequisiti

Prima di immergerti, assicurati di avere quanto segue:

1. Aspose.Words per .NET: scaricalo e installalo da [Qui](https://releases.aspose.com/words/net/).
2. Visual Studio: qualsiasi versione funzionerà, ma per questa guida utilizzeremo Visual Studio 2019.
3. Conoscenza di base di C#: la familiarità con C# ti aiuterà a seguire il corso senza problemi.

## Passaggio 1: importare gli spazi dei nomi necessari

Per prima cosa, dobbiamo importare gli spazi dei nomi richiesti. Questo ci consente di accedere alle classi e ai metodi necessari senza dover digitare ogni volta l'intero spazio dei nomi.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 2: definire la directory dei documenti

Quindi, imposta il percorso della directory del documento. Qui si trova il documento Word di input e dove verranno salvate le immagini di output.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: carica il documento

Ora carichiamo il documento che desideri elaborare. Assicurati che il documento, denominato "Rendering.docx", si trovi nella directory specificata.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 4: configurare le opzioni di salvataggio delle immagini

Imposteremo le opzioni per il salvataggio delle immagini, specificando che vogliamo salvare le pagine come file PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

Qui, `PageSet` definisce l'intervallo di pagine da salvare e `PageSavingCallback` punta alla nostra classe di callback personalizzata.

## Passaggio 5: implementare il callback di salvataggio della pagina

Ora dobbiamo implementare la classe di callback che gestisce il modo in cui ogni pagina viene salvata.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

Questa classe implementa il `IPageSavingCallback` interfaccia. Nell' `PageSaving` metodo, specifichiamo il modello di denominazione per ogni pagina salvata.

## Passaggio 6: Salvare il documento come immagini

Infine salviamo il documento utilizzando le opzioni configurate.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Conclusione

Congratulazioni! Hai configurato correttamente una callback per il salvataggio delle pagine, che salva ogni pagina di un documento Word come immagine PNG separata utilizzando Aspose.Words per .NET. Questa tecnica è incredibilmente utile per diverse applicazioni, dalla creazione di anteprime di pagina alla generazione di singole immagini di pagina per i report.

## Domande frequenti

### Posso salvare le pagine in formati diversi da PNG?
Sì! Puoi salvare le pagine in formati come JPEG, BMP e TIFF modificando il `SaveFormat` In `ImageSaveOptions`.

### Come posso salvare solo pagine specifiche?
Per salvare pagine specifiche, regolare il `PageSet` parametro in `ImageSaveOptions` per includere solo le pagine desiderate.

### È possibile personalizzare la qualità dell'immagine?
Assolutamente! Puoi controllare la qualità dell'immagine in uscita impostando proprietà come `ImageSaveOptions.JpegQuality`.

### Come posso gestire in modo efficiente documenti di grandi dimensioni?
Per i documenti di grandi dimensioni, valutare l'elaborazione delle pagine in batch per gestire in modo efficace l'utilizzo della memoria.

### Dove posso trovare maggiori informazioni su Aspose.Words per .NET?
Per guide ed esempi completi, consulta il [Documentazione di Aspose.Words](https://reference.aspose.com/words/net/).