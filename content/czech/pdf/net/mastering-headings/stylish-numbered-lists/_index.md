---
"description": "Zjistěte, jak vytvářet krásně číslované seznamy ve vašich PDF dokumentech pomocí Aspose.PDF pro .NET. Tato příručka vás provede procesem použití různých stylů číslování – například římských číslic."
"linktitle": "Stylové číslované seznamy pomocí Aspose.PDF pro .NET"
"second_title": "Aspose.PDF pro referenční příručku k .NET API"
"title": "Stylové číslované seznamy pomocí Aspose.PDF pro .NET"
"url": "/cs/net/programming-with-headings/stylish-numbered-lists/"
"weight": 10
---

## Zavedení

Potřebovali jste někdy ve svých PDF dokumentech vytvořit dobře strukturované, číslované seznamy? Ať už se jedná o právní dokumenty, zprávy nebo prezentace, efektivní styly číslování jsou klíčové pro organizaci vašeho obsahu. S Aspose.PDF pro .NET můžete snadno aplikovat různé styly číslování na nadpisy PDF, což vede k propracovaným a profesionálním dokumentům.

## Předpoklady

Než se pustíme do kódování, ujistěte se, že máte připravené následující:

1. Aspose.PDF pro .NET: Stáhněte si nejnovější verzi z [zde](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí: Budete potřebovat Visual Studio nebo jakékoli IDE kompatibilní s .NET.
3. .NET Framework: Ujistěte se, že máte nainstalovaný .NET Framework 4.0 nebo vyšší.
4. Licence: Můžete použít dočasnou licenci od [zde](https://purchase.aspose.com/temporary-license/) nebo prozkoumejte [bezplatná zkušební verze](https://releases.aspose.com/) možnosti.

## Import požadovaných balíčků

Začněte importem potřebných jmenných prostorů do vašeho projektu:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 1: Nastavení dokumentu

Začněme vytvořením nového dokumentu PDF a nastavením jeho rozvržení, včetně velikosti stránky a okrajů.

```csharp
// Cesta k adresáři s dokumenty.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Nastavení rozměrů a okrajů stránky
pdfDoc.PageInfo.Width = 612.0; // 8,5 palce
pdfDoc.PageInfo.Height = 792.0; // 11 palců
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo(72, 72, 72, 72); // okraje 1 palec
```

Toto nastavení dává vašemu dokumentu standardní velikost Letter s okraji o velikosti jednoho palce na všech stranách.

## Krok 2: Přidání stránky do PDF

Dále přidáme do dokumentu PDF prázdnou stránku, na kterou později použijeme styly číslování.

```csharp
// Přidání nové stránky do dokumentu PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo = pdfDoc.PageInfo; // Použijte stejná nastavení jako v dokumentu
```

## Krok 3: Vytvoření plovoucího rámečku

Plovoucí pole (FloatingBox) umožňuje umístit obsah nezávisle na toku stránky, což vám dává větší kontrolu nad rozvržením.

```csharp
// Vytvořte FloatingBox pro strukturovaný obsah
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox
{
    Margin = pdfPage.PageInfo.Margin
};
pdfPage.Paragraphs.Add(floatBox);
```

## Krok 4: Přidání nadpisů římskými číslicemi

Nyní přidejme náš první nadpis s malými římskými číslicemi.

```csharp
// Vytvořte první nadpis pomocí římských číslic
Aspose.Pdf.Heading heading1 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 1,
    Text = "List 1",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading1);
```

## Krok 5: Přidání druhého nadpisu s vlastním počátečním číslem

Dále přidáme druhý nadpis, počínaje římskou číslicí 13.

```csharp
// Vytvořte druhý nadpis začínající římskou číslicí 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 13,
    Text = "List 2",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading2);
```

## Krok 6: Přidání nadpisu s abecedním číslováním

Pro zpestření přidejme třetí nadpis s použitím abecedního číslování malými písmeny.

```csharp
// Vytvořte nadpis s abecedním číslováním
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2)
{
    IsInList = true,
    StartNumber = 1,
    Text = "The value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed",
    Style = NumberingStyle.LettersLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading3);
```

## Krok 7: Uložení PDF souboru

Nakonec uložte soubor PDF do požadovaného adresáře.

```csharp
// Uložit dokument PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine($"\nNumber style applied successfully in headings.\nFile saved at {dataDir}");
```

## Závěr

Gratulujeme! Úspěšně jste pomocí Aspose.PDF pro .NET použili různé styly číslování – římské číslice a abecední – na nadpisy v souboru PDF. Flexibilita Aspose.PDF vám umožňuje ovládat rozvržení stránky, styly číslování a umístění obsahu, což vám umožňuje vytvářet dobře organizované a profesionální dokumenty PDF.

## Často kladené otázky

### Mohu na stejný dokument PDF použít různé styly číslování?  
Ano, v jednom dokumentu můžete kombinovat různé styly číslování, například římské číslice, arabské číslice a abecední číslování.

### Jak mohu přizpůsobit počáteční číslování pro nadpisy?  
Počáteční číslo pro libovolný nadpis můžete nastavit pomocí `StartNumber` vlastnictví.

### Existuje způsob, jak resetovat pořadí číslování?  
Ano, číslování můžete resetovat úpravou `StartNumber` vlastnost pro každý nadpis.

### Mohu kromě číslování použít na nadpisy tučné písmo nebo kurzívu?  
Rozhodně! Styly nadpisů si můžete přizpůsobit úpravou vlastností, jako je písmo, velikost, tučné písmo a kurzíva, pomocí `TextState` objekt.

### Jak získám dočasnou licenci pro Aspose.PDF?  
Dočasné povolení můžete získat od [zde](https://purchase.aspose.com/temporary-license/) otestovat Aspose.PDF bez omezení.