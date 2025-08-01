---
"description": "Objevte, jak efektivně spravovat velké soubory Excelu úpravou úrovní komprese pomocí Aspose.Cells pro .NET. Tato podrobná příručka pokrývá vše od nastavení adresářů až po měření doby komprese a pomáhá vám optimalizovat velikost souborů a zlepšit výkon."
"linktitle": "Úprava úrovně komprese v sešitu"
"second_title": "Rozhraní API pro zpracování Excelu Aspose.Cells v .NET"
"title": "Úprava úrovně komprese v sešitu"
"url": "/cs/cells/net/mastering-workbook-operations/adjusting-compression-level/"
"weight": 14
---

## Zavedení

Správa velkých souborů aplikace Excel může být náročná, zejména pokud jde o efektivitu ukládání a přenosu. Naštěstí komprese souborů může výrazně zmenšit velikost těchto souborů, což usnadňuje jejich práci. Pokud používáte Aspose.Cells pro .NET, máte možnost snadno upravit úroveň komprese svých sešitů. Tato příručka vás krok za krokem provede procesem a poskytne vám jasné vysvětlení každé části kódu.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte následující předpoklady:

1. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.
2. Knihovna Aspose.Cells: Stáhněte a nainstalujte knihovnu Aspose.Cells z [zde](https://releases.aspose.com/cells/net/).
3. Visual Studio: Pro spuštění kódu je nutné vývojové prostředí, jako je Visual Studio.
4. .NET Framework: Ujistěte se, že váš projekt je nastaven s kompatibilní verzí .NET Framework.

## Import potřebných balíčků

Chcete-li začít, musíte do svého projektu C# importovat potřebné balíčky. Na začátek souboru s kódem přidejte následující řádky:

```csharp
using Aspose.Cells.Rendering;
using Aspose.Cells.WebExtensions;
using System;
```

Tyto balíčky jsou nezbytné pro práci s excelovými soubory pomocí knihovny Aspose.Cells. `Aspose.Cells` jmenný prostor obsahuje všechny třídy potřebné pro manipulaci se soubory aplikace Excel, zatímco `Aspose.Cells.Xlsb` nabízí možnosti pro ukládání souborů ve formátu XLSB.

## Krok 1: Definování zdrojového a výstupního adresáře

Nejprve nastavte adresáře, kde se nacházejí zdrojové soubory a kam chcete ukládat výstupní soubory:

```csharp
// Definování zdrojového a výstupního adresáře
string sourceDir = "Your Document Directory\\";
string outDir = "Your Document Directory\\";
```

Nezapomeňte vyměnit `"Your Document Directory\\"` se skutečnými cestami k vašim adresářům. Tím zajistíte, že váš program dokáže najít soubory, se kterými potřebuje pracovat.

## Krok 2: Načtení sešitu

Dále načtěte sešit, který chcete komprimovat:

```csharp
Workbook workbook = new Workbook(sourceDir + "LargeSampleFile.xlsx");
```

Zde vytvoříme novou instanci třídy `Workbook` třídu a načtěte existující soubor aplikace Excel. Ujistěte se, že název souboru odpovídá názvu ve zdrojovém adresáři.

## Krok 3: Nastavení možností ukládání

Nyní nakonfigurujte možnosti ukládání pro váš sešit:

```csharp
XlsbSaveOptions options = new XlsbSaveOptions();
```

Ten/Ta/To `XlsbSaveOptions` Třída umožňuje zadat různé možnosti při ukládání sešitu ve formátu XLSB, včetně úrovní komprese.

## Krok 4: Změřte dobu komprese pro úroveň 1

Začněte s první úrovní komprese a změřte čas potřebný k uložení sešitu:

```csharp
options.CompressionType = OoxmlCompressionType.Level1;
var watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_1_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 1 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Tento úryvek kódu nastaví typ komprese na úroveň 1, uloží sešit a změří uplynulý čas.

## Krok 5: Změřte dobu komprese pro úroveň 6

Dále otestujte výkon s kompresí úrovně 6:

```csharp
options.CompressionType = OoxmlCompressionType.Level6;
watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_6_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 6 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Tento krok je podobný předchozímu, ale s vyšší úrovní komprese.

## Krok 6: Změřte dobu komprese pro úroveň 9

Nakonec vyhodnoťte výkon s nejvyšší úrovní komprese:

```csharp
options.CompressionType = OoxmlCompressionType.Level9;
watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_9_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 9 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

V tomto kroku se nastaví úroveň komprese na úroveň 9, kde pravděpodobně dojde k nejvýznamnějšímu zmenšení velikosti souboru, i když zpracování může trvat déle.

## Krok 7: Konečný výstup

Po dokončení všech úrovní komprese se zobrazí zpráva oznamující, že proces byl úspěšně dokončen:

```csharp
Console.WriteLine("Compression adjustment completed successfully.");
```

Tento jednoduchý řádek potvrzuje, že váš program proběhl bez problémů.

## Závěr

Úprava úrovně komprese sešitů pomocí Aspose.Cells pro .NET je přímočarý proces, který může vést k významnému zlepšení velikosti souborů a výkonu. Dodržováním kroků popsaných v této příručce můžete efektivně implementovat kompresi ve svých aplikacích a vylepšit tak možnosti správy souborů v Excelu.

## Často kladené otázky

### Co je Aspose.Cells?  
Aspose.Cells je výkonná knihovna pro .NET, která umožňuje vývojářům vytvářet, manipulovat a převádět soubory aplikace Excel bez nutnosti používat Microsoft Excel.

### Jak nainstaluji Aspose.Cells?  
Aspose.Cells si můžete stáhnout a nainstalovat z [Webové stránky Aspose](https://releases.aspose.com/cells/net/).

### Jaké jsou k dispozici úrovně komprese?  
Aspose.Cells podporuje několik úrovní komprese od úrovně 1 (nejnižší komprese) do úrovně 9 (nejvyšší komprese).

### Mohu si Aspose.Cells vyzkoušet zdarma?  
Ano! Můžete získat bezplatnou zkušební verzi Aspose.Cells. [zde](https://releases.aspose.com/).

### Kde najdu podporu pro Aspose.Cells?  
V případě jakýchkoli dotazů nebo potřeby podpory navštivte fórum podpory Aspose. [zde](https://forum.aspose.com/c/cells/9).