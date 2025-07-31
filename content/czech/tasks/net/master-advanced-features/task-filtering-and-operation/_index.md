---
"description": "Naučte se, jak využít třídu v Aspose.Tasks pro .NET k filtrování projektových úkolů na základě více podmínek. Kombinací kritérií, jako jsou souhrnné úkoly a atributy jiné než null."
"linktitle": "Filtrování úloh AND operace v Aspose.Tasks"
"second_title": "Rozhraní Aspose.Tasks .NET API"
"title": "Filtrování úloh AND operace v Aspose.Tasks"
"url": "/cs/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Zavedení

V tomto tutoriálu se podíváme na to, jak provádět pokročilé filtrování projektových úkolů v Aspose.Tasks pro .NET pomocí... `Util.And` třída. Tato výkonná funkce umožňuje vývojářům efektivně filtrovat úlohy na základě více kritérií.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Základní znalost programování v C#.
2. Aspose.Tasks pro .NET je nainstalován. Pokud jste tak ještě neučinili, můžete si jej stáhnout z [tento odkaz](https://releases.aspose.com/tasks/net/).
3. Integrované vývojové prostředí (IDE), jako je Visual Studio, pro psaní a spouštění kódu.

## Import jmenných prostorů

Chcete-li začít, musíte importovat požadované jmenné prostory do svého projektu v C#. To vám umožní přístup k funkcím poskytovaným Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Krok 1: Inicializace projektu a shromažďování úloh

Nejprve inicializujte projekt Aspose.Tasks a shromážděte v něm všechny úlohy. Pro demonstrační účely budeme předpokládat, že existuje soubor projektu s názvem `Project2.mpp`.

```csharp
// Cesta k adresáři dokumentů
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Shromáždit všechny podřízené úkoly
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Krok 2: Definování podmínek filtru

V tomto kroku definujeme podmínky pro filtrování úkolů. V našem příkladu vytvoříme dvě podmínky: jednu pro filtrování souhrnných úkolů a druhou pro zajištění toho, aby úkoly neměly hodnotu null.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Krok 3: Kombinace podmínek s operací AND

Dalším krokem je zkombinovat tyto podmínky pomocí `Util.And` třída. To nám umožňuje vytvořit složenou podmínku, která vyžaduje obě kritéria.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Krok 4: Použití kombinovaných úkolů podmínky a filtru

Nyní aplikujme kombinovanou podmínku na shromážděné úkoly, abychom odfiltrovali konkrétní úkoly, které splňují obě podmínky.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Krok 5: Výpis filtrovaných úloh

Nakonec projdeme filtrované úkoly a zobrazíme relevantní podrobnosti. To nám pomůže pochopit, které úkoly splňují naše kritéria.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Závěr

V tomto tutoriálu jsme si ukázali, jak provádět pokročilé operace filtrování v Aspose.Tasks pro .NET pomocí... `Util.And` třída. Kombinací více podmínek můžeme efektivně filtrovat úkoly, a tím zvýšit užitečnost našich aplikací pro řízení projektů.

## Často kladené otázky

### Co je Aspose.Tasks pro .NET?

Aspose.Tasks pro .NET je komplexní API určené pro vývojáře, kteří chtějí programově manipulovat se soubory Microsoft Projectu v rámci .NET aplikací.

### Mohu pomocí Util.And kombinovat více než dvě podmínky?

Ano! Ten/Ta/To `Util.And` Třída umožňuje kombinovat více podmínek, což umožňuje komplexní logiku filtrování přizpůsobenou vašim potřebám.

### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?

Ano, můžete si stáhnout bezplatnou zkušební verzi z [tento odkaz](https://releases.aspose.com/).

### Kde najdu podrobnou dokumentaci k Aspose.Tasks?

Podrobná dokumentace je k dispozici [zde](https://reference.aspose.com/tasks/net/).

### Jak mohu vyhledat podporu pro Aspose.Tasks?

Podpora je k dispozici prostřednictvím komunitního fóra Aspose.Tasks, které je přístupné [zde](https://forum.aspose.com/c/tasks/15).