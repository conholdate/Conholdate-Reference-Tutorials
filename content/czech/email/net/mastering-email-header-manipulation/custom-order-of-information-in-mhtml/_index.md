---
"description": "V tomto podrobném návodu se naučíte, jak definovat vlastní pořadí informací v MHTML pomocí Aspose.Email pro .NET."
"linktitle": "Vlastní řazení informací v MHTML s Aspose.Email"
"second_title": "Rozhraní API pro zpracování e-mailů Aspose.Email v .NET"
"title": "Vlastní řazení informací v MHTML s Aspose.Email"
"url": "/cs/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## Zavedení

Vytváření bohatých e-mailových formátů může výrazně zlepšit komunikaci, zejména při exportu e-mailů do různých formátů souborů, jako je MHTML. Aspose.Email pro .NET poskytuje vývojářům výkonnou sadu nástrojů pro manipulaci s e-maily, která zahrnuje definování vlastního pořadí zobrazení informací při exportu do MHTML. V této příručce si rozebereme kroky potřebné k dosažení tohoto cíle, což usnadní sledování, ať už jste zkušený vývojář nebo teprve začínáte. Tak pojďme rovnou na to!

## Předpoklady

Než se pustíte do definování vlastního pořadí informací v MHTML, je třeba splnit několik předpokladů:

1. Vývojové prostředí .NET: Ujistěte se, že máte nastavené vývojové prostředí .NET. Můžete použít Visual Studio, Visual Studio Code nebo jakékoli jiné kompatibilní IDE.

2. Knihovna Aspose.Email: Musíte mít nainstalovanou knihovnu Aspose.Email pro .NET. Nejnovější verzi si můžete stáhnout z [Stránka s vydáním Aspose](https://releases.aspose.com/email/net/).

3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět kódu.

4. Ukázkový soubor e-mailu: Budete potřebovat vzorek `.eml` soubor (například `Attachments.eml`) pro účely testování.

Jakmile splníte tyto předpoklady, můžete začít s návodem!

## Importovat balíčky

Abyste mohli začít s kódem, budete muset importovat potřebné jmenné prostory z knihovny Aspose.Email. To je nezbytné pro přístup ke všem třídám a metodám potřebným pro manipulaci s e-mailovými soubory.

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

Vložte je na začátek souboru C#. Nyní jste připraveni se pustit do programování!

Nyní, když máte vše nastavené, rozdělme si tutoriál na zvládnutelné kroky.

## Krok 1: Nastavení datového adresáře

První věc, kterou je třeba udělat, je vytvořit adresář, kam budou uloženy vaše e-mailové soubory. Může to být jakákoli cesta na vašem lokálním počítači.

```csharp
string dataDir = "Your Data Directory";
```

Nahradit `"Your Data Directory"` se skutečnou cestou, kde se nachází vaše `.eml` soubor se nachází. Například pokud se váš soubor nachází v `C:\Emails`, napsali byste:

```csharp
string dataDir = @"C:\Emails\";
```

## Krok 2: Načtení e-mailové zprávy

Dále je třeba načíst `.eml` zařadit do `MailMessage` objekt. To vám umožňuje manipulovat s obsahem a metadaty e-mailu.

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

Ujistěte se, že název souboru odpovídá názvu souboru v zadaném adresáři. Pokud má váš soubor jiný název, aktualizujte jej odpovídajícím způsobem.

## Krok 3: Nastavení možností ukládání MHTML

Po načtení e-mailu je čas definovat, jak jej chcete uložit jako MHTML. Můžete začít s výchozími možnostmi.

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

Tento řádek inicializuje možnosti ukládání MHTML a připravuje půdu pro pozdější úpravu záhlaví.

## Krok 4: Uložení MHTML s výchozím pořadím

Uložme e-mail jako MHTML s použitím výchozího pořadí. To vám poskytne výchozí hodnotu pro porovnání po úpravě.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

Spusťte tento řádek a zkontrolujte zadaný adresář. Měli byste nyní vidět nový soubor MHTML s názvem `CustomOrderOfInformationInMHTML_1.mhtml`Otevřete jej a podívejte se, jak se informace zobrazují ve výchozím nastavení.

## Krok 5: Úprava pořadí záhlaví

A teď přichází ta zábavná část! Můžete určit, které hlavičky se mají zahrnout do výstupu MHTML a v jakém pořadí. Začneme s některými běžnými hlavičkami.

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

Přidáním těchto záhlaví sdělíte Aspose, jak chcete, aby se e-mail zobrazoval.

## Krok 6: Uložení MHTML s vlastním pořadím

Po úpravě záhlaví je třeba e-mail znovu uložit jako MHTML, abyste viděli, jak nové pořadí ovlivní výstup.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

Spusťte tento kód a poté otevřete `CustomOrderOfInformationInMHTML_2.mhtml`Porovnejte ho s prvním a zjistěte, jak se informace změnily v závislosti na pořadí záhlaví.

## Krok 7: Vymazat a přidat nové pořadí záhlaví

Co když chcete úplně jiné pořadí? Můžete začít znovu vymazáním stávajícího nastavení záhlaví.

```csharp
opt.RenderingHeaders.Clear();
```

Nyní je čas definovat nové pořadí záhlaví. Pokud chcete například upřednostnit přílohy a kopírovat příjemce:

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## Krok 8: Uložení MHTML s novým vlastním pořadím

Nakonec e-mail ještě jednou uložte s novým nastavením záhlaví.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

Po spuštění tohoto řádku otevřete `CustomOrderOfInformationInMHTML_3.mhtml` a zkontrolujte, jak prezentuje informace na základě vašeho nového přizpůsobení.

## Závěr

A tady to máte – jednoduchý návod, jak definovat vlastní pořadí informací v MHTML pomocí Aspose.Email pro .NET. Dodržováním těchto kroků můžete ovládat, jak jsou vaše e-maily reprezentovány ve formátu MHTML, a zajistit, aby nejdůležitější informace byly prezentovány způsobem, který vyhovuje vašim potřebám. 

## Často kladené otázky

### Co je MHTML?
MHTML je zkratka pro „MIME HTML“, což je formát archivu webových stránek, který kombinuje HTML a další zdroje, jako jsou obrázky.

### Mohu používat Aspose.Email zdarma?
Ano, Aspose nabízí vývojářům bezplatnou zkušební verzi. Najdete ji [zde](https://releases.aspose.com/).

### Co když narazím na problémy s používáním Aspose.Email?
Podporu od komunity můžete získat prostřednictvím [Fórum Aspose](https://forum.aspose.com/c/email/12/).

### Je pro Aspose.Email k dispozici dočasná licence?
Ano, můžete požádat o dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Kde si mohu koupit Aspose.Email?
Knihovnu si můžete zakoupit zde [odkaz](https://purchase.aspose.com/buy).