---
"description": "Naučte se, jak snadno převádět soubory DGN do PDF pomocí výkonné knihovny Aspose.CAD pro .NET. Tato podrobná příručka je určena pro vývojáře všech úrovní."
"linktitle": "Převod DGN do PDF v Aspose.CAD pro .NET"
"second_title": "Aspose.CAD .NET - formát souborů CAD a BIM"
"title": "Převod DGN do PDF v Aspose.CAD pro .NET"
"url": "/cs/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## Zavedení

Orientace ve světě CAD souborů může být náročná, ale s Aspose.CAD pro .NET mohou vývojáři snadno manipulovat s různými CAD formáty a převádět je. Jednou z běžných potřeb je převod DGN souborů do PDF, který si v tomto tutoriálu krok za krokem probereme.

## Předpoklady

Abyste mohli pokračovat, ujistěte se, že máte následující:

- Základní znalost C# a .NET frameworku.
- Je nainstalována knihovna Aspose.CAD pro .NET. Můžete si ji stáhnout. [zde](https://releases.aspose.com/cad/net/).
- Ukázkový soubor DGN (např. Nikon_D90_Camera.dgn). 

## Krok 1: Importujte požadované jmenné prostory

Začněte importem příslušných jmenných prostorů do vašeho projektu C#:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Krok 2: Načtení souboru DGN

Zadejte adresář pro váš DGN soubor a načtěte jej pomocí následujícího kódu:

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // Zde proběhne další zpracování...
}
```

## Krok 3: Konfigurace možností rastrování

Dále nastavte možnosti rastrování, abyste definovali, jak bude váš DGN vykreslen v PDF:

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // Upravte šířku dle potřeby
    PageHeight = 300, // Upravte výšku dle potřeby
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## Krok 4: Možnosti vytvoření PDF

Definujte možnosti PDF a integrujte dříve nakonfigurovaná nastavení rasterizace:

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Krok 5: Uložení DGN jako PDF

Nakonec uložte soubor DGN jako PDF pomocí nakonfigurovaných možností:

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## Závěr

Gratulujeme! Úspěšně jste převedli soubor DGN do formátu PDF pomocí programu Aspose.CAD pro .NET. Tento jednoduchý tutoriál vás provedl načtením souboru DGN, nastavením možností rastrování a uložením výstupu ve formátu PDF.

## Často kladené otázky

### Potřebuji pro používání Aspose.CAD předchozí znalosti CADu?  
Rozhodně! Aspose.CAD je navržen tak, aby zjednodušil složité CAD úlohy a byl přístupný všem vývojářům bez ohledu na jejich znalosti CADu.

### Kde najdu další zdroje a dokumentaci k Aspose.CAD?  
Komplexní průvodce a příklady si můžete prohlédnout v [Dokumentace k Aspose.CAD](https://reference.aspose.com/cad/net/).

### Je k dispozici bezplatná zkušební verze pro Aspose.CAD?  
Ano, lze získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.CAD?  
Můžete požádat o dočasné licence [zde](https://purchase.conholdate.com/temporary-license/).

### Potřebujete pomoc nebo máte otázky?  
Zapojte se do konverzace v [Fórum Aspose.CAD](https://forum.aspose.com/c/cad/19) pro podporu a dotazy komunity.