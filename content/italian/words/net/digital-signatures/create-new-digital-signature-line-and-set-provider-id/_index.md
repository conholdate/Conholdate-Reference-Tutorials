---
"description": "Scopri come aggiungere righe di firma ai tuoi documenti Word tramite codice sorgente utilizzando Aspose.Words per .NET. Questa guida completa copre tutti gli aspetti, dalla configurazione dell'ambiente di sviluppo all'inserimento di righe di firma e alla firma sicura dei documenti."
"linktitle": "Crea una nuova riga di firma digitale e imposta l'ID del fornitore"
"second_title": "API di elaborazione dei documenti Aspose.Words"
"title": "Crea una nuova riga di firma digitale e imposta l'ID del fornitore"
"url": "/it/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Introduzione

Ciao, appassionati di tecnologia! Avete mai desiderato automatizzare l'inclusione delle righe di firma nei vostri documenti Word? Oggi spiegheremo come farlo utilizzando Aspose.Words per .NET. Questa guida passo passo vi guiderà nella creazione di una riga di firma e nell'impostazione dell'ID provider, rendendo le vostre attività di elaborazione dei documenti più efficienti e snelle.

## Prerequisiti

Prima di iniziare, assicuriamoci di aver impostato tutto:

1. Aspose.Words per .NET: se non lo hai ancora installato, scaricalo [Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: utilizzare Visual Studio o qualsiasi configurazione di sviluppo C#.
3. .NET Framework: assicurati che .NET Framework sia installato sul tuo computer.
4. Certificato PFX: per firmare i documenti è necessario un certificato PFX, che può essere ottenuto da un'autorità di certificazione attendibile.

## Importazione degli spazi dei nomi necessari

Per iniziare, importa gli spazi dei nomi richiesti nel tuo progetto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Ora entriamo nei dettagli della creazione di una nuova riga di firma e dell'impostazione dell'ID del provider.

## Passaggio 1: creare un nuovo documento

Per prima cosa, dobbiamo creare un nuovo documento Word, che servirà da base per la nostra riga della firma:

```csharp
// Specificare il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Qui, inizializziamo un nuovo `Document` e un `DocumentBuilder`, che ci consente di aggiungere elementi facilmente.

## Passaggio 2: definire le opzioni della riga della firma

Successivamente, definiremo le opzioni per la riga della nostra firma, inclusi il nome del firmatario, il titolo, l'email e altri dettagli rilevanti:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Queste opzioni aiutano a personalizzare la riga della firma, rendendola chiara e professionale.

## Passaggio 3: inserire la riga della firma

Con le opzioni pronte, possiamo ora inserire la riga della firma nel documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

IL `InsertSignatureLine` Il metodo aggiunge la riga della firma e le assegniamo un ID provider univoco.

## Passaggio 4: Salva il documento

Dopo aver inserito la riga della firma, salviamo il documento:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

In questo modo il documento verrà salvato con la riga della firma appena aggiunta.

## Passaggio 5: impostare le opzioni di firma

Ora configureremo le opzioni di firma, tra cui l'ID della riga della firma, l'ID del provider, i commenti e l'ora della firma:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Queste impostazioni garantiscono che il documento venga firmato con i dati corretti.

## Passaggio 6: creare il titolare del certificato

Per firmare il documento, dobbiamo creare un titolare del certificato utilizzando il certificato PFX:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Sostituire `"morzal.pfx"` con il nome effettivo del file del certificato e `"aw"` con la password del tuo certificato.

## Fase 7: Firmare il documento

Infine, firmeremo il documento utilizzando l'utilità di firma digitale:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Questo processo firma il documento e lo salva come nuovo file.

## Conclusione

Congratulazioni! Hai creato con successo una riga di firma e impostato l'ID del provider in un documento Word utilizzando Aspose.Words per .NET. Questa potente libreria semplifica le attività di elaborazione dei documenti, rendendo il tuo flusso di lavoro più efficiente. Provala e scopri come può migliorare i tuoi progetti!

## Domande frequenti

### Posso personalizzare l'aspetto della riga della firma?
Assolutamente! Puoi regolare varie opzioni nel `SignatureLineOptions` per adattarsi al tuo stile e alle tue esigenze.

### Cosa succede se non ho un certificato PFX?
Sarà necessario ottenerne uno da un'autorità di certificazione attendibile, poiché è essenziale per la firma digitale dei documenti.

### Posso aggiungere più righe di firma a un documento?
Sì, è possibile aggiungere più righe di firma ripetendo il processo di inserimento con opzioni diverse.

### Aspose.Words per .NET è compatibile con .NET Core?
Sì, Aspose.Words per .NET supporta .NET Core, rendendolo versatile per vari ambienti di sviluppo.

### Quanto sono sicure le firme digitali?
Le firme digitali create con Aspose.Words sono estremamente sicure, a condizione che si utilizzi un certificato valido e attendibile.