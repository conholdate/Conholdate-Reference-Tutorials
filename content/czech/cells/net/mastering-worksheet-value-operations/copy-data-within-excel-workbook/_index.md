---
"description": "Naučte se, jak efektivně kopírovat data v sešitu aplikace Excel pomocí nástroje Aspose.Cells pro .NET. Postupujte podle tohoto podrobného návodu, abyste snadno duplikovali listy, přenášeli data a snadno spravovali soubory aplikace Excel."
"linktitle": "Kopírování dat v sešitu aplikace Excel pomocí Aspose.Cells pro .NET"
"second_title": "Rozhraní API pro zpracování Excelu Aspose.Cells v .NET"
"title": "Kopírování dat v sešitu aplikace Excel pomocí Aspose.Cells pro .NET"
"url": "/cs/cells/net/mastering-worksheet-value-operations/copy-data-within-excel-workbook/"
"weight": 12
---

## Zavedení

V tomto podrobném návodu si ukážeme, jak kopírovat data v rámci stejného sešitu pomocí Aspose.Cells pro .NET. Podle níže uvedených podrobných pokynů se naučíte, jak programově duplikovat listy a zachovat jejich obsah a formátování.

## Předpoklady pro kopírování dat v Excelu pomocí Aspose.Cells

Než se pustíme do procesu kódování, ujistěte se, že máte vše připravené:

1. Knihovna Aspose.Cells pro .NET: Musíte mít nainstalovanou knihovnu Aspose.Cells pro .NET. Nejnovější verzi si můžete stáhnout z [Stránka ke stažení Aspose.Cells pro .NET](https://releases.aspose.com/cells/net/).
2. Vývojové prostředí: Pro psaní a spouštění kódu je nezbytné IDE kompatibilní s .NET, jako je Visual Studio.
3. Licence Aspose: Můžete použít buď bezplatnou zkušební verzi, nebo zakoupenou licenci. Více informací naleznete na [zde](https://purchase.aspose.com/temporary-license/).

Jakmile jsou nastaveny předpoklady, můžete začít pracovat s knihovnou.

## Import požadovaných balíčků

Nejprve budete muset importovat příslušné jmenné prostory z Aspose.Cells. To vám umožní pracovat se soubory aplikace Excel pomocí tříd a metod poskytovaných Aspose.Cells.

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

Tyto jmenné prostory vám poskytnou přístup k `Workbook` třída (pro práci s excelovými soubory) a `WorksheetCollection` (pro přístup k více listům v sešitu).

## Krok 1: Inicializace cest k souborům pro sešit

Aby byl váš kód uspořádaný, je nezbytné definovat cesty k souborům, kde se váš sešit nachází a kam chcete uložit upravený soubor. Zde je návod, jak můžete tyto cesty zadat:

```csharp
// Definujte cestu k adresáři, kde se nachází soubor Excel.
string dataDir = "Your Directory Path";

// Definujte úplnou cestu ke vstupnímu sešitu.
string inputPath = dataDir + "book1.xls";
```

Nahradit `"Your Directory Path"` se skutečnou cestou k adresáři obsahujícímu sešit. To pomáhá zajistit flexibilitu kódu a efektivní správu cest.

## Krok 2: Otevření sešitu pro přístup k datům

Nyní, když jsou cesty k souborům nastaveny, je dalším krokem načtení sešitu aplikace Excel do `Workbook` objekt. To vám umožňuje přístup k jeho obsahu pro manipulaci.

```csharp
// Načtěte soubor aplikace Excel do objektu Sešit.
Workbook wb = new Workbook(inputPath);
```

S tímto řádkem jste úspěšně načetli `book1.xls` do `wb` objekt a zpřístupnění jeho dat.

## Krok 3: Přístup ke kolekci pracovních listů

Jakmile je sešit načten, máte přístup k listům v něm obsaženým. Aspose.Cells poskytuje `Worksheets` kolekce, která umožňuje interakci s každým listem v sešitu.

```csharp
// Načtěte kolekci pracovních listů ze sešitu.
WorksheetCollection sheets = wb.Worksheets;
```

Ten/Ta/To `sheets` objekt vám nyní poskytuje přístup ke všem pracovním listům v něm `book1.xls`a můžete s nimi provádět různé operace, včetně kopírování dat z jednoho listu do druhého.

## Krok 4: Kopírování dat z jednoho listu do druhého

Pro kopírování dat z jednoho listu do druhého v rámci stejného sešitu nabízí Aspose.Cells snadno použitelnou metodu s názvem `AddCopy`Tato metoda vytvoří duplikát zadaného listu a připojí ho k sešitu.

```csharp
// Zkopírujte data z „Listu1“ do nového listu v sešitu.
sheets.AddCopy("Sheet1");
```

V tomto příkladu kopírujeme data z „Listu1“ do nového listu. `AddCopy` Metoda duplikuje celý list a zachová veškerý jeho obsah, včetně vzorců, formátování a hodnot.

## Krok 5: Uložení upraveného sešitu

Po zkopírování dat můžete upravený sešit uložit pod novým názvem nebo umístěním. To se provede voláním funkce `Save` metoda na `Workbook` objekt.

```csharp
// Uložte upravený sešit pod novým názvem.
wb.Save(dataDir + "book1_copy.xls");
```

Tím se sešit s kopírovaným listem uloží jako `book1_copy.xls` v zadaném adresáři. Název souboru a cestu můžete změnit podle svých potřeb.

## Závěr

Kopírování dat v sešitu aplikace Excel pomocí nástroje Aspose.Cells pro .NET je snadný úkol a tato příručka poskytuje kroky potřebné k jeho efektivnímu provedení. Ať už duplikujete celé listy nebo konkrétní oblasti dat, Aspose.Cells nabízí robustní a flexibilní API, které automatizaci v Excelu zjednodušuje a zefektivňuje.

## Často kladené otázky

### Mohu kopírovat více listů najednou?

Aspose.Cells nepodporuje kopírování více listů v jednom volání. Můžete však procházet listy, které chcete kopírovat, a kopírovat je jednotlivě.

### Jak mohu přejmenovat zkopírovaný list?

Po zkopírování listu jej můžete přejmenovat takto:

```csharp
sheets[sheets.Count - 1].Name = "NewSheetName";
```

### Je Aspose.Cells kompatibilní s .NET Core?

Ano, Aspose.Cells je plně kompatibilní s prostředími .NET Framework i .NET Core.

### Jak Aspose.Cells zvládá formátování během kopírování?

Ten/Ta/To `AddCopy` Metoda zachovává veškerý obsah a formátování při kopírování listů a zajišťuje, že kopírovaná data vypadají identicky s originálem.

### Mohu zkopírovat list do jiného sešitu?

Ano, list můžete zkopírovat do jiného sešitu pomocí `Copy` metoda s odkazem na cílový sešit.

```csharp
sheets.Add().Copy(wb.Worksheets["Sheet1"]);
```