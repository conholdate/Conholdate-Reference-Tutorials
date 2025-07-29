---
"description": "Scopri come creare facilmente PDF interattivi da file Excel utilizzando Aspose.Cells per .NET. Questo tutorial illustra come aggiungere segnalibri con destinazioni denominate per migliorare la navigazione nei PDF."
"linktitle": "Aggiungere segnalibri con destinazioni denominate nei PDF dai file Excel"
"second_title": "API di elaborazione Excel .NET Aspose.Cells"
"title": "Aggiungere segnalibri con destinazioni denominate nei PDF dai file Excel"
"url": "/it/cells/net/mastering-rendering-and-exporting/add-bookmarks-with-named-destinations/"
"weight": 10
---

## Introduzione

Esplorare file PDF di grandi dimensioni può spesso sembrare come cercare un ago in un pagliaio, soprattutto quando sono generati da fogli di calcolo Excel estesi. I segnalibri nei documenti PDF offrono un modo semplice per passare da una sezione rilevante all'altra di un file, migliorando l'esperienza utente. Questa guida dettagliata vi guiderà attraverso il processo di aggiunta di segnalibri con destinazioni denominate a un PDF generato da un file Excel utilizzando Aspose.Cells per .NET.

## Prerequisiti per lavorare con Aspose.Cells per .NET

Prima di immergerci nel codice, è essenziale assicurarsi di avere tutti gli strumenti necessari per un'implementazione di successo. Ecco i prerequisiti:

1. Visual Studio: l'IDE consigliato per lo sviluppo .NET. Assicurati che sia installato e configurato correttamente sul tuo sistema.
2. Aspose.Cells per .NET: la libreria di base necessaria per manipolare i file Excel a livello di programmazione. È possibile [scaricalo qui](https://releases.aspose.com/cells/net/)Se sei nuovo su Aspose, puoi iniziare con [prova gratuita](https://releases.aspose.com/).
3. .NET Framework: assicurati di utilizzare una versione compatibile di .NET Framework. Aspose.Cells supporta più versioni.
4. Conoscenza di base di C#: una conoscenza di base di C# sarà utile per seguire il codice.

Una volta installati questi componenti, sei pronto per iniziare a creare documenti PDF con segnalibri!

## Impostazione del progetto

Una volta che l'ambiente di sviluppo è pronto, puoi procedere alla creazione di un nuovo progetto C# in Visual Studio. Per utilizzare le funzionalità di Aspose.Cells, dovrai importare gli spazi dei nomi richiesti.

## Importazione degli spazi dei nomi richiesti

Nella parte superiore del file C#, aggiungi quanto segue `using` istruzioni per garantire che il progetto possa accedere ad Aspose.Cells per .NET:

```csharp
using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Aspose.Cells.Rendering;
using System.Drawing.Imaging;
```

Questi namespace forniscono l'accesso alle classi essenziali che ti aiuteranno a manipolare i dati di Excel e a convertirli in un PDF.

## Passaggio 1: impostazione delle directory per i file di input e output

Il primo passo è definire le directory di input e output dei file. Questo garantisce che il file Excel di origine e il file PDF risultante siano posizionati correttamente.

```csharp
string sourceDir = "Your Document Directory";  // Percorso dei file Excel
string outputDir = "Your Document Directory"; // Percorso in cui verrà salvato il PDF di output
```

È simile all'organizzazione dello spazio di lavoro prima di iniziare un progetto.

## Passaggio 2: caricamento della cartella di lavoro di Excel

Il passo successivo è caricare il file Excel di origine. Aspose.Cells consente di caricare facilmente un file Excel in un `Workbook` oggetto, fornendo accesso a tutti i suoi fogli, celle e contenuti.

```csharp
Workbook wb = new Workbook(sourceDir + "sampleExcelFile.xlsx");
```

In questo modo si apre la cartella di lavoro e la si prepara per la manipolazione. Ora è possibile iniziare a estrarre i dati e formattarli per il PDF.

## Fase 3: Accesso al foglio di lavoro

Ora che la cartella di lavoro è caricata, è il momento di accedere al foglio di lavoro in cui si trovano le celle pertinenti per i segnalibri. In questo esempio, lavoreremo con il primo foglio di lavoro:

```csharp
Worksheet ws = wb.Worksheets[0]; // Accesso al primo foglio di lavoro
```

Questo passaggio definisce l'area di lavoro per i segnalibri. Ogni cella a cui farai riferimento per un segnalibro verrà da questo foglio di lavoro.

## Passaggio 4: creazione di segnalibri con destinazioni denominate

A questo punto, possiamo iniziare a creare segnalibri. I segnalibri sono essenzialmente link che forniscono un accesso rapido ad aree specifiche del documento. In questo esempio, creeremo un segnalibro per la cella "C5".

### Creazione di un segnalibro per una singola cella

Per creare un segnalibro, devi prima accedere alla cella a cui vuoi collegarti. Dopodiché, creerai un `PdfBookmarkEntry` e associarlo alla posizione della cellula.

```csharp
Cell cell = ws.Cells["C5"];
PdfBookmarkEntry bookmarkEntry = new PdfBookmarkEntry();
bookmarkEntry.Text = "Bookmark for C5"; // Il testo per il segnalibro
bookmarkEntry.Destination = cell;  // Collegamento del segnalibro alla cella
bookmarkEntry.DestinationName = "AsposeCells--" + cell.Name; // Nome di destinazione univoco
```

Immagina di contrassegnare un punto nel documento a cui puoi tornare con un solo clic. Puoi assegnare qualsiasi testo al segnalibro (ad esempio "Segnalibro per C5") e collegarlo a una cella specifica.

### Aggiunta di sotto-segnalibri per una navigazione migliorata

È possibile migliorare l'esperienza utente aggiungendo segnalibri secondari che si diramano dal segnalibro principale. Questi segnalibri secondari possono puntare ad aree diverse all'interno dello stesso foglio di lavoro o ad altri fogli.

```csharp
cell = ws.Cells["G56"];
PdfBookmarkEntry subbookmarkEntry1 = new PdfBookmarkEntry();
subbookmarkEntry1.Text = "Sub-Bookmark 1"; // Testo per il primo sotto-segnalibro
subbookmarkEntry1.Destination = cell;
subbookmarkEntry1.DestinationName = "AsposeCells--" + cell.Name;

cell = ws.Cells["L4"];
PdfBookmarkEntry subbookmarkEntry2 = new PdfBookmarkEntry();
subbookmarkEntry2.Text = "Sub-Bookmark 2"; // Testo per il secondo sotto-segnalibro
subbookmarkEntry2.Destination = cell;
subbookmarkEntry2.DestinationName = "AsposeCells--" + cell.Name;
```

Questi sotto-segnalibri fungono da ulteriori indicazioni per la navigazione nel documento, proprio come i capitoli di un libro.

### Raggruppamento di sotto-segnalibri sotto un segnalibro principale

Per creare una struttura gerarchica, è possibile aggiungere questi sotto-segnalibri sotto il segnalibro principale. In questo modo, gli utenti potranno navigare più facilmente tra le diverse sezioni.

```csharp
ArrayList list = new ArrayList();
list.Add(subbookmarkEntry1);
list.Add(subbookmarkEntry2);
bookmarkEntry.SubEntry = list; // Aggiungere sotto-segnalibri al segnalibro principale
```

In questo modo si crea una struttura ad albero in cui ogni segnalibro può avere più sotto-segnalibri.

## Passaggio 5: Salvataggio del PDF con i segnalibri

### Impostazione delle opzioni di salvataggio PDF

Prima di salvare il documento come PDF, dobbiamo specificare le opzioni di salvataggio e assicurarci che i segnalibri siano inclusi. Useremo `PdfSaveOptions` per questo scopo.

```csharp
PdfSaveOptions opts = new PdfSaveOptions();
opts.Bookmark = bookmarkEntry;  // Assegnazione dei segnalibri al PDF
```

In questo modo Aspose.Cells genera un PDF che include i segnalibri appena creati.

### Salvataggio del documento

Ora che i segnalibri sono impostati, possiamo salvare la cartella di lavoro come PDF.

```csharp
wb.Save(outputDir + "outputWithBookmarks.pdf", opts);
```

In questo modo viene generato il PDF finale con segnalibri cliccabili, consentendo agli utenti di passare rapidamente a sezioni specifiche del documento.

## Conclusione

Seguendo questi semplici passaggi, hai creato con successo un PDF con segnalibri e destinazioni denominate da un file Excel utilizzando Aspose.Cells per .NET. La possibilità di aggiungere segnalibri non solo migliora l'esperienza utente, ma rende anche la navigazione all'interno di documenti di grandi dimensioni molto più efficiente. Che tu stia lavorando a un report, una guida o una presentazione, aggiungere segnalibri alle sezioni chiave aiuterà i tuoi lettori a ottenere il massimo dal tuo documento.

## Domande frequenti

### Che cos'è Aspose.Cells per .NET?
Aspose.Cells per .NET è una potente API per lavorare con i file Excel, che consente di creare, modificare e convertire documenti Excel a livello di codice. Con questo strumento è possibile manipolare facilmente dati, grafici e formattazione.

### Come posso ottenere una prova gratuita di Aspose.Cells per .NET?
È possibile scaricare una versione di prova gratuita di Aspose.Cells per .NET da [Qui](https://releases.aspose.com/).

### Con quali formati di file può funzionare Aspose.Cells?
Aspose.Cells supporta un'ampia gamma di formati di file, tra cui XLSX, XLS, CSV, PDF e molti altri.

### Posso automatizzare il processo di creazione dei segnalibri in PDF?
Sì! Il processo può essere completamente automatizzato integrando Aspose.Cells nelle tue applicazioni, consentendoti di generare dinamicamente PDF basati su Excel con segnalibri come parte del tuo flusso di lavoro.

### Dove posso ottenere supporto per Aspose.Cells per .NET?
Puoi visitare il [Forum di Aspose](https://forum.aspose.com/c/cells/9) per porre domande o segnalare problemi.