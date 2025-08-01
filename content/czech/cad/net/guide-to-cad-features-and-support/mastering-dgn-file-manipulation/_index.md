---
"description": "Naučte se, jak načítat soubory DGN, procházet jejich prvky, spravovat 2D i 3D entity a exportovat je jako rastrové obrázky – to vše s využitím výkonných funkcí knihovny Aspose.CAD."
"linktitle": "Zvládnutí manipulace se soubory DGN"
"second_title": "Aspose.CAD .NET - formát souborů CAD a BIM"
"title": "Zvládnutí manipulace s DGN soubory pomocí Aspose.CAD v .NET"
"url": "/cs/cad/net/guide-to-cad-features-and-support/mastering-dgn-file-manipulation/"
"weight": 18
---

## Zavedení

Jste vývojář v .NET a toužíte po integraci souborů DGN do svých aplikací? Aspose.CAD pro .NET nabízí výkonnou knihovnu navrženou speciálně pro práci s formáty souborů DGN. V tomto tutoriálu se podíváme na to, jak efektivně pracovat se soubory DGN, včetně podporovaných prvků, a jak s nimi manipulovat ve vašich .NET projektech.

## Předpoklady

Než začnete, ujistěte se, že máte následující nastavení:

- Základní znalost programování v .NET: Znalost C# nebo VB.NET bude výhodou.
- Visual Studio: Nainstalováno na vašem počítači pro vývoj projektů.
- Knihovna Aspose.CAD pro .NET: Stáhněte si ji z [Aspose.CAD](https://releases.aspose.com/cad/net/).

## Krok 1: Importujte potřebné jmenné prostory

Chcete-li využít funkce Aspose.CAD, začněte importem požadovaných jmenných prostorů do vašeho projektu.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
using Aspose.CAD.FileFormats.Dgn;
using Aspose.CAD.FileFormats.Dgn.DgnElements;
```

## Krok 2: Načtěte soubor DGN

Začněte načtením existujícího souboru DGN do vaší aplikace. To se provede vytvořením instance `DgnImage`.

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage dgnImage = (DgnImage)Image.Load(sourceFilePath))
{
    // Pokračujte zde se svou logikou
}
```

## Krok 3: Iterace prvků DGN

Jakmile je soubor DGN načten, můžete iterovat mezi jeho prvky. Aspose.CAD nabízí pro vaši manipulaci různé typy prvků DGN.

```csharp
foreach (DgnDrawingElementBase element in dgnImage.Elements)
{
    // Zpracovat každý prvek
}
```

## Krok 4: Zpracování 2D a 3D entit

Můžete rozlišovat mezi 2D a 3D DGN prvky. Níže je uveden návod, jak s nimi efektivně pracovat:

### Zpracování 2D entit

Dříve podporované 2D entity můžete spravovat pomocí bloku switch-case.

```csharp
switch (element.Metadata.Type)
{
    case DgnElementType.Line:
    case DgnElementType.Ellipse:
    case DgnElementType.Curve:
        // Zde přidejte svou logiku zpracování 
        break;
}
```

### Zpracování 3D entit

Podobně zacházejte s 3D entitami takto:

```csharp
switch (element.Metadata.Type)
{
    case DgnElementType.SolidHeader3D:
    case DgnElementType.Cone:
    case DgnElementType.CellHeader:
        // Zde přidejte svou logiku zpracování 
        break;
}
```

## Krok 5: Export souboru DGN

Po manipulaci s prvky DGN můžete soubor exportovat jako rastrový obrázek. Toho lze snadno dosáhnout pomocí programu Aspose.CAD.

```csharp
string outputFilePath = myDir + "Exported_Image.png"; // Definujte výstupní cestu
dgnImage.Save(outputFilePath, new Aspose.CAD.ImageOptions.PngOptions());
Console.WriteLine($"\nThe DGN file exported successfully to raster image.\nFile saved at {outputFilePath}");
```

## Závěr

V tomto tutoriálu jsme se naučili, jak používat Aspose.CAD pro .NET k efektivní správě DGN souborů. Dodržováním popsaných kroků můžete bez námahy pracovat s 2D i 3D DGN prvky a exportovat je jako rastrové obrázky. Tato výkonná knihovna umožňuje bezproblémovou integraci zpracování DGN do vašich .NET aplikací a rozšiřuje tak možnosti vašich projektů.

## Často kladené otázky

### Kde najdu dokumentaci k Aspose.CAD pro .NET?

Komplexní dokumentace je k dispozici [zde](https://reference.aspose.com/cad/net/).

### Jak si stáhnu Aspose.CAD pro .NET?

Nejnovější verzi knihovny si můžete stáhnout [zde](https://releases.aspose.com/cad/net/).

### Je k dispozici bezplatná zkušební verze Aspose.CAD pro .NET?

Ano, je k dispozici bezplatná zkušební verze [zde](https://releases.aspose.com/).

### Jak mohu získat dočasné licence pro Aspose.CAD pro .NET?

Můžete požádat o dočasné licence [zde](https://purchase.conholdate.com/temporary-license/).

### Potřebujete pomoc nebo máte otázky?

Pro podporu nebo s dotazy navštivte komunitu Aspose.CAD. [fórum podpory](https://forum.aspose.com/c/cad/19).