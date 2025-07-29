---
"description": "Questa guida fornisce istruzioni dettagliate e codice di esempio per aiutarti a creare in modo efficiente immagini indicizzate 1Bpp per scopi di archiviazione, stampa o risparmio di spazio."
"linktitle": "Crea 1Bpp indicizzato"
"second_title": "API di elaborazione dei documenti Aspose.Words"
"title": "Crea 1Bpp indicizzato"
"url": "/it/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## Introduzione

Hai mai avuto bisogno di convertire un documento Word in un'immagine in bianco e nero? Che si tratti di archiviazione digitale, stampa o semplicemente di risparmiare spazio, convertire i tuoi documenti in un'immagine indicizzata a 1 bit per pagina può essere incredibilmente utile. In questa guida, illustreremo un metodo semplice per ottenere questo risultato utilizzando Aspose.Words per .NET. Iniziamo!

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere quanto segue:

- Aspose.Words per .NET: Scarica e installa la libreria da [Qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo .NET: sebbene Visual Studio sia una scelta diffusa, funzionerà qualsiasi IDE che supporti .NET.
- Conoscenza di base di C#: la familiarità con C# sarà utile, ma manterremo le cose semplici.
- Esempio di documento Word: prepara un documento per la conversione.

## Passaggio 1: importare gli spazi dei nomi necessari

Per utilizzare Aspose.Words, è necessario importare i namespace pertinenti. Questo è essenziale per accedere alle classi e ai metodi necessari per la manipolazione dei documenti.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 2: imposta la directory dei documenti

Specificare il percorso della directory in cui è archiviato il documento Word e dove si desidera salvare l'immagine convertita.

```csharp
// Percorso alla directory dei documenti
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Passaggio 3: caricare il documento Word

Carica il tuo documento Word in un `Aspose.Words.Document` oggetto. Questo oggetto consente di manipolare il documento a livello di programmazione.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 4: configurare le opzioni di salvataggio delle immagini

Quindi, imposta il `ImageSaveOptions` per definire come il documento verrà salvato come immagine. Lo configureremo per salvare in formato PNG con modalità colore indicizzato a 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // Converti solo la prima pagina
    ImageColorMode = ImageColorMode.BlackAndWhite, // Impostato su bianco e nero
    PixelFormat = ImagePixelFormat.Format1bppIndexed // Utilizzare il formato indicizzato 1Bpp
};
```

- SaveFormat.Png: specifica che il formato di output sarà PNG.
- PageSet(1): indica che verrà convertita solo la prima pagina del documento.
- ImageColorMode.BlackAndWhite: assicura che l'immagine sia in bianco e nero.
- ImagePixelFormat.Format1bppIndexed: imposta il formato pixel su 1Bpp indicizzato, ottimizzando lo spazio.

## Passaggio 5: Salvare il documento come immagine

Infine, utilizzare il `Save` metodo del `Document` oggetto per salvare l'immagine convertita.

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## Conclusione

Congratulazioni! Hai convertito con successo un documento Word in un'immagine indicizzata 1Bpp utilizzando Aspose.Words per .NET. Questo metodo non solo è efficiente, ma ti aiuta anche a creare immagini ad alto contrasto adatte a diverse applicazioni. Sentiti libero di integrare questa funzionalità nei tuoi progetti. Buona programmazione!

## Domande frequenti

### Che cos'è un'immagine indicizzata 1Bpp?
Un'immagine indicizzata a 1 Bpp (1 bit per pixel) è un formato di immagine in bianco e nero in cui ogni pixel è rappresentato da un singolo bit, 0 o 1. Questo formato è molto efficiente in termini di spazio, il che lo rende ideale per l'archiviazione.

### Posso convertire più pagine di un documento Word contemporaneamente?
Sì! Basta modificare il `PageSet` proprietà nel `ImageSaveOptions` per includere più pagine o impostarlo per convertire l'intero documento.

### Ho bisogno di una licenza per utilizzare Aspose.Words per .NET?
Sì, è necessaria una licenza per la piena funzionalità. È possibile ottenere una [licenza temporanea qui](https://purchase.aspose.com/temporary-license/).

### In quali altri formati immagine posso convertire il mio documento Word?
Aspose.Words supporta vari formati, tra cui JPEG, BMP e TIFF. Basta cambiare il `SaveFormat` nel `ImageSaveOptions` nel formato desiderato.

### Dove posso trovare ulteriore documentazione su Aspose.Words per .NET?
Per una documentazione completa, visitare il sito [Pagina di documentazione di Aspose.Words per .NET](https://reference.aspose.com/words/net/).