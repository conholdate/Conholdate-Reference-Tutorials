---
"description": "Scopri come modificare facilmente l'orientamento della pagina dei file PDF utilizzando Aspose.PDF per .NET. Questa guida dettagliata fornisce istruzioni chiare su come caricare, ruotare e salvare i tuoi documenti."
"linktitle": "Cambia l'orientamento della pagina PDF"
"second_title": "Riferimento API Aspose.PDF per .NET"
"title": "Cambia l'orientamento della pagina PDF"
"url": "/it/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Introduzione

Ti è mai capitato di imbatterti in un file PDF con l'orientamento delle pagine completamente sbagliato? Che si tratti di un documento scansionato in modo errato o di uno che necessita semplicemente di un layout diverso, modificare l'orientamento può fare la differenza. Fortunatamente, Aspose.PDF per .NET offre un modo potente e intuitivo per manipolare i file PDF, inclusa la modifica dell'orientamento delle pagine. In questa guida, ti guideremo passo dopo passo attraverso il processo, sia che tu voglia passare dall'orientamento verticale a quello orizzontale o viceversa.

## Prerequisiti

Prima di entrare nei dettagli, assicurati di avere a disposizione quanto segue:

- Aspose.PDF per .NET: assicurati di aver installato la libreria Aspose.PDF. Se non l'hai ancora fatto, puoi [scaricalo qui](https://releases.aspose.com/pdf/net/).
- Un ambiente di sviluppo .NET: puoi utilizzare Visual Studio, JetBrains Rider o qualsiasi altro IDE che preferisci per lo sviluppo .NET.
- Conoscenza di base di C#: la familiarità con C# ti aiuterà a seguire più facilmente.
- Un file PDF: tieni pronto un file PDF di esempio da testare. Puoi crearne uno o scaricarne uno online.

Se stai appena iniziando, prova Aspose.PDF con un [licenza temporanea gratuita](https://purchase.aspose.com/temporary-license/) prima di decidere di [acquista la versione completa](https://purchase.aspose.com/buy).

## Importa spazi dei nomi

Per manipolare le pagine PDF, devi prima importare gli spazi dei nomi necessari nel tuo progetto C#. Aggiungi le seguenti righe all'inizio del file di codice:

```csharp
using System.IO;
using Aspose.Pdf;
```

Ora che abbiamo impostato tutto, cominciamo!

## Passaggio 1: caricare il documento PDF

Il primo passo è caricare il file PDF che si desidera modificare. Utilizzare il `Document` classe dallo spazio dei nomi Aspose.PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Assicurati di sostituire `"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del tuo file PDF.

## Passaggio 2: scorrere ogni pagina

Successivamente, scorreremo ogni pagina del documento PDF. Questo ci permetterà di applicare la modifica di orientamento a tutte le pagine:

```csharp
foreach (Page page in doc.Pages)
{
    // Manipola ogni pagina
}
```

## Passaggio 3: accedi al MediaBox della pagina

Ogni pagina PDF ha un `MediaBox` che ne definisce i confini. Dobbiamo accedervi per verificare l'orientamento corrente e apportare modifiche:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

IL `MediaBox` fornisce le dimensioni della pagina, tra cui larghezza e altezza.

## Passaggio 4: scambia larghezza e altezza

Per modificare l'orientamento della pagina, invertiamo i valori di larghezza e altezza. Questa modifica modificherà le dimensioni della pagina:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Qui calcoliamo le nuove dimensioni e riposizioniamo l'angolo inferiore sinistro (`LLY`) di conseguenza.

## Passaggio 5: Aggiorna MediaBox e CropBox

Ora che abbiamo le nuove dimensioni, applicheremo queste modifiche al `MediaBox` E `CropBox` per garantire che la pagina venga visualizzata correttamente:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Passaggio 6: ruota la pagina

Per finalizzare la modifica dell'orientamento, ruoteremo la pagina. Con Aspose.PDF è semplicissimo:

```csharp
page.Rotate = Rotation.on90; // Ruota di 90 gradi
```

Questa linea capovolge effettivamente la pagina nell'orientamento desiderato.

## Passaggio 7: Salva il PDF di output

Dopo aver modificato l'orientamento di tutte le pagine, salva il documento aggiornato in un nuovo file:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Assicurati di fornire un nuovo nome file per evitare di sovrascrivere il documento originale.

## Conclusione

Ed ecco fatto! Cambiare l'orientamento della pagina di un file PDF utilizzando Aspose.PDF per .NET è un processo semplice. Caricando il documento, scorrendo le pagine, aggiornando MediaBox e salvando il file, è possibile adattare facilmente il layout alle proprie esigenze. Che si tratti di correggere un documento scansionato male o di formattare le pagine per una presentazione, questa guida dovrebbe aiutarvi a svolgere il lavoro in modo efficiente.

## Domande frequenti

### Posso ruotare pagine specifiche anziché tutte le pagine del PDF?  
Sì, puoi modificare il ciclo in modo che prenda di mira pagine specifiche in base al loro indice, anziché scorrere tutte le pagine.

### Che cosa è il `MediaBox`?  
IL `MediaBox` definisce le dimensioni e la forma della pagina in un file PDF, determinando dove verrà posizionato il contenuto.

### Aspose.PDF per .NET funziona con altri formati di file?  
Sì, Aspose.PDF può gestire vari formati di file, tra cui HTML, XML, XPS e altri.

### Esiste una versione gratuita di Aspose.PDF per .NET?  
Sì, puoi iniziare con un [prova gratuita](https://releases.aspose.com/) o richiedi un [licenza temporanea](https://purchase.aspose.com/temporary-license/).

### Posso annullare le modifiche una volta salvate?  
Una volta salvato il documento, le modifiche sono permanenti. Si consiglia di lavorare su una copia o di conservare un backup del file originale.