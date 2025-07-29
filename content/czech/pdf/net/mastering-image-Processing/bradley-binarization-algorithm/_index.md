---
"description": "Naučte se, jak převést stránky PDF do vysoce kvalitních binárních obrázků TIFF pomocí Bradleyho binarizačního algoritmu v Aspose.PDF pro .NET. Tato podrobná příručka obsahuje příklad kódu."
"linktitle": "Bradleyho binarizační algoritmus"
"second_title": "Aspose.PDF pro referenční příručku k .NET API"
"title": "Bradleyho binarizační algoritmus"
"url": "/cs/pdf/net/mastering-image-Processing/bradley-binarization-algorithm/"
"weight": 30
---

## Zavedení

V tomto tutoriálu vás provedeme procesem převodu stránky PDF do obrázku TIFF pomocí Bradleyho binarizačního algoritmu. Aspose.PDF pro .NET tento úkol zjednodušuje a umožňuje vám snadno automatizovat a zefektivnit pracovní postupy s dokumenty.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Aspose.PDF pro .NET: Stáhněte si knihovnu z [zde](https://releases.aspose.com/pdf/net/).
- Visual Studio (nebo jakékoli C# IDE).
- Základní znalost C#.
- Platný řidičský průkaz nebo [dočasná licence](https://purchase.aspose.com/temporary-license/) z Aspose.

## Krok 1: Nastavení projektu

Nejprve si ve svém IDE vytvořte nový projekt v C# a importujte potřebné jmenné prostory:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

## Krok 2: Definování adresáře dokumentů

Zadejte cestu k adresáři, kde se nachází váš dokument PDF, a také výstupní cesty pro obrázky TIFF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Cesta k vašemu PDF souboru
```

Tento adresář bude ukládat jak zdrojový PDF, tak i převedené soubory TIFF.

## Krok 3: Načtěte dokument PDF

Otevřete PDF dokument, který chcete převést:

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

Nahradit `PageToTIFF.pdf` názvem vašeho PDF souboru.

## Krok 4: Určení výstupních cest

Definujte výstupní cesty pro generované soubory TIFF:

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Krok 5: Nastavení rozlišení obrazu

Nastavte rozlišení pro obrázky TIFF. Vyšší DPI povede k lepší kvalitě obrazu:

```csharp
Resolution resolution = new Resolution(300);
```

## Krok 6: Konfigurace nastavení TIFF

Nakonfigurujte nastavení pro obrázek TIFF, včetně komprese a barevné hloubky:

```csharp
TiffSettings tiffSettings = new TiffSettings
{
    Compression = CompressionType.LZW,
    Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp
};
```

Použití 1bpp (1 bit na pixel) připraví obraz pro binární výstup.

## Krok 7: Vytvořte zařízení TIFF

Vytvořte zařízení TIFF, které bude provádět konverzi:

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Krok 8: Převod stránky PDF do formátu TIFF

Převeďte první stránku PDF do formátu TIFF:

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Krok 9: Aplikujte Bradleyho binarizační algoritmus

Nyní použijte Bradleyho algoritmus k převodu obrazu TIFF ve stupních šedi na binární obrázek:

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

Ten/Ta/To `BinarizeBradley` Metoda přijímá dva souborové streamy (vstupní a výstupní) a prahovou hodnotu. Pro optimální výsledky upravte prahovou hodnotu dle potřeby.

## Krok 10: Potvrzení úspěšné konverze

Nakonec potvrďte, že konverze proběhla úspěšně:

```csharp
Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

## Závěr

Gratulujeme! Úspěšně jste převedli stránku PDF do obrázku TIFF a aplikovali Bradleyho binarizační algoritmus pomocí Aspose.PDF pro .NET. Tento proces je nezbytný pro archivaci dokumentů, OCR a další profesionální aplikace. Díky vysokému rozlišení a efektivní kompresi budou obrázky vašich dokumentů jasné a zvládnutelné velikosti.

## Často kladené otázky

### Co je Bradleyho algoritmus?
Bradleyho algoritmus je binarizační technika, která převádí obrazy ve stupních šedi na binární obrazy určením adaptivního prahu pro každý pixel na základě jeho okolí.

### Mohu touto metodou převést více stránek PDF do formátu TIFF?
Ano, můžete upravit `Process` metoda pro procházení všech stránek v dokumentu za účelem převodu.

### Jaké je optimální rozlišení pro převod PDF do TIFF?
Pro vysoce kvalitní obrázky se obecně doporučuje rozlišení 300 DPI, ale toto rozlišení si můžete upravit podle svých specifických potřeb.

### Co znamená 1bpp v barevné hloubce?
1bpp (1 bit na pixel) znamená, že obraz bude černobílý, přičemž každý pixel bude buď zcela černý, nebo zcela bílý.

### Je Bradleyho algoritmus vhodný pro OCR?
Ano, Bradleyho algoritmus se často používá v předzpracování OCR, protože zvyšuje kontrast textu ve skenovaných dokumentech a tím zlepšuje přesnost rozpoznávání.