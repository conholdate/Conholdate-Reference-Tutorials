---
"description": "Zjistěte, jak vylepšit kvalitu dokumentů aplikace Excel programově upravovat záhlaví a zápatí pomocí nástroje Aspose.Cells pro .NET. Tato komplexní příručka vás provede každým krokem – od nastavení sešitu až po dynamické vkládání názvu listu."
"linktitle": "Implementace záhlaví a zápatí s Aspose.Cells pro .NET"
"second_title": "Rozhraní API pro zpracování Excelu Aspose.Cells v .NET"
"title": "Implementace záhlaví a zápatí s Aspose.Cells pro .NET"
"url": "/cs/cells/net/mastering-worksheet-page-setup-features/implement-header-footer/"
"weight": 22
---

## Zavedení

Záhlaví a zápatí jsou základními prvky v tabulkách aplikace Excel a poskytují důležité kontextové informace, jako jsou názvy souborů, data a čísla stránek. Ať už automatizujete sestavy nebo generujete dynamické soubory, Aspose.Cells pro .NET zjednodušuje proces programově upravovaných záhlaví a zápatí. Tato příručka nabízí podrobný postup, jak vylepšit vaše soubory aplikace Excel pomocí elegantních a profesionálních záhlaví a zápatí.

## Předpoklady

Než se ponoříte, ujistěte se, že máte následující:

1. Aspose.Cells pro .NET: Stáhněte si a nainstalujte z [zde](https://releases.aspose.com/cells/net/).
2. Nastavení IDE: Použijte Visual Studio nebo vámi preferované IDE s frameworkem .NET.
3. Licence: Začněte s bezplatnou zkušební verzí, ale pro kompletní funkčnost zvažte pořízení plné nebo dočasné licence. Můžete [získat dočasnou licenci](https://purchase.aspose.com/temporary-license/).

## Import požadovaných balíčků

Začněte importem potřebných jmenných prostorů do vašeho projektu:

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

To vám poskytne přístup ke třídám a metodám potřebným pro práci se záhlavími, zápatími a dalšími funkcemi Excelu v Aspose.Cells.

## Krok 1: Vytvořte sešit a nastavení stránky v aplikaci Access

Začněte vytvořením nového sešitu a přístupem k nastavení stránky listu. Zde upravíte nastavení záhlaví a zápatí.

```csharp
// Definujte cestu k uložení dokumentu
string dataDir = "Your Document Directory";

// Vytvoření instance objektu Workbook
Workbook excel = new Workbook();
```

Zde, a `Workbook` Objekt představuje váš soubor aplikace Excel. `PageSetup` Vlastnost listu vám umožní přizpůsobit záhlaví a zápatí.

## Krok 2: Přístup k vlastnostem listu a nastavení stránky

Každý pracovní list v Aspose.Cells má `PageSetup` vlastnost, která řídí funkce rozvržení, včetně záhlaví a zápatí. Získejte `PageSetup` objekt pro váš pracovní list:

```csharp
// Získání odkazu na PageSetup prvního listu
PageSetup pageSetup = excel.Worksheets[0].PageSetup;
```

Teď, `pageSetup` obsahuje nastavení potřebná k přizpůsobení záhlaví a zápatí.

## Krok 3: Nastavení levé části záhlaví

Záhlaví se skládají ze tří částí: levé, středové a pravé. Začněme nastavením levé části pro zobrazení názvu listu.

```csharp
// Nastavení názvu listu v levé části záhlaví
pageSetup.SetHeader(0, "&A");
```

Používání `&A` dynamicky zobrazuje název listu, což je obzvláště užitečné pro sešity s více listy.

## Krok 4: Přidejte datum a čas do středu záhlaví

Dále přidejte aktuální datum a čas do střední části záhlaví a pro styling použijte vlastní písmo.

```csharp
// Nastavit datum a čas do střední části záhlaví tučným písmem
pageSetup.SetHeader(1, "&\"Times New Roman,Bold\"&D-&T");
```

V tomto řádku:
- `&D` vloží aktuální datum.
- `&T` vloží aktuální čas.
- `"Times New Roman,Bold"` použije tučné písmo Times New Roman.

## Krok 5: Zobrazení názvu souboru v pravé části záhlaví

Pro dokončení záhlaví zobrazte název souboru na pravé straně s určenou velikostí písma.

```csharp
// Zobrazit název souboru v pravé části záhlaví s vlastní velikostí písma
pageSetup.SetHeader(2, "&\"Times New Roman,Bold\"&12&F");
```

Zde, `&F` představuje název souboru a `&12` nastaví velikost písma na 12.

## Krok 6: Přidání vlastního textu do sekce levé patičky

Nyní nastavme levou část zápatí vlastním textem a specifickým stylem písma.

```csharp
// Přidat vlastní text se stylem písma do levé části zápatí
pageSetup.SetFooter(0, "Hello World! &\"Courier New\"&14 123");
```

V tomto příkladu text `123` je stylizováno písmem „Courier New“ velikosti 14, zatímco zbytek zůstává ve výchozím písmu zápatí.

## Krok 7: Vložte číslo stránky do středu zápatí

Zahrnutí čísel stránek do zápatí pomáhá čtenářům sledovat vícestránkové dokumenty.

```csharp
// Vložit číslo stránky do střední části zápatí
pageSetup.SetFooter(1, "&P");
```

Ten/Ta/To `&P` Kód přidá aktuální číslo stránky do střední části zápatí.

## Krok 8: Zobrazení celkového počtu stránek v pravé části zápatí

Doplňte zápatí zobrazením celkového počtu stránek v pravé části.

```csharp
// Zobrazit celkový počet stránek v pravé části zápatí
pageSetup.SetFooter(2, "&N");
```

Ten/Ta/To `&N` Kód poskytuje celkový počet stránek a informuje čtenáře o délce dokumentu.

## Krok 9: Uložení sešitu

Nakonec sešit uložte a vygenerujte soubor aplikace Excel s přizpůsobenými záhlavími a zápatími.

```csharp
// Uložit sešit
excel.Save(dataDir + "SetHeadersAndFooters_out.xls");
```

Tento řádek uloží soubor s vašimi úpravami.

## Závěr

Úpravy záhlaví a zápatí v listech aplikace Excel zvyšují profesionalitu vašich dokumentů. S Aspose.Cells pro .NET můžete tyto prvky snadno ovládat, od zobrazování názvů listů až po vkládání vlastního textu, data, časů a dynamických čísel stránek. Nyní, když jste se naučili jednotlivé kroky, můžete vylepšit své automatizované projekty v Excelu.

## Často kladené otázky

### Mohu použít různá písma pro různé části záhlaví a zápatí?
Ano, Aspose.Cells umožňuje zadat jedinečná písma pro každou sekci záhlaví a zápatí.

### Jak odstraním záhlaví a zápatí?
Vymazání záhlaví a zápatí nastavením jejich textu na prázdný řetězec pomocí `SetHeader` nebo `SetFooter`.

### Mohu vkládat obrázky do záhlaví nebo zápatí pomocí Aspose.Cells pro .NET?
Aspose.Cells v současné době primárně podporuje text v záhlavích a zápatích. Obrázky mohou vyžadovat alternativní metody, například jejich vkládání přímo do listu.

### Podporuje Aspose.Cells dynamická data v záhlavích a zápatích?  
Ano, můžete použít různé dynamické kódy (například `&D` pro datum nebo `&P` pro číslo stránky) pro přidání dynamického obsahu.

### Jak mohu upravit výšku záhlaví nebo zápatí?  
Aspose.Cells nabízí možnosti v rámci `PageSetup` třída pro úpravu okrajů záhlaví a zápatí, což vám dává kontrolu nad rozestupy.