---
"description": "Scopri come estrarre allegati email in C# utilizzando Aspose.Email per .NET. Guida dettagliata con esempi per PDF, immagini e altro ancora."
"linktitle": "Estrarre allegati di posta elettronica in C# - Tutorial Aspose.Email"
"second_title": "API di elaborazione e-mail Aspose.Email .NET"
"title": "Estrarre allegati di posta elettronica in C# - Tutorial Aspose.Email"
"url": "/it/email/net/handling-email-attachments/extract-email-attachments-in-csharp/"
"weight": 14
---

## Introduzione

Ti è mai capitato di dover scaricare manualmente gli allegati di posta elettronica, uno per uno? Non solo richiede molto tempo, ma è anche soggetto a errori. Fortunatamente, Aspose.Email per .NET offre un modo potente ed efficiente per automatizzare questa attività. Che si tratti di PDF, immagini o qualsiasi altro tipo di file, puoi estrarre gli allegati senza sforzo utilizzando C#.

In questa guida, ti guideremo attraverso un tutorial completo, partendo dai prerequisiti fino a un esempio completamente funzionante. Pronti a risparmiare ore di lavoro manuale? Iniziamo!

## Prerequisiti

Prima di iniziare a programmare, assicurati di avere quanto segue:

- Visual Studio installato sul tuo computer.
- Aspose.Email per la libreria .NET. Puoi [scaricalo qui](https://releases.aspose.com/email/net/) oppure installarlo tramite NuGet.
- Un account di posta elettronica valido (supportato IMAP/POP3).
- Una conoscenza di base della programmazione C#.

Se sei nuovo su Aspose.Email, prendi in considerazione la possibilità di richiedere un [prova gratuita](https://releases.aspose.com/) o un [licenza temporanea](https://purchase.aspose.com/temporary-license/) per sbloccare tutte le funzionalità.

## Importa pacchetti

Prima di immergerti nel codice, assicurati di aver importato gli spazi dei nomi necessari. Aggiungi quanto segue all'inizio del tuo file C#:

```csharp
using Aspose.Email;
using Aspose.Email.Clients.Imap;
using Aspose.Email.Clients.Pop3;
```

Suddividiamo il processo in fasi facilmente assimilabili. Seguiamo attentamente ogni passaggio per garantirne un'esecuzione fluida.


## Passaggio 1: configura il tuo client IMAP

Il primo passo è connettersi al server di posta elettronica utilizzando il protocollo IMAP. IMAP consente di accedere e recuperare i messaggi di posta elettronica dal server.

```csharp
ImapClient client = new ImapClient("imap.example.com", "username", "password");
client.SelectFolder(ImapFolderInfo.InBox);
```

- Sostituire `imap.example.com` con l'indirizzo del server IMAP del tuo provider di posta elettronica (ad esempio, `imap.gmail.com` per Gmail).
- Utilizza la tua email reale `username` E `password`.
- `SelectFolder(ImapFolderInfo.InBox)` specifica che vogliamo lavorare con la posta in arrivo.


## Passaggio 2: recupera le email dalla posta in arrivo

Una volta connessi, è necessario recuperare i messaggi di posta elettronica dalla posta in arrivo. Aspose.Email fornisce un metodo semplice per elencare tutti i messaggi.

```csharp
ImapMessageInfoCollection messages = client.ListMessages();
```

- `ListMessages()` recupera i metadati di tutte le email nella posta in arrivo.
- IL `ImapMessageInfoCollection` L'oggetto contiene dettagli quali mittente, oggetto e ID univoci.


## Passaggio 3: recupera ogni messaggio e-mail

Per accedere al contenuto e agli allegati, è necessario recuperare ogni e-mail utilizzando il suo ID univoco.


```csharp
foreach (ImapMessageInfo messageInfo in messages)
{
    MailMessage message = client.FetchMessage(messageInfo.UniqueId);
}
```

- IL `foreach` il ciclo scorre tutti i messaggi.
- `FetchMessage()` recupera il contenuto effettivo dell'email per un dato ID messaggio.


## Passaggio 4: scorrere gli allegati

Ora che hai il contenuto dell'email, è il momento di estrarre gli allegati. Ogni `MailMessage` l'oggetto contiene una raccolta di allegati.

```csharp
foreach (Attachment attachment in message.Attachments)
{
    Console.WriteLine($"Attachment Name: {attachment.Name}");
}
```

- IL `Attachments` La proprietà elenca tutti gli allegati presenti nell'e-mail.
- Utilizzo `attachment.Name` per ottenere il nome del file.


## Passaggio 5: Salva gli allegati sul disco

Infine, salva gli allegati sul tuo computer locale. Puoi filtrare i file per tipo, dimensione o altri criteri.

```csharp
foreach (Attachment attachment in message.Attachments)
{
    string filePath = Path.Combine("C:\\Attachments", attachment.Name);
    using (var stream = new FileStream(filePath, FileMode.Create))
    {
        attachment.Save(stream);
    }
}
```

- Sostituire `"C:\\Attachments"` con il percorso della cartella desiderato.
- IL `attachment.Save()` Il metodo scrive il file sul disco.


## Fase 6: Elaborare gli allegati per tipo

Se hai bisogno di gestire gli allegati in modo diverso in base al tipo (ad esempio, PDF o JPEG), Aspose.Email semplifica la procedura.

```csharp
if (attachment.ContentType.MediaType == "application/pdf")
{
    Console.WriteLine("Processing PDF...");
}
else if (attachment.ContentType.MediaType == "image/jpeg")
{
    Console.WriteLine("Processing JPEG...");
}
```

- `ContentType.MediaType` identifica il tipo di file (ad esempio, `application/pdf` per i PDF, `image/jpeg` per le immagini).
- Aggiungere logica personalizzata per diversi tipi di file, secondo necessità.


## Conclusione

Ed ecco fatto! Estrarre allegati dalle email non è più un compito noioso. Con Aspose.Email per .NET, puoi automatizzare questo processo in poche righe di codice. Dalla configurazione del client IMAP al salvataggio degli allegati in locale, questa guida ha coperto tutto il necessario per iniziare. 

Allora perché aspettare? [Scarica Aspose.Email](https://releases.aspose.com/email/net/) e inizia subito a semplificare i flussi di lavoro della tua posta elettronica!


## Domande frequenti

### Posso usare questo codice con Gmail o Outlook?
Sì! Sostituisci `imap.example.com` con Gmail (`imap.gmail.com`) o di Outlook (`outlook.office365.com`) Indirizzo del server IMAP.

### Aspose.Email è gratuito?
Aspose.Email richiede una licenza per tutte le funzionalità. Puoi richiederne una [prova gratuita](https://releases.aspose.com/) o un [licenza temporanea](https://purchase.aspose.com/temporary-license/).

### Come posso gestire la sicurezza delle password?
Si consiglia di utilizzare variabili di ambiente o un archivio di credenziali sicuro anziché password codificate in modo rigido.

### Posso estrarre gli allegati dagli elementi inviati?
Sì, basta usare `SelectFolder(ImapFolderInfo.Sent)` invece della posta in arrivo.

### Aspose.Email supporta POP3?
Assolutamente sì! Oltre a IMAP, supporta anche POP3 e SMTP.