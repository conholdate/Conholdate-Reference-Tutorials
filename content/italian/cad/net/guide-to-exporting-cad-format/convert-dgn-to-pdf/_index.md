---
"description": "Scopri come convertire senza sforzo i file DGN in PDF utilizzando la potente libreria Aspose.CAD per .NET. Questa guida passo passo è pensata per sviluppatori di tutti i livelli."
"linktitle": "Converti DGN in PDF in Aspose.CAD per .NET"
"second_title": "Aspose.CAD .NET - Formato file CAD e BIM"
"title": "Converti DGN in PDF in Aspose.CAD per .NET"
"url": "/it/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## Introduzione

Orientarsi nel mondo dei file CAD può essere impegnativo, ma con Aspose.CAD per .NET, gli sviluppatori possono manipolare e convertire facilmente vari formati CAD. Un'esigenza comune è la conversione di file DGN in PDF, che esploreremo passo dopo passo in questo tutorial.

## Prerequisiti

Per seguire il corso, assicurati di avere quanto segue:

- Conoscenza di base di C# e del framework .NET.
- Libreria Aspose.CAD per .NET installata. Puoi scaricarla [Qui](https://releases.aspose.com/cad/net/).
- Un file DGN di esempio (ad esempio, Nikon_D90_Camera.dgn). 

## Passaggio 1: importare gli spazi dei nomi richiesti

Per iniziare, importa gli spazi dei nomi pertinenti nel tuo progetto C#:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Passaggio 2: caricare il file DGN

Specifica la directory per il tuo file DGN e caricalo utilizzando il seguente codice:

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // Ulteriori elaborazioni verranno eseguite qui...
}
```

## Passaggio 3: configurare le opzioni di rasterizzazione

Successivamente, imposta le opzioni di rasterizzazione per definire come verrà visualizzato il tuo DGN nel PDF:

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // Regola la larghezza secondo necessità
    PageHeight = 300, // Regolare l'altezza secondo necessità
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## Passaggio 4: creare opzioni PDF

Definire le opzioni PDF, integrando le impostazioni di rasterizzazione configurate in precedenza:

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Passaggio 5: Salvare il DGN come PDF

Infine, salva il file DGN come PDF utilizzando le opzioni che hai configurato:

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## Conclusione

Congratulazioni! Hai convertito con successo un file DGN in PDF utilizzando Aspose.CAD per .NET. Questo semplice tutorial ti ha guidato nel caricamento del file DGN, nell'impostazione delle opzioni di rasterizzazione e nel salvataggio dell'output in PDF.

## Domande frequenti

### Per utilizzare Aspose.CAD è necessaria una conoscenza pregressa del CAD?  
Assolutamente sì! Aspose.CAD è progettato per semplificare le attività CAD complesse, rendendole accessibili a tutti gli sviluppatori, indipendentemente dalle loro conoscenze CAD.

### Dove posso trovare ulteriori risorse e documentazione per Aspose.CAD?  
Puoi esplorare guide ed esempi completi in [Documentazione Aspose.CAD](https://reference.aspose.com/cad/net/).

### È disponibile una versione di prova gratuita per Aspose.CAD?  
Sì, è possibile ottenere una prova gratuita [Qui](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.CAD?  
È possibile richiedere licenze temporanee [Qui](https://purchase.conholdate.com/temporary-license/).

### Hai bisogno di assistenza o hai domande?  
Unisciti alla conversazione nel [Forum Aspose.CAD](https://forum.aspose.com/c/cad/19) per supporto e richieste alla comunità.