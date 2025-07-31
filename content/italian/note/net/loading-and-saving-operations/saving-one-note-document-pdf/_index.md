---
"description": "Scopri come salvare in modo efficiente i documenti di Microsoft OneNote come file PDF utilizzando Aspose.Note per .NET. Questa guida illustra i prerequisiti necessari e offre utili FAQ."
"linktitle": "Salvataggio di documenti OneNote in PDF"
"second_title": "API Aspose.Note .NET"
"title": "Salvataggio di documenti OneNote in PDF tramite Aspose.Note per .NET"
"url": "/it/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Introduzione

In questo tutorial, esploreremo come salvare documenti in formato PDF utilizzando Aspose.Note per .NET. Aspose.Note è una potente libreria che consente agli sviluppatori di lavorare con i file di Microsoft OneNote a livello di codice. Illustreremo i prerequisiti, importeremo gli spazi dei nomi e forniremo guide dettagliate per il salvataggio di documenti in PDF in diversi layout di pagina.

## Prerequisiti
1. Visual Studio: assicurati che sia installato.
2. Aspose.Note per .NET: scarica e installa la libreria.
3. Conoscenza del linguaggio C#: è richiesta una conoscenza di base del linguaggio.

## Importazione degli spazi dei nomi necessari
Prima di procedere, importa i seguenti namespace nel tuo codice:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Passaggio 1: Salva in PDF con le impostazioni della pagina Lettera
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Aggiorna questo percorso
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Carica il documento OneNote e lo salva come PDF utilizzando le impostazioni di pagina in formato Lettera.

## Passaggio 2: Salva in PDF con impostazioni pagina A4 (nessun limite di altezza)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Aggiorna questo percorso
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Simile al passaggio 1, ma utilizza le impostazioni della pagina A4 senza limitazioni di altezza.

## Conclusione
Il tutorial illustra con successo come convertire i file OneNote in formato PDF utilizzando Aspose.Note. Utilizzando diverse impostazioni di pagina, gli sviluppatori ottengono maggiore flessibilità nella gestione dei documenti.

## Domande frequenti
### Aspose.Note può gestire file OneNote complessi?
Sì, gestisce efficacemente varie funzionalità dei file OneNote complessi.

### Aspose.Note è adatto ai progetti commerciali?
Sì, puoi utilizzarlo per applicazioni commerciali dopo aver acquistato una licenza.

### Aspose.Note offre una prova gratuita?
Sì, è disponibile una prova gratuita per l'esplorazione.

### Dove posso trovare la documentazione per Aspose.Note?
La documentazione dettagliata è disponibile sul sito di riferimento di Aspose.

### Hai bisogno di ulteriore assistenza?
Per domande e supporto, fare riferimento al forum Aspose.Note.