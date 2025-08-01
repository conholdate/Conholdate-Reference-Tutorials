---
"description": "Scopri come convertire in modo efficiente i layout CAD in vari formati di immagini raster utilizzando Aspose.CAD per .NET. Questa guida completa ti guiderà attraverso il processo con un codice chiaro."
"linktitle": "Conversione da esportazione CAD a immagine raster"
"second_title": "Aspose.CAD .NET - Formato file CAD e BIM"
"title": "Esportazione di immagini CAD in conversione di immagini raster con Aspose.CAD per .NET"
"url": "/it/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## Introduzione

Vuoi convertire layout CAD in formati di immagini raster senza sforzo utilizzando Aspose.CAD per .NET? Questa guida passo passo è progettata per aiutarti a orientarti nel processo, completa di frammenti di codice concisi per un'esperienza fluida. Che tu sia uno sviluppatore esperto o alle prime armi, questo tutorial offre spunti preziosi per tutti i livelli di competenza.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Libreria Aspose.CAD per .NET: scaricare e installare la libreria da [Sito web Aspose.CAD](https://releases.aspose.com/cad/net/).
- File di disegno CAD: avere il file di disegno CAD (ad esempio, `conic_pyramid.dxf`) pronto per la conversione.

## Importa gli spazi dei nomi richiesti

Nel tuo progetto .NET, dovrai importare gli spazi dei nomi necessari per utilizzare le funzioni di Aspose.CAD. Aggiungi quanto segue all'inizio del codice:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Passaggio 1: carica il tuo disegno CAD

Per prima cosa, specifica la directory e carica il tuo file CAD in un'istanza Image:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// Carica il disegno CAD
using (var image = Image.Load(sourceFilePath))
{
    // Procedi ai passaggi successivi
}
```

## Passaggio 2: creare opzioni di rasterizzazione

Successivamente, imposta le opzioni di rasterizzazione, definendo le dimensioni desiderate per l'immagine di output:

```csharp
// Inizializza CadRasterizationOptions
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## Passaggio 3: specificare i livelli per la conversione

Se vuoi convertire livelli specifici, aggiungili alle opzioni di rasterizzazione:

```csharp
// Specificare il livello da convertire
rasterizationOptions.Layers = new [] { "LayerA" };
```

## Passaggio 4: impostare le opzioni di esportazione JPEG

Ora, crea le opzioni per il formato dell'immagine in cui desideri esportare (JPEG in questo caso):

```csharp
// Crea JpegOptions per l'esportazione
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Passaggio 5: Esporta in formato JPEG

Infine, salva l'immagine convertita:

```csharp
// Definisci il percorso del file di output e salva l'immagine
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## Funzionalità aggiuntiva: converti tutti i livelli

Per convertire tutti i livelli nel disegno CAD, puoi implementare un metodo come questo:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // Scorrere i livelli e salvare ciascuno come file JPEG separato
    // Il tuo codice di implementazione qui
}
```

## Conclusione

Congratulazioni! Hai imparato come convertire efficacemente i layout CAD in formati di immagini raster utilizzando Aspose.CAD per .NET. Questa guida offre un approccio semplice, adatto agli sviluppatori che desiderano conversioni CAD efficienti.

## Domande frequenti

### Posso esportare in formati immagine diversi?

Assolutamente! Semplicemente scambia `JpegOptions` con altre opzioni di formato, come `PngOptions` O `BmpOptions`, a seconda delle vostre esigenze.

### È disponibile una versione di prova?

Sì, puoi scaricare una versione di prova per esplorare le funzionalità seguendo questa [collegamento](https://releases.aspose.com/cad/net/).

### Dove posso trovare supporto per Aspose.CAD?

Per il supporto della community, consulta Aspose.CAD [foro](https://forum.aspose.com/c/cad/19)oppure valuta l'acquisto di una licenza per un'assistenza più dedicata.

### Sono possibili licenze temporanee?

Sì, sono disponibili licenze temporanee; puoi richiederne una [Qui](https://purchase.conholdate.com/temporary-license/).

### Dove posso accedere alla documentazione dettagliata?

Visita la documentazione completa [Qui](https://reference.aspose.com/cad/net/) per maggiori informazioni.