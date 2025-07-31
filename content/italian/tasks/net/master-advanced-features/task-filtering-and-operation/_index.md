---
"description": "Scopri come sfruttare la classe in Aspose.Tasks per .NET per filtrare le attività di progetto in base a più condizioni, combinando criteri come attività di riepilogo e attributi non nulli."
"linktitle": "Filtraggio e operazione delle attività in Aspose.Tasks"
"second_title": "API .NET di Aspose.Tasks"
"title": "Filtraggio e operazione delle attività in Aspose.Tasks"
"url": "/it/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Introduzione

In questo tutorial, esploreremo come eseguire il filtraggio avanzato delle attività del progetto in Aspose.Tasks per .NET utilizzando `Util.And` classe. Questa potente funzionalità consente agli sviluppatori di filtrare le attività in modo efficiente in base a più criteri.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Conoscenza di base della programmazione C#.
2. Aspose.Tasks per .NET installato. Se non l'hai ancora fatto, puoi scaricarlo da [questo collegamento](https://releases.aspose.com/tasks/net/).
3. Un ambiente di sviluppo integrato (IDE) come Visual Studio per scrivere ed eseguire il codice.

## Importazione di spazi dei nomi

Per iniziare, è necessario importare gli spazi dei nomi richiesti nel progetto C#. Questo consentirà di accedere alle funzionalità fornite da Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Passaggio 1: inizializzare il progetto e raccogliere le attività

Per prima cosa, inizializza un progetto Aspose.Tasks e raccogli tutti i task al suo interno. A scopo dimostrativo, supporremo che ci sia un file di progetto denominato `Project2.mpp`.

```csharp
// Percorso alla directory dei documenti
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Raccogli tutte le attività figlio
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Passaggio 2: definire le condizioni del filtro

In questo passaggio, definiremo le condizioni per filtrare le attività. Nel nostro esempio, creeremo due condizioni: una per filtrare le attività di riepilogo e un'altra per garantire che le attività non siano nulle.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Passaggio 3: combinare le condizioni con l'operazione AND

Il passo successivo è quello di combinare queste condizioni utilizzando il `Util.And` classe. Ciò ci consente di creare una condizione composita che impone entrambi i criteri.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Passaggio 4: applicare le attività di condizione e filtro combinate

Ora applichiamo la condizione combinata alle attività raccolte per filtrare le attività specifiche che soddisfano entrambe le condizioni.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Passaggio 5: Emissione delle attività filtrate

Infine, analizzeremo le attività filtrate e ne otterremo i dettagli rilevanti. Questo ci aiuterà a individuare le attività che soddisfano i nostri criteri.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Conclusione

In questo tutorial, abbiamo dimostrato come eseguire operazioni di filtraggio avanzate in Aspose.Tasks per .NET utilizzando `Util.And` classe. Combinando più condizioni, possiamo filtrare efficacemente le attività, migliorando così l'utilità delle nostre applicazioni di gestione dei progetti.

## Domande frequenti

### Che cos'è Aspose.Tasks per .NET?

Aspose.Tasks per .NET è un'API completa progettata per consentire agli sviluppatori di manipolare programmaticamente i file di Microsoft Project all'interno delle applicazioni .NET.

### Posso combinare più di due condizioni utilizzando Util.And?

Sì! Il `Util.And` La classe consente di combinare più condizioni, consentendo una logica di filtraggio complessa su misura per le tue esigenze.

### È disponibile una versione di prova gratuita per Aspose.Tasks?

Sì, puoi scaricare una versione di prova gratuita da [questo collegamento](https://releases.aspose.com/).

### Dove posso trovare la documentazione dettagliata per Aspose.Tasks?

È disponibile la documentazione dettagliata [Qui](https://reference.aspose.com/tasks/net/).

### Come posso richiedere supporto per Aspose.Tasks?

Il supporto è disponibile tramite il forum della community Aspose.Tasks, a cui è possibile accedere [Qui](https://forum.aspose.com/c/tasks/15).