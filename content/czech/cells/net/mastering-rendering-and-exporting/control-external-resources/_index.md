---
"description": "Odemkněte plný potenciál převodů z Excelu do PDF s Aspose.Cells pro .NET. V této komplexní příručce se naučíte, jak spravovat externí zdroje, jako jsou obrázky, a zajistit, aby vaše PDF soubory přesně odpovídaly vašim požadavkům na formátování."
"linktitle": "Ovládání externích zdrojů pomocí Aspose.Cells pro .NET"
"second_title": "Rozhraní API pro zpracování Excelu Aspose.Cells v .NET"
"title": "Ovládání externích zdrojů pomocí Aspose.Cells pro .NET"
"url": "/cs/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## Zavedení

dnešní digitální krajině je převod tabulek Excelu do dokumentů PDF běžným a nezbytným úkolem. Ať už připravujete zprávy, finanční data nebo prezentační materiály, je klíčové zajistit, aby vaše PDF soubory odpovídaly zamýšlenému formátu. Aspose.Cells pro .NET poskytuje výkonnou knihovnu, která vám umožňuje detailně řídit tento proces převodu, zejména při práci s externími zdroji, jako jsou obrázky. V této příručce prozkoumáme, jak efektivně spravovat externí zdroje během procesu převodu Excelu do PDF pomocí Aspose.Cells. Pojďme se do toho pustit!

## Předpoklady

Než začneme, ujistěte se, že máte připravené následující:

1. Visual Studio nebo jakékoli vývojové prostředí kompatibilní s .NET: Toto bude vaše vývojové prostředí.
2. Aspose.Cells pro .NET: Pokud jste jej ještě nenainstalovali, navštivte [Soubory ke stažení Aspose](https://releases.aspose.com/cells/net/) stránku pro získání nejnovější verze.
3. Základní znalost C#: Znalost C# bude výhodou. Pokud potřebujete objasnit nějaké koncepty, neváhejte si je vyhledat.
4. Ukázkový soubor aplikace Excel: Připravte si soubor aplikace Excel, například „samplePdfSaveOptions_StreamProvider.xlsx“, který obsahuje externí zdroje, jež chcete převést.
5. Soubor obrázku pro testování: Během převodu použijte jako externí zdroj soubor obrázku, například „newPdfSaveOptions_StreamProvider.png“.

## Importovat potřebné balíčky

Pro začátek budete muset importovat požadované jmenné prostory z knihovny Aspose.Cells. Na začátek souboru C# přidejte následující direktivy using:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

Tyto jmenné prostory poskytují základní třídy a metody pro vaše úlohy.

## Krok 1: Vytvoření třídy poskytovatele streamu

Nejprve vytvořte třídu poskytovatele streamu, která implementuje `IStreamProvider` rozhraní. Tato třída vám umožní řídit, jak se načítají externí zdroje.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // Načíst obrázek do paměťového proudu
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: Tato metoda se volá při uzavření streamu, aktuálně se zaznamenává ladicí zpráva.
- InitStream: Tato metoda načte externí obrazový soubor jako bajtové pole, převede ho do paměťového proudu a přiřadí ho k `options.Stream` vlastnictví.

## Krok 2: Nastavení zdrojového a výstupního adresáře

Dále definujte adresáře pro váš soubor Excel a výstupní PDF.

```csharp
// Zdrojový adresář
string sourceDir = "Your Document Directory";
// Výstupní adresář
string outputDir = "Your Document Directory";
```

Nahradit `"Your Document Directory"` se skutečnou cestou ve vašem systému, kde se vaše soubory nacházejí.

## Krok 3: Načtěte soubor aplikace Excel

Nyní načtěte soubor Excel, ze kterého chcete vytvořit PDF.

```csharp
// Načtěte zdrojový soubor Excel obsahující externí obrázky
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

Ten/Ta/To `Workbook` Třída z Aspose.Cells představuje váš soubor Excel, který může obsahovat různé externí zdroje, jako například obrázky.

## Krok 4: Nastavení možností ukládání PDF

Před uložením sešitu jako PDF zadejte požadované možnosti uložení.

```csharp
// Zadejte možnosti ukládání PDF – poskytovatel streamu
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // Uložit každý list na novou stránku
};
```

Tím se vytvoří instance `PdfSaveOptions`, což vám umožňuje přizpůsobit formát PDF. `OnePagePerSheet` Tato možnost zajistí, že se každý list aplikace Excel zobrazí ve výsledném PDF na samostatné stránce.

## Krok 5: Přiřaďte svého poskytovatele streamu

Připojte svůj `Workbook` instance s `MyStreamProvider` třídu, kterou jste vytvořili dříve.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

Tento řádek zajišťuje, že kdykoli se během převodu setkáte s externími zdroji, váš vlastní poskytovatel je bude odpovídajícím způsobem spravovat.

## Krok 6: Uložte sešit jako PDF

Nyní uložte sešit aplikace Excel jako PDF.

```csharp
// Uložit sešit do PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

Zavoláním `Save` Metodou na objektu sešitu a předáním výstupního adresáře spolu s možnostmi PDF převedete soubor Excel do dobře naformátovaného PDF.

## Krok 7: Potvrzení úspěšného provedení

Nakonec je dobrým zvykem potvrdit, že proces byl úspěšně dokončen.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

Tato zpráva vás bude informovat o stavu vaší operace a poskytne vám užitečnou zpětnou vazbu.

## Závěr

Nyní jste zvládli proces správy externích zdrojů během převodů z Excelu do PDF pomocí Aspose.Cells! Dodržením těchto kroků zajistíte, že vaše dokumenty budou přesně obsahovat obrázky a další externí prvky, což pokaždé povede k dokonale vybroušenému finálnímu produktu.

## Často kladené otázky

### Co je Aspose.Cells?
Aspose.Cells je výkonná knihovna pro vývojáře .NET, která umožňuje vytváření, manipulaci, konverzi a vykreslování souborů aplikace Excel v různých formátech.

### Jak si stáhnu Aspose.Cells?
Nejnovější verzi si můžete stáhnout z [Odkaz ke stažení](https://releases.aspose.com/cells/net/).

### Mohu si Aspose.Cells vyzkoušet zdarma?
Ano! Bezplatnou zkušební verzi si můžete vyzkoušet na [Stránka s bezplatnou zkušební verzí](https://releases.aspose.com/).

### Kde najdu podporu pro Aspose.Cells?
S dotazy týkajícími se podpory navštivte [Fórum podpory Aspose](https://forum.aspose.com/c/cells/9).

### Jak mohu získat dočasnou licenci pro Aspose.Cells?
Můžete požádat o dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).