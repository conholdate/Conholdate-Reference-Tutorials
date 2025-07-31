---
"description": "Naučte se, jak efektivně převádět CAD rozvržení do různých rastrových obrazových formátů pomocí Aspose.CAD pro .NET. Tato komplexní příručka vás provede celým procesem pomocí srozumitelného kódu."
"linktitle": "Export CAD do rastrového obrázku"
"second_title": "Aspose.CAD .NET - formát souborů CAD a BIM"
"title": "Export CAD do rastrového obrázku - konverze pomocí Aspose.CAD pro .NET"
"url": "/cs/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## Zavedení

Hledáte způsob, jak bez námahy převést CAD rozvržení do rastrových obrazových formátů pomocí Aspose.CAD pro .NET? Tato podrobná příručka je navržena tak, aby vám pomohla zorientovat se v celém procesu, a obsahuje stručné úryvky kódu pro hladký zážitek. Ať už jste zkušený vývojář, nebo teprve začínáte, tento tutoriál poskytuje cenné informace pro všechny úrovně dovedností.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Knihovna Aspose.CAD pro .NET: Stáhněte a nainstalujte knihovnu z [Webové stránky Aspose.CAD](https://releases.aspose.com/cad/net/).
- Soubor s výkresem CAD: Mějte svůj soubor s výkresem CAD (např. `conic_pyramid.dxf`) připraveno k převodu.

## Importovat požadované jmenné prostory

Ve vašem projektu .NET budete muset importovat potřebné jmenné prostory pro použití funkcí Aspose.CAD. Na začátek kódu přidejte následující:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Krok 1: Načtěte výkres CAD

Nejprve zadejte adresář a načtěte soubor CAD do instance obrázku:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// Načtení výkresu CAD
using (var image = Image.Load(sourceFilePath))
{
    // Pokračujte k dalším krokům
}
```

## Krok 2: Vytvořte možnosti rastrování

Dále nastavte možnosti rasterizace a definujte požadované rozměry výstupního obrázku:

```csharp
// Inicializovat možnosti rastrování Cad
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## Krok 3: Určení vrstev pro převod

Pokud chcete převést konkrétní vrstvy, přidejte je do možností rastrování:

```csharp
// Zadejte vrstvu, kterou chcete převést
rasterizationOptions.Layers = new [] { "LayerA" };
```

## Krok 4: Nastavení možností exportu JPEG

Nyní vytvořte možnosti pro formát obrázku, do kterého chcete exportovat (v tomto případě JPEG):

```csharp
// Vytvořit JPEGOptions pro export
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Krok 5: Export do formátu JPEG

Nakonec uložte převedený obrázek:

```csharp
// Definujte cestu k výstupnímu souboru a uložte obrázek
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## Další funkce: Převést všechny vrstvy

Chcete-li převést všechny vrstvy ve vašem CAD výkresu, můžete implementovat metodu podobnou této:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // Procházejte vrstvami a ukládejte každou jako samostatný soubor JPEG
    // Váš implementační kód zde
}
```

## Závěr

Gratulujeme! Naučili jste se, jak efektivně převádět CAD rozvržení do rastrových obrazových formátů pomocí Aspose.CAD pro .NET. Tato příručka nabízí přímočarý přístup vhodný pro vývojáře, kteří usilují o efektivní CAD konverze.

## Často kladené otázky

### Mohu exportovat do různých obrazových formátů?

Rozhodně! Jednoduše vyměňte `JpegOptions` s dalšími možnostmi formátování, jako například `PngOptions` nebo `BmpOptions`, v závislosti na vašich potřebách.

### Je k dispozici zkušební verze?

Ano, zkušební verzi si můžete stáhnout a prozkoumat funkce podle následujícího postupu [odkaz](https://releases.aspose.com/cad/net/).

### Kde najdu podporu pro Aspose.CAD?

Pro podporu komunity se podívejte na Aspose.CAD [forum](https://forum.aspose.com/c/cad/19), nebo zvažte zakoupení licence pro specializovanější asistenci.

### Jsou možné dočasné licence?

Ano, dočasné licence jsou k dispozici; můžete si o jednu požádat [zde](https://purchase.conholdate.com/temporary-license/).

### Kde mohu získat přístup k podrobné dokumentaci?

Navštivte komplexní dokumentaci [zde](https://reference.aspose.com/cad/net/) pro více informací.