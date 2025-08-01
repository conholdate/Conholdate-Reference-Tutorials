---
"description": "Zjistěte, jak bez problémů převést dokumenty XPS (XML Paper Specification) do PDF (Portable Document Format) pomocí výkonné knihovny Aspose.Page pro .NET."
"linktitle": "Převod XPS do PDF"
"second_title": "Rozhraní Aspose.Page .NET API"
"title": "Převod XPS do PDF pomocí Aspose.Page pro .NET"
"url": "/cs/page/net/convert-document/converting-xps-to-pdf/"
"weight": 11
---

## Zavedení

V tomto tutoriálu se podíváme na to, jak převést dokumenty XPS (XML Paper Specification) do PDF (Portable Document Format) pomocí všestranné knihovny Aspose.Page pro .NET. Tato výkonná knihovna zjednodušuje převod dokumentů a nabízí různé možnosti přizpůsobení, což z ní činí vynikající volbu pro vývojáře.

## Předpoklady

Než začneme, ujistěte se, že máte připraveno následující:

- Knihovna Aspose.Page pro .NET: Stáhněte a nainstalujte knihovnu Aspose.Page pro .NET z [Dokumentace k Aspose.Page](https://reference.aspose.com/page/net/).
  
- Vývojové prostředí: Nastavte vývojové prostředí .NET pomocí Visual Studia nebo jiného kompatibilního IDE.

- Dokument XPS: Mějte připravený soubor XPS, který chcete převést, uložený v určeném adresáři.

## Krok 1: Importujte požadované jmenné prostory

Začněte importem potřebného jmenného prostoru pro přístup k funkcím Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

## Krok 2: Inicializace adresáře dokumentů

Definujte cestu k adresáři, kde jsou uloženy vaše dokumenty:

```csharp
string dataDir = "Your Document Directory";
```

Nezapomeňte vyměnit `"Your Document Directory"` se skutečnou cestou k adresáři obsahujícímu váš dokument XPS.

### Krok 3: Otevření datových proudů PDF a XPS

Dále inicializujte streamy pro vstupní soubor XPS i výstupní soubor PDF:

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Ujistěte se, že máte nastavenou správnou cestu k souborům.

### Krok 4: Načtěte dokument XPS

Nyní načtěte dokument XPS pomocí knihovny Aspose.Page:

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Krok 5: Konfigurace možností ukládání PDF

Nastavte možnosti ukládání PDF, včetně kvality obrazu a parametrů komprese:

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100, // Nastavení úrovně kvality JPEGu
    ImageCompression = PdfImageCompression.Jpeg, // Používejte kompresi JPEG pro obrázky
    TextCompression = PdfTextCompression.Flate, // Použít kompresi Flate pro text
    PageNumbers = new int[] { 1, 2, 6 } // Zadejte čísla stránek, která mají být zahrnuta
};
```

Neváhejte upravit tyto parametry podle svých požadavků.

### Krok 6: Vytvořte zařízení pro vykreslování PDF

Vytvořte vykreslovací zařízení pro formát PDF:

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 7: Uložte dokument jako PDF

Nakonec uložte dokument XPS do PDF pomocí zadaného zařízení a možností:

```csharp
document.Save(device, options);
```

## Závěr

Gratulujeme! Úspěšně jste převedli dokument XPS do PDF pomocí knihovny Aspose.Page pro .NET. Tato knihovna nejen zjednodušuje převod dokumentů, ale také nabízí rozsáhlé možnosti pro práci s různými formáty.

## Často kladené otázky

### Mohu převést více souborů XPS do jednoho PDF?

Rozhodně! Můžete procházet více souborů XPS a sloučit je do jednoho dokumentu PDF pomocí stejných kroků převodu.

### Jaké další výstupní formáty podporuje Aspose.Page pro .NET?

Kromě PDF podporuje Aspose.Page pro .NET řadu formátů, včetně TIFF, JPEG a PNG.

### Jak si mohu přizpůsobit vzhled převedeného PDF?

Parametry můžete upravit v `PdfSaveOptions` objektu, například nastavení kvality JPEG a komprese, abyste dosáhli požadovaného vzhledu.

### Je k dispozici zkušební verze Aspose.Page pro .NET?

Ano, můžete si vyzkoušet Aspose.Page pro .NET s bezplatnou zkušební verzí. [zde](https://releases.aspose.com/).

### Kde najdu komunitní podporu pro Aspose.Page pro .NET?

Pro diskuze s komunitou a podporu navštivte [Fórum Aspose.Page](https://forum.aspose.com/c/page/39).