---
"description": "Sfrutta appieno il potenziale delle tue conversioni da Excel a PDF con Aspose.Cells per .NET. In questa guida completa, scopri come gestire risorse esterne, come le immagini, assicurandoti che i tuoi PDF rispecchino esattamente i tuoi requisiti di formattazione."
"linktitle": "Controlla le risorse esterne con Aspose.Cells per .NET"
"second_title": "API di elaborazione Excel .NET Aspose.Cells"
"title": "Controlla le risorse esterne con Aspose.Cells per .NET"
"url": "/it/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## Introduzione

Nel panorama digitale odierno, convertire fogli di calcolo Excel in documenti PDF è un'attività comune ed essenziale. Che si tratti di preparare report, dati finanziari o materiali di presentazione, è fondamentale assicurarsi che i PDF riflettano il formato desiderato. Aspose.Cells per .NET offre una potente libreria che consente di controllare questo processo di conversione in dettaglio, soprattutto quando si gestiscono risorse esterne come le immagini. In questa guida, esploreremo come gestire efficacemente le risorse esterne durante il processo di conversione da Excel a PDF utilizzando Aspose.Cells. Iniziamo!

## Prerequisiti

Prima di iniziare, assicurati di avere a portata di mano quanto segue:

1. Visual Studio o qualsiasi IDE compatibile con .NET: questo sarà il tuo ambiente di sviluppo.
2. Aspose.Cells per .NET: se non lo hai ancora installato, visita il [Download di Aspose](https://releases.aspose.com/cells/net/) pagina per ottenere l'ultima versione.
3. Conoscenza di base di C#: la familiarità con C# sarà utile. Se hai bisogno di chiarimenti su qualsiasi concetto, sentiti libero di consultarli.
4. File Excel di esempio: preparare un file Excel, ad esempio "samplePdfSaveOptions_StreamProvider.xlsx", che contenga le risorse esterne che si desidera convertire.
5. File immagine per il test: utilizzare un file immagine come "newPdfSaveOptions_StreamProvider.png" come risorsa esterna durante la conversione.

## Importa i pacchetti necessari

Per iniziare, dovrai importare gli spazi dei nomi richiesti dalla libreria Aspose.Cells. Aggiungi le seguenti direttive using all'inizio del tuo file C#:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

Questi namespace forniscono le classi e i metodi essenziali per le tue attività.

## Passaggio 1: creare una classe di provider di streaming

Per prima cosa, crea una classe provider di streaming che implementi `IStreamProvider` interfaccia. Questa classe ti consentirà di controllare come vengono caricate le risorse esterne.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // Carica l'immagine in un flusso di memoria
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: questo metodo viene chiamato quando il flusso viene chiuso e attualmente registra un messaggio di debug.
- InitStream: questo metodo legge il file immagine esterno come un array di byte, lo converte in un flusso di memoria e lo assegna al `options.Stream` proprietà.

## Passaggio 2: impostare le directory di origine e di output

Successivamente, definisci le directory per il file Excel e il PDF di output.

```csharp
// Directory di origine
string sourceDir = "Your Document Directory";
// Directory di output
string outputDir = "Your Document Directory";
```

Sostituire `"Your Document Directory"` con il percorso effettivo sul tuo sistema in cui si trovano i tuoi file.

## Passaggio 3: carica il file Excel

Ora carica il file Excel da cui vuoi creare il PDF.

```csharp
// Carica il file Excel di origine contenente immagini esterne
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

IL `Workbook` La classe di Aspose.Cells rappresenta il file Excel, che può includere varie risorse esterne come le immagini.

## Passaggio 4: imposta le opzioni di salvataggio PDF

Prima di salvare la cartella di lavoro in formato PDF, specificare le opzioni di salvataggio desiderate.

```csharp
// Specificare le opzioni di salvataggio PDF - Fornitore di streaming
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // Salva ogni foglio su una nuova pagina
};
```

Questo crea un'istanza di `PdfSaveOptions`, consentendo di personalizzare il formato PDF. Il `OnePagePerSheet` L'opzione garantisce che ogni foglio Excel venga visualizzato su una pagina separata nel PDF finale.

## Passaggio 5: Assegna il tuo fornitore di streaming

Connetti il tuo `Workbook` esempio con il `MyStreamProvider` classe creata in precedenza.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

Questa riga garantisce che ogni volta che durante la conversione vengono incontrate risorse esterne, il tuo provider personalizzato le gestirà di conseguenza.

## Passaggio 6: Salvare la cartella di lavoro come PDF

Ora salva la tua cartella di lavoro Excel come PDF.

```csharp
// Salva la cartella di lavoro in PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

Chiamando il `Save` sull'oggetto cartella di lavoro e passando la directory di output insieme alle opzioni PDF, si converte il file Excel in un PDF formattato correttamente.

## Passaggio 7: Confermare l'esecuzione corretta

Infine, è buona norma confermare che il processo sia stato completato correttamente.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

Questo messaggio ti informerà sullo stato della tua operazione, fornendoti un feedback utile.

## Conclusione

Ora hai imparato a controllare le risorse esterne durante la conversione da Excel a PDF utilizzando Aspose.Cells! Seguendo questi passaggi, puoi garantire che i tuoi documenti includano correttamente immagini e altri elementi esterni, ottenendo ogni volta un prodotto finale impeccabile.

## Domande frequenti

### Che cos'è Aspose.Cells?
Aspose.Cells è una potente libreria per sviluppatori .NET che consente la creazione, la manipolazione, la conversione e il rendering di file Excel in vari formati.

### Come faccio a scaricare Aspose.Cells?
Puoi scaricare l'ultima versione da [Link per il download](https://releases.aspose.com/cells/net/).

### Posso provare Aspose.Cells gratuitamente?
Sì! Puoi accedere a una prova gratuita visitando il [Pagina di prova gratuita](https://releases.aspose.com/).

### Dove posso trovare supporto per Aspose.Cells?
Per domande relative al supporto, visitare il [Forum di supporto Aspose](https://forum.aspose.com/c/cells/9).

### Come posso ottenere una licenza temporanea per Aspose.Cells?
Puoi richiedere una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/).