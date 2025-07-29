---
"description": "Scopri come aggiungere una nuova firma digitale a un file Excel firmato esistente utilizzando Aspose.Cells per .NET. Questa guida completa illustra tutti i prerequisiti, le istruzioni dettagliate e un esempio di codice."
"linktitle": "Aggiunta di una nuova firma digitale al file Excel firmato"
"second_title": "API di elaborazione Excel .NET Aspose.Cells"
"title": "Aggiunta di una nuova firma digitale al file Excel firmato"
"url": "/it/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## Introduzione

Nell'attuale panorama digitale, garantire l'autenticità e l'integrità dei documenti è più cruciale che mai. Le firme digitali offrono un modo affidabile per verificare che un documento non sia stato alterato e che provenga da una fonte legittima. Se lavorate con file Excel in .NET e dovete aggiungere una nuova firma digitale a un file già firmato, questa guida è per voi! Vi guideremo attraverso il processo di aggiunta di una firma digitale a un file Excel firmato esistente utilizzando Aspose.Cells per .NET.

## Prerequisiti

Prima di addentrarci nell'implementazione, assicurati di avere quanto segue:

1. Aspose.Cells per .NET: Scarica e installa Aspose.Cells da [pagina di rilascio](https://releases.aspose.com/cells/net/).
2. .NET Framework: assicurati che sul tuo computer sia installato .NET Framework e che tu abbia familiarità con i concetti base della programmazione .NET.
3. Certificato digitale: ottieni un certificato digitale valido in formato .pfx. Per testare, puoi creare un certificato autofirmato.
4. Ambiente di sviluppo: utilizza un IDE come Visual Studio per scrivere ed eseguire il codice C#.
5. Esempio di file Excel: avere un file Excel esistente già firmato digitalmente, che sarà la destinazione per l'aggiunta di una nuova firma.

Con questi prerequisiti, passiamo subito al codice!

## Importa i pacchetti necessari

Nella parte superiore del file C#, includi i seguenti namespace per accedere alle classi e ai metodi richiesti:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Passaggio 1: definisci le tue directory

Specificare le directory per i file sorgente e dove salvare il file di output:

```csharp
// Directory di origine
string sourceDir = "Your Document Directory"; // Sostituisci con la tua directory effettiva
// Directory di output
string outputDir = "Your Document Directory"; // Sostituisci con la tua directory effettiva
```

## Passaggio 2: caricare la cartella di lavoro firmata esistente

Caricare la cartella di lavoro di Excel già firmata:

```csharp
// Caricare la cartella di lavoro già firmata digitalmente
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## Passaggio 3: creare una raccolta di firme digitali

Crea una raccolta per gestire le tue firme digitali:

```csharp
// Creare la raccolta di firme digitali
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## Passaggio 4: carica il tuo certificato

Carica il tuo certificato digitale, che verrà utilizzato per creare la nuova firma:

```csharp
// File del certificato e relativa password
string certFileName = sourceDir + "AsposeDemo.pfx"; // Il tuo file di certificato
string password = "aspose"; // La password del tuo certificato

// Crea un nuovo certificato
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## Passaggio 5: creare una nuova firma digitale

Ora crea una nuova firma digitale e aggiungila alla tua raccolta:

```csharp
// Crea una nuova firma digitale e aggiungila alla raccolta
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## Passaggio 6: aggiungere la raccolta di firme alla cartella di lavoro

Aggiungere la raccolta di firme digitali alla cartella di lavoro:

```csharp
// Aggiungi la raccolta di firme digitali alla cartella di lavoro
workbook.AddDigitalSignature(dsCollection);
```

## Passaggio 7: Salvare la cartella di lavoro

Salva la cartella di lavoro con la nuova firma digitale inclusa:

```csharp
// Salva la cartella di lavoro
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## Passaggio 8: conferma il successo

Fornire un feedback in caso di esecuzione riuscita:

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## Conclusione

Congratulazioni! Hai aggiunto con successo una nuova firma digitale a un file Excel già firmato utilizzando Aspose.Cells per .NET. Questo processo migliora la sicurezza dei tuoi documenti e ne garantisce l'autenticità e l'integrità.

## Domande frequenti

### Che cos'è una firma digitale?

Una firma digitale è uno schema matematico che verifica l'autenticità e l'integrità di messaggi o documenti digitali, assicurando che non siano stati alterati e confermando l'identità del firmatario.

### Ho bisogno di un certificato speciale per creare una firma digitale?

Sì, per creare una firma digitale valida è necessario un certificato digitale rilasciato da un'autorità di certificazione (CA) attendibile.

### Posso utilizzare un certificato autofirmato per i test?

Assolutamente sì! È possibile utilizzare un certificato autofirmato per scopi di sviluppo e test, ma per la produzione è consigliabile utilizzare un certificato rilasciato da una CA attendibile.

### Cosa succede se provo ad aggiungere una firma a un documento non firmato?

Se si tenta di aggiungere una firma digitale a un documento che non è ancora firmato, l'operazione funzionerà senza problemi, ma la firma originale non sarà presente.

### Dove posso trovare maggiori informazioni su Aspose.Cells?

Per guide dettagliate e riferimenti API, consultare [Documentazione di Aspose.Cells](https://reference.aspose.com/cells/net/).