---
"description": "Zjistěte, jak efektivně spravovat velké datové sady v Excelu pomocí knihovny Aspose.Cells pro .NET. Tato příručka poskytuje podrobný postup pro identifikaci maximálního počtu řádků a sloupců podporovaných formáty souborů XLS i XLSX."
"linktitle": "Nalezení maximálního počtu řádků a sloupců ve formátech XLS a XLSX"
"second_title": "Rozhraní API pro zpracování Excelu Aspose.Cells v .NET"
"title": "Nalezení maximálního počtu řádků a sloupců ve formátech XLS a XLSX"
"url": "/cs/cells/net/mastering-workbook-settings/find-maximum-rows-and-columns/"
"weight": 11
---

## Zavedení

Správa velkých datových sad v Excelu může být náročná, zejména s ohledem na omezení různých formátů souborů. Tento tutoriál vás provede používáním knihovny Aspose.Cells for .NET k určení maximálního počtu řádků a sloupců podporovaných formáty XLS (Excel 97-2003) a XLSX (Excel 2007 a novější). Na konci budete vybaveni k efektivnímu zvládání úkolů souvisejících s Excelem.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. [.NET Framework](https://dotnet.microsoft.com/en-us/download) nebo [.NET Core](https://dotnet.microsoft.com/en-us/download) nainstalovaný ve vašem systému.
2. [Aspose.Cells pro .NET](https://releases.aspose.com/cells/net/) knihovna stažená a odkazovaná ve vašem projektu (můžete ji také nainstalovat pomocí [NuGet](https://www.nuget.org/packages/Aspose.Cells/)).

## Import požadovaných balíčků

Pro import potřebných balíčků z knihovny Aspose.Cells přidejte na začátek souboru C# následující příkazy using:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: Maximální počet řádků a sloupců pro formát XLS

Začněme nalezením maximálního počtu řádků a sloupců podporovaných formátem XLS.

```csharp
// Vytiskněte zprávu o formátu XLS.
Console.WriteLine("Maximum Rows and Columns supported by XLS format:");

// Vytvořte sešit ve formátu XLS.
Workbook wb = new Workbook(FileFormatType.Excel97To2003);

// Načíst maximální počet řádků a sloupců.
int maxRows = wb.Settings.MaxRow + 1;
int maxCols = wb.Settings.MaxColumn + 1;

// Zobrazte výsledky.
Console.WriteLine("Maximum Rows: " + maxRows);
Console.WriteLine("Maximum Columns: " + maxCols);
Console.WriteLine();
```

1. Vytiskněte zprávu, která indikuje, že pracujeme s formátem XLS.
2. Vytvořte `Workbook` instance pro formát XLS s použitím `FileFormatType.Excel97To2003`.
3. Získejte maximální počet řádků a sloupců pomocí `wb.Settings.MaxRow` a `wb.Settings.MaxColumn`, přičemž se přidává 1, protože tyto čísla jsou založena na nule.
4. Vypište maximální počet řádků a sloupců do konzole.

## Krok 2: Maximální počet řádků a sloupců pro formát XLSX

Dále prozkoumáme maximální počet řádků a sloupců podporovaných formátem XLSX.

```csharp
// Vytiskněte zprávu o formátu XLSX.
Console.WriteLine("Maximum Rows and Columns supported by XLSX format:");

// Vytvořte sešit ve formátu XLSX.
wb = new Workbook(FileFormatType.Xlsx);

// Načíst maximální počet řádků a sloupců.
maxRows = wb.Settings.MaxRow + 1;
maxCols = wb.Settings.MaxColumn + 1;

// Zobrazte výsledky.
Console.WriteLine("Maximum Rows: " + maxRows);
Console.WriteLine("Maximum Columns: " + maxCols);
```

1. Vypíše zprávu oznamující, že pracujeme s formátem XLSX.
2. Vytvořte `Workbook` instance pro formát XLSX s použitím `FileFormatType.Xlsx`.
3. Načtěte a vypište maximální počet řádků a sloupců jako předtím.

## Krok 3: Zobrazení zprávy o úspěchu

Po provedení kroků označme úspěch.

```csharp
Console.WriteLine("Execution completed successfully: Maximum Rows and Columns retrieval for both formats.");
```

## Závěr

V tomto tutoriálu jste se naučili, jak pomocí knihovny Aspose.Cells pro .NET najít maximální počet řádků a sloupců podporovaných formáty souborů XLS a XLSX. Pochopení těchto omezení je nezbytné pro efektivní správu dat v Excelu a zajištění souladu vašich datových sad s možnostmi formátu.

## Často kladené otázky

### Jaký je maximální počet řádků podporovaných formátem XLS?
Maximální počet řádků podporovaných formátem XLS je 65 536.

### Jaký je maximální počet sloupců podporovaných formátem XLS?
Maximální počet sloupců podporovaných formátem XLS je 256.

### Jaký je maximální počet řádků podporovaných formátem XLSX?
Maximální počet řádků podporovaných formátem XLSX je 1 048 576.

### Jaký je maximální počet sloupců podporovaných formátem XLSX?
Maximální počet sloupců podporovaných formátem XLSX je 16 384.

### Mohu použít knihovnu Aspose.Cells pro .NET s jinými formáty souborů aplikace Excel?
Ano, Aspose.Cells pro .NET podporuje různé formáty souborů, včetně XLS, XLSX, ODS a dalších. Zkontrolujte [dokumentace](https://reference.aspose.com/cells/net/) pro podrobnosti o podporovaných funkcích a možnostech.