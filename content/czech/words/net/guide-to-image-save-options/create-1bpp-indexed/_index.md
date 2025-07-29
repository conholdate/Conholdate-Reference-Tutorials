---
"description": "Tato příručka poskytuje podrobné pokyny a ukázkový kód, které vám pomohou efektivně vytvářet indexované obrazy 1Bpp pro archivaci, tisk nebo pro účely úspory místa."
"linktitle": "Vytvořit indexované 1Bpp"
"second_title": "Rozhraní API pro zpracování dokumentů Aspose.Words"
"title": "Vytvořit indexované 1Bpp"
"url": "/cs/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## Zavedení

Potřebovali jste někdy převést dokument Wordu do černobílého obrázku? Ať už jde o digitální archivaci, tisk nebo jen o úsporu místa, převod dokumentů do obrázků s indexem 1Bpp může být neuvěřitelně užitečný. V této příručce si ukážeme jednoduchý způsob, jak toho dosáhnout pomocí Aspose.Words pro .NET. Pojďme začít!

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte následující:

- Aspose.Words pro .NET: Stáhněte a nainstalujte knihovnu z [zde](https://releases.aspose.com/words/net/).
- Vývojové prostředí .NET: I když je Visual Studio oblíbenou volbou, bude fungovat jakékoli IDE, které podporuje .NET.
- Základní znalost C#: Znalost C# vám pomůže, ale budeme se snažit věci zjednodušit.
- Ukázkový dokument Wordu: Mějte připravený dokument k převodu.

## Krok 1: Importujte potřebné jmenné prostory

Pro použití Aspose.Words je nutné importovat příslušné jmenné prostory. To je nezbytné pro přístup ke třídám a metodám potřebným pro manipulaci s dokumenty.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 2: Nastavení adresáře dokumentů

Zadejte cestu k adresáři, kde je uložen dokument aplikace Word a kam chcete uložit převedený obrázek.

```csharp
// Cesta k adresáři s dokumenty
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Krok 3: Načtěte dokument Wordu

Vložte dokument Wordu do `Aspose.Words.Document` objekt. Tento objekt umožňuje programově manipulovat s dokumentem.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 4: Konfigurace možností ukládání obrázků

Dále nastavte `ImageSaveOptions` definovat, jak bude dokument uložen jako obrázek. Nakonfigurujeme ho pro ukládání ve formátu PNG s indexovaným barevným režimem 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // Převést pouze první stránku
    ImageColorMode = ImageColorMode.BlackAndWhite, // Nastaveno na černobílou
    PixelFormat = ImagePixelFormat.Format1bppIndexed // Použijte indexovaný formát 1Bpp
};
```

- SaveFormat.Png: Určuje, že výstupní formát bude PNG.
- PageSet(1): Označuje, že bude převedena pouze první stránka dokumentu.
- ImageColorMode.BlackAndWhite: Zajistí, že obrázek bude černobílý.
- ImagePixelFormat.Format1bppIndexed: Nastaví formát pixelů na indexovaný 1Bpp, optimalizuje tak prostor.

## Krok 5: Uložte dokument jako obrázek

Nakonec použijte `Save` metoda `Document` objekt pro uložení převedeného obrázku.

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## Závěr

Gratulujeme! Úspěšně jste převedli dokument Wordu na obrázek indexovaný s rozlišením 1Bpp pomocí nástroje Aspose.Words pro .NET. Tato metoda je nejen efektivní, ale také vám pomůže vytvářet obrázky s vysokým kontrastem vhodné pro různé aplikace. Neváhejte tuto funkci integrovat do svých projektů. Přejeme vám příjemné programování!

## Často kladené otázky

### Co je to 1Bpp indexovaný obrázek?
Obrázek indexovaný 1Bpp (1 bit na pixel) je černobílý obrazový formát, kde každý pixel je reprezentován jedním bitem, buď 0 nebo 1. Tento formát je velmi prostorově efektivní, takže je ideální pro archivaci.

### Mohu převést více stránek dokumentu Word najednou?
Ano! Jednoduše upravte `PageSet` nemovitost v `ImageSaveOptions` zahrnout více stránek nebo nastavit převod celého dokumentu.

### Potřebuji licenci k používání Aspose.Words pro .NET?
Ano, pro plnou funkčnost je vyžadována licence. Můžete si ji pořídit [dočasná licence zde](https://purchase.aspose.com/temporary-license/).

### Do jakých dalších formátů obrázků mohu převést dokument Word?
Aspose.Words podporuje různé formáty, včetně JPEG, BMP a TIFF. Stačí změnit `SaveFormat` v `ImageSaveOptions` do vámi požadovaného formátu.

### Kde najdu další dokumentaci k Aspose.Words pro .NET?
Pro úplnou dokumentaci navštivte [Dokumentace k Aspose.Words pro .NET](https://reference.aspose.com/words/net/).