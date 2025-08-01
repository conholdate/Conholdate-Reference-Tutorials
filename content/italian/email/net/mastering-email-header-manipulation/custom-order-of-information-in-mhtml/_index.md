---
"description": "Scopri come definire un ordine di informazioni personalizzato in MHTML utilizzando Aspose.Email per .NET in questo tutorial passo passo."
"linktitle": "Ordine personalizzato delle informazioni in MHTML con Aspose.Email"
"second_title": "API di elaborazione e-mail Aspose.Email .NET"
"title": "Ordine personalizzato delle informazioni in MHTML con Aspose.Email"
"url": "/it/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## Introduzione

La creazione di formati di posta elettronica avanzati può migliorare notevolmente la comunicazione, soprattutto quando si esportano email in formati di file diversi come MHTML. Aspose.Email per .NET offre agli sviluppatori un potente toolkit per la manipolazione delle email, che include la definizione di un ordine personalizzato per la visualizzazione delle informazioni durante l'esportazione in MHTML. In questa guida, analizzeremo i passaggi necessari per raggiungere questo obiettivo, rendendola facile da seguire sia per gli sviluppatori esperti che per chi è alle prime armi. Quindi, iniziamo subito!

## Prerequisiti

Prima di addentrarti nella definizione dell'ordine personalizzato delle informazioni in MHTML, ci sono alcuni prerequisiti che devi verificare:

1. Ambiente di sviluppo .NET: assicurati di aver configurato un ambiente di sviluppo .NET. Puoi utilizzare Visual Studio, Visual Studio Code o qualsiasi altro IDE compatibile.

2. Libreria Aspose.Email: è necessario che sia installata la libreria Aspose.Email per .NET. È possibile scaricare l'ultima versione da [Pagina delle versioni di Aspose](https://releases.aspose.com/email/net/).

3. Conoscenza di base di C#: la familiarità con la programmazione C# ti aiuterà a comprendere meglio il codice.

4. Esempio di file di posta elettronica: avrai bisogno di un campione `.eml` file (ad esempio, `Attachments.eml`) a scopo di test.

Una volta soddisfatti questi prerequisiti, sei pronto per seguire il tutorial!

## Importa pacchetti

Per iniziare a scrivere il codice, è necessario importare gli spazi dei nomi necessari dalla libreria Aspose.Email. Questo è essenziale per accedere a tutte le classi e i metodi necessari per la manipolazione dei file di posta elettronica.

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

Includili all'inizio del tuo file C#. Ora sei pronto per immergerti nella programmazione!

Ora che hai impostato tutto, suddividiamo il tutorial in passaggi gestibili.

## Passaggio 1: imposta la directory dei dati

La prima cosa da fare è stabilire una directory in cui verranno archiviati i file di posta elettronica. Può essere qualsiasi percorso sul computer locale.

```csharp
string dataDir = "Your Data Directory";
```

Sostituire `"Your Data Directory"` con il percorso effettivo in cui ti trovi `.eml` si trova il file. Ad esempio, se il file è in `C:\Emails`, scriveresti:

```csharp
string dataDir = @"C:\Emails\";
```

## Passaggio 2: carica il messaggio e-mail

Successivamente, è necessario caricare il `.eml` file in un `MailMessage` oggetto. Ciò consente di manipolare il contenuto e i metadati dell'e-mail.

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

Assicurati che il nome del file corrisponda a quello presente nella directory specificata. Se il file ha un nome diverso, aggiornalo di conseguenza.

## Passaggio 3: imposta le opzioni di salvataggio MHTML

Una volta caricata l'email, è il momento di definire come salvarla in formato MHTML. Puoi iniziare con le opzioni predefinite.

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

Questa riga inizializza le opzioni di salvataggio MHTML, preparando il terreno per la successiva personalizzazione delle intestazioni.

## Passaggio 4: Salva MHTML con l'ordine predefinito

Salviamo l'email come MHTML seguendo l'ordine predefinito. Questo ci fornirà una base di riferimento con cui effettuare il confronto dopo la personalizzazione.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

Esegui questa riga e controlla la directory specificata. Ora dovresti vedere un nuovo file MHTML denominato `CustomOrderOfInformationInMHTML_1.mhtml`Aprilo per vedere come vengono visualizzate le informazioni per impostazione predefinita.

## Passaggio 5: personalizzare l'ordine dell'intestazione

Ora arriva la parte divertente! Puoi specificare quali intestazioni includere nell'output MHTML e in quale ordine. Inizieremo con alcune intestazioni comuni.

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

Aggiungendo queste intestazioni, stai comunicando ad Aspose come desideri che venga visualizzata l'e-mail.

## Passaggio 6: Salva MHTML con ordine personalizzato

Dopo aver personalizzato le intestazioni, è necessario salvare nuovamente l'e-mail come MHTML per vedere come il nuovo ordine influisce sull'output.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

Esegui questo codice, quindi apri `CustomOrderOfInformationInMHTML_2.mhtml`Confrontalo con il primo per vedere come le informazioni sono cambiate in base all'ordine dell'intestazione.

## Passaggio 7: Cancella e aggiungi un nuovo ordine di intestazione

se volessi un ordine completamente diverso? Puoi ricominciare da capo cancellando le impostazioni dell'intestazione esistenti.

```csharp
opt.RenderingHeaders.Clear();
```

Ora è il momento di definire un nuovo ordine per le intestazioni. Ad esempio, se si desidera dare priorità agli allegati e ai destinatari delle copie:

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## Passaggio 8: Salva MHTML con nuovo ordine personalizzato

Infine, salva l'e-mail un'ultima volta con le nuove impostazioni dell'intestazione.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

Dopo aver eseguito questa riga, apri `CustomOrderOfInformationInMHTML_3.mhtml` e controlla come vengono presentate le informazioni in base alla tua nuova personalizzazione.

## Conclusione

Ed ecco qui una guida semplice per definire un ordine personalizzato delle informazioni in MHTML utilizzando Aspose.Email per .NET. Seguendo questi passaggi, puoi controllare il modo in cui le tue email vengono rappresentate in formato MHTML, assicurandoti che le informazioni più importanti siano presentate nel modo più adatto alle tue esigenze. 

## Domande frequenti

### Che cos'è MHTML?
MHTML è l'acronimo di "MIME HTML", un formato di archivio di pagine web che combina HTML e altre risorse come le immagini.

### Posso usare Aspose.Email gratuitamente?
Sì, Aspose offre una versione di prova gratuita che gli sviluppatori possono esplorare. Puoi trovarla [Qui](https://releases.aspose.com/).

### Cosa succede se riscontro problemi durante l'utilizzo di Aspose.Email?
Puoi ottenere supporto dalla comunità tramite [Forum di Aspose](https://forum.aspose.com/c/email/12/).

### È disponibile una licenza temporanea per Aspose.Email?
Sì, puoi richiedere una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/).

### Dove posso acquistare Aspose.Email?
Puoi acquistare la biblioteca qui [collegamento](https://purchase.aspose.com/buy).