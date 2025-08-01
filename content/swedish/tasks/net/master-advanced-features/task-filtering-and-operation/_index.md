---
"description": "Lär dig hur du använder klassen i Aspose.Tasks för .NET för att filtrera projektuppgifter baserat på flera villkor. Genom att kombinera kriterier som sammanfattningsuppgifter och attribut som inte är null."
"linktitle": "Uppgiftsfiltrering OCH operation i Aspose.Tasks"
"second_title": "Aspose.Tasks .NET API"
"title": "Uppgiftsfiltrering OCH operation i Aspose.Tasks"
"url": "/sv/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Introduktion

I den här handledningen kommer vi att utforska hur man utför avancerad filtrering av projektuppgifter i Aspose.Tasks för .NET genom att använda `Util.And` klass. Den här kraftfulla funktionen låter utvecklare filtrera uppgifter effektivt baserat på flera kriterier.

## Förkunskapskrav

Innan vi börjar, se till att du har följande:

1. Grundläggande kunskaper i C#-programmering.
2. Aspose.Tasks för .NET installerat. Om du inte har gjort det än kan du ladda ner det från [den här länken](https://releases.aspose.com/tasks/net/).
3. En integrerad utvecklingsmiljö (IDE) som Visual Studio för att skriva och köra koden.

## Importera namnrymder

För att komma igång måste du importera de namnrymder som krävs till ditt C#-projekt. Detta ger dig tillgång till funktionerna som tillhandahålls av Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Steg 1: Initiera projektet och samla in uppgifter

Först, initiera ett Aspose.Tasks-projekt och samla alla uppgifter i det. För demonstrationsändamål antar vi att det finns en projektfil med namnet `Project2.mpp`.

```csharp
// Sökväg till dokumentkatalogen
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Samla alla underordnade uppgifter
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Steg 2: Definiera filtervillkor

I det här steget definierar vi villkoren för filtrering av uppgifter. I vårt exempel skapar vi två villkor: ett för att filtrera sammanfattningsuppgifter och ett annat för att säkerställa att uppgifterna inte är null.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Steg 3: Kombinera villkor med OCH-operationen

Nästa steg är att kombinera dessa villkor med hjälp av `Util.And` klass. Detta gör att vi kan skapa ett sammansatt villkor som kräver båda kriterierna.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Steg 4: Tillämpa de kombinerade villkors- och filteruppgifterna

Nu ska vi tillämpa det kombinerade villkoret på de insamlade uppgifterna för att filtrera bort de specifika uppgifter som uppfyller båda villkoren.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Steg 5: Skriv ut de filtrerade uppgifterna

Slutligen kommer vi att iterera igenom våra filtrerade uppgifter och mata ut relevant information. Detta hjälper oss att förstå de uppgifter som uppfyller våra kriterier.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Slutsats

I den här handledningen visade vi hur man utför avancerade filtreringsåtgärder i Aspose.Tasks för .NET med hjälp av `Util.And` klass. Genom att kombinera flera villkor kan vi effektivt filtrera uppgifter och därigenom förbättra användbarheten hos våra projektledningsprogram.

## Vanliga frågor

### Vad är Aspose.Tasks för .NET?

Aspose.Tasks för .NET är ett omfattande API utformat för att utvecklare ska kunna manipulera Microsoft Project-filer programmatiskt inom .NET-applikationer.

### Kan jag kombinera fler än två villkor med Util.And?

Ja! Den `Util.And` klassen låter dig kombinera flera villkor, vilket möjliggör komplex filtreringslogik skräddarsydd efter dina behov.

### Finns det en gratis testversion av Aspose.Tasks?

Ja, du kan ladda ner en gratis testversion från [den här länken](https://releases.aspose.com/).

### Var kan jag hitta detaljerad dokumentation för Aspose.Tasks?

Detaljerad dokumentation finns tillgänglig [här](https://reference.aspose.com/tasks/net/).

### Hur kan jag söka support för Aspose.Tasks?

Support finns tillgänglig via Aspose.Tasks communityforum, som kan nås [här](https://forum.aspose.com/c/tasks/15).