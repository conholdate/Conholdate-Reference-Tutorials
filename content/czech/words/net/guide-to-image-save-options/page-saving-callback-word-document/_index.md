---
"description": "Naučte se, jak snadno převést každou stránku dokumentu Word na jednotlivé obrázky PNG pomocí Aspose.Words pro .NET. Tato příručka poskytuje podrobné pokyny, včetně příkladů kódu."
"linktitle": "Zpětné volání ukládání stránky v dokumentech Word"
"second_title": "Rozhraní API pro zpracování dokumentů Aspose.Words"
"title": "Zpětné volání ukládání stránky v dokumentech Word"
"url": "/cs/words/net/guide-to-image-save-options/page-saving-callback-word-document/"
"weight": 10
---

## Zavedení

Potřebovali jste někdy převést každou stránku dokumentu Word na jednotlivé obrázky? Ať už chcete vytvořit miniatury pro náhled nebo rozdělit dlouhou zprávu na srozumitelné vizuály, Aspose.Words pro .NET tento úkol zjednodušuje a zefektivňuje. V této příručce vás provedeme procesem nastavení zpětného volání pro ukládání stránky, které uloží každou stránku vašeho dokumentu jako obrázek PNG. Pojďme na to!

## Předpoklady

Než se ponoříte, ujistěte se, že máte následující:

1. Aspose.Words pro .NET: Stáhněte si a nainstalujte z [zde](https://releases.aspose.com/words/net/).
2. Visual Studio: Fungovat bude jakákoli verze, ale v této příručce budeme používat Visual Studio 2019.
3. Základní znalost C#: Znalost C# vám pomůže plynule se orientovat.

## Krok 1: Importujte potřebné jmenné prostory

Nejprve musíme importovat požadované jmenné prostory. To nám umožní přístup k potřebným třídám a metodám, aniž bychom museli pokaždé zadávat celý jmenný prostor.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 2: Definujte adresář dokumentů

Dále nastavte cestu k adresáři s dokumenty. Zde se nachází váš vstupní dokument Wordu a kam se budou ukládat výstupní obrázky.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Vložte dokument

Nyní načtěme dokument, který chcete zpracovat. Ujistěte se, že se váš dokument s názvem „Rendering.docx“ nachází v zadaném adresáři.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 4: Konfigurace možností ukládání obrázků

Nastavíme možnosti pro ukládání obrázků a určíme, že chceme stránky ukládat jako soubory PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

Zde, `PageSet` definuje rozsah stránek, které se mají uložit, a `PageSavingCallback` odkazuje na naši vlastní třídu zpětného volání.

## Krok 5: Implementace zpětného volání pro ukládání stránky

Nyní musíme implementovat třídu zpětného volání, která se stará o to, jak se každá stránka ukládá.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

Tato třída implementuje `IPageSavingCallback` rozhraní. V `PageSaving` metodou určíme vzor pojmenování pro každou uloženou stránku.

## Krok 6: Uložte dokument jako obrázky

Nakonec dokument uložíme s použitím nakonfigurovaných možností.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Závěr

Gratulujeme! Úspěšně jste nastavili zpětné volání pro ukládání stránek, které uloží každou stránku dokumentu Word jako samostatný obrázek PNG pomocí Aspose.Words pro .NET. Tato technika je neuvěřitelně užitečná pro různé aplikace, od vytváření náhledů stránek až po generování jednotlivých obrázků stránek pro sestavy.

## Často kladené otázky

### Mohu ukládat stránky v jiných formátech než PNG?
Ano! Stránky můžete ukládat ve formátech jako JPEG, BMP a TIFF změnou `SaveFormat` v `ImageSaveOptions`.

### Jak mohu uložit pouze určité stránky?
Chcete-li uložit konkrétní stránky, upravte `PageSet` parametr v `ImageSaveOptions` zahrnout pouze požadované stránky.

### Je možné si přizpůsobit kvalitu obrazu?
Rozhodně! Kvalitu výstupního obrazu můžete ovládat nastavením vlastností, jako je `ImageSaveOptions.JpegQuality`.

### Jak mohu efektivně zpracovávat velké dokumenty?
U velkých dokumentů zvažte dávkové zpracování stránek, abyste efektivně spravovali využití paměti.

### Kde najdu více informací o Aspose.Words pro .NET?
Pro komplexní návody a příklady se podívejte na [Dokumentace k Aspose.Words](https://reference.aspose.com/words/net/).