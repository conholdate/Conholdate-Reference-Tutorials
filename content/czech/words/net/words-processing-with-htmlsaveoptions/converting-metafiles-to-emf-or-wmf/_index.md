---
"description": "Naučte se, jak bez problémů převádět obrázky SVG do formátů EMF nebo WMF v dokumentech Word pomocí Aspose.Words pro .NET. Podrobný návod s příklady kódu pro přesné a kompatibilní výsledky."
"linktitle": "Převod metasouborů do formátu EMF nebo WMF"
"second_title": "Rozhraní API pro zpracování dokumentů Aspose.Words"
"title": "Převod metasouborů do formátu EMF nebo WMF"
"url": "/cs/words/net/words-processing-with-htmlsaveoptions/converting-metafiles-to-emf-or-wmf/"
"weight": 10
---

## Zavedení

Efektivní správa a převod obrazových formátů je klíčovou součástí vytváření profesionálních dokumentů Word. V této příručce se ponoříme do používání Aspose.Words pro .NET k převodu obrázků SVG do formátů EMF (Enhanced Metafile) nebo WMF (Windows Metafile) pro bezproblémovou integraci. Tento tutoriál poskytuje jasné a podrobné pokyny, které vývojářům pomohou snadno implementovat převod.

## Předpoklady pro převod SVG do EMF nebo WMF

Pro zajištění hladkého průběhu vývoje je nutné splnit následující požadavky:

- Aspose.Words pro .NET: Získejte nejnovější verzi z [Stránka s vydáním Aspose](https://releases.aspose.com/words/net/).
- .NET Framework: Ověřte instalaci .NET Framework (nebo .NET Core/5/6 v závislosti na vašem prostředí).
- Vývojové prostředí: Visual Studio se doporučuje pro své robustní funkce.
- Znalost C#: Základní znalost programování v C# je nezbytná.

## Import požadovaných jmenných prostorů

Ve svém projektu importujte potřebné jmenné prostory pro přístup k funkcím Aspose.Words:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Definování adresáře dokumentů

Nastavte cestu k adresáři, kam budou uloženy vaše dokumenty Wordu. To je nezbytné pro efektivní správu výstupních souborů.

```csharp
string dataDir = @"C:\MyDocuments\";
```

Nahradit `@"C:\MyDocuments\"` s vaší požadovanou cestou.

## Krok 2: Příprava HTML řetězce obsahujícího SVG

Vytvořte řetězec HTML s vloženým obsahem SVG. To umožní Aspose.Words vykreslit a zpracovat SVG.

```csharp
string htmlContent = 
    @"<html>
        <body>
            <svg xmlns='http://www.w3.org/2000/svg šířka='300' výška='100' viewBox='0 0 300 100'>
                <rect x='10' y='10' width='280' height='80' fill='blue' stroke='black' stroke-width='2'/>
                <text x='20' y='60' fill='white' font-size='20'>Aspose SVG Example</text>
            </svg>
        </body>
    </html>";
```

## Krok 3: Konfigurace možností načítání HTML

Pro zajištění správného zpracování konverze SVG nakonfigurujte `HtmlLoadOptions` s `ConvertSvgToEmf`.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions
{
    ConvertSvgToEmf = true
};
```

## Krok 4: Načtení HTML do dokumentu Wordu

Pomocí nakonfigurovaných možností načítání vytvořte `Document` objekt z HTML řetězce.

```csharp
using (MemoryStream htmlStream = new MemoryStream(Encoding.UTF8.GetBytes(htmlContent)))
{
    Document document = new Document(htmlStream, loadOptions);
}
```

## Krok 5: Konfigurace možností ukládání pro EMF/WMF

Upravte možnosti ukládání a definujte požadovaný formát metasouboru. Zde vybereme `HtmlMetafileFormat.Emf`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    MetafileFormat = HtmlMetafileFormat.Emf
};
```

## Krok 6: Uložte dokument

Uložte dokument s použitím zadaných možností uložení.

```csharp
document.Save(dataDir + "ConvertedDocument.emf", saveOptions);
```

Výsledný soubor bude obsahovat obsah SVG převedený do formátu EMF.

## Závěr

Tento tutoriál ukázal, jak převést obrázky SVG do formátů EMF nebo WMF pomocí Aspose.Words pro .NET. Dodržením těchto kroků můžete zlepšit kompatibilitu a vizuální věrnost vašich dokumentů Word. Ať už automatizujete vytváření dokumentů nebo připravujete vysoce kvalitní zprávy, tato metoda zaručuje bezproblémové výsledky.

## Často kladené otázky

### Mohu tuto metodu použít pro dávkové zpracování více SVG obrázků?
Ano, můžete iterovat přes více HTML souborů obsahujících SVG a aplikovat stejný proces ve smyčce.

### Jaký je rozdíl mezi EMF a WMF?
EMF je vylepšená verze WMF, která nabízí lepší podporu pro složitou grafiku a větší velikosti dat.

### Je Aspose.Words kompatibilní s .NET Core?
Ano, Aspose.Words pro .NET podporuje .NET Core a .NET 5/6, takže je vhodný pro moderní multiplatformní aplikace.

### Mohu ve výstupu zachovat původní formát SVG?
Ne, tato metoda konkrétně převádí SVG na EMF/WMF. Původní SVG však můžete zachovat jeho vložením přímo do dokumentu bez převodu.

### Kde si mohu stáhnout bezplatnou zkušební verzi Aspose.Words?
Zkušební verzi zdarma si můžete stáhnout z [Stránka s vydáním Aspose](https://releases.aspose.com/).