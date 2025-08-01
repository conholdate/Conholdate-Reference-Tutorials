---
"description": "Naučte se, jak změnit písma během konverze MHT pomocí Aspose.Email pro .NET. Pro snadné přizpůsobení postupujte podle tohoto podrobného návodu."
"linktitle": "Změna přizpůsobení písma MHT pomocí C#"
"second_title": "Rozhraní API pro zpracování e-mailů Aspose.Email v .NET"
"title": "Změna přizpůsobení písma MHT pomocí C#"
"url": "/cs/email/net/mastering-email-header-manipulation/changing-mht-font-customization/"
"weight": 11
---

## Zavedení

Ve světě webové komunikace představují soubory MHT (MHTML) praktický způsob, jak ukládat a sdílet webový obsah, včetně obrázků, odkazů a stylů. Co se ale stane, když potřebujete tyto soubory MHT vylepšit změnou písma? Díky Aspose.Email pro .NET se tento úkol stává hračkou. V tomto tutoriálu vás krok za krokem provedeme procesem změny písma během konverze MHT. Ať už vyvíjíte aplikaci, která zpracovává formátování e-mailů, nebo si chcete jen přizpůsobit dokumenty pro svou firmu, tento průvodce vám poskytne potřebné znalosti.

## Předpoklady

Než se ponoříme do kódu, měli bychom si připravit několik základních věcí:

1. Visual Studio: Pro práci na projektu v C# budete potřebovat integrované vývojové prostředí (IDE).
2. Knihovna Aspose.Email pro .NET: Ujistěte se, že máte knihovnu nainstalovanou. Můžete si ji stáhnout z [odkaz](https://releases.aspose.com/email/net/).
3. .NET Framework: Váš projekt by měl být kompatibilní s .NET Framework; obvykle fungují dobře verze .NET Core nebo novější.

Máte je seřazené? Paráda! Pojďme na to.

## Import balíčků

Nejprve se ujistěte, že je váš projekt nastaven pro použití potřebných jmenných prostorů. Na začátek souboru C# budete chtít zahrnout následující:

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Tools;
```

Tyto balíčky vám poskytnou přístup k funkcím potřebným pro práci se soubory MHT a úpravu jejich obsahu.

Nyní si rozeberme kroky spojené se změnou písma během konverze MHT.

## Krok 1: Načtěte soubor MHT

První věc, kterou musíte udělat, je načíst soubor MHT do `MailMessage` objekt. Zde můžete přistupovat k jeho obsahu a manipulovat s ním.

```csharp
MailMessage message = MailMessage.Load("input.mht", new MhtmlLoadOptions());
```

Vysvětlení: Zde, `"input.mht"` je cesta k vašemu souboru MHT. `MhtmlLoadOptions()` umožňuje nakonfigurovat způsob načítání souboru, například odlišné zpracování příloh nebo propojených zdrojů.

## Krok 2: Iterujte alternativními zobrazeními

Soubory MHT mají často více alternativních zobrazení, zejména pokud obsahují HTML. Abyste našli to, které chcete upravit, je třeba tato zobrazení procházet.

```csharp
foreach (var alternateView in message.AlternateViews)
{
    if (alternateView.ContentType.MediaType == "text/html")
    {
        var htmlView = (AlternateView)alternateView;
        var linkedResources = htmlView.LinkedResources;
```

Vysvětlení: Kontrolujete každý `AlternateView` abyste zjistili, zda je typu HTML. Pokud ano, můžete přistupovat `LinkedResources`, kde jsou obvykle uloženy všechny fonty odkazované v HTML.

## Krok 3: Identifikace a úprava písem

Nyní, když máte přístup k propojeným zdrojům, můžete identifikovat, které zdroje jsou písma, a podle potřeby je přizpůsobit.

```csharp
foreach (var linkedResource in linkedResources)
{
    if (linkedResource.ContentType.MediaType == "application/x-font-ttf")
    {
        linkedResource.ContentType.Name = "Arial";  // Změnit na požadované písmo
        linkedResource.TransferEncoding = TransferEncoding.Base64;  // Ujistěte se, že je správně kódovaný
    }
}
```

Vysvětlení: Tato smyčka kontroluje, zda je typ obsahu propojeného zdroje písmo TrueType. Pokud se shoduje, můžete změnit název písma na požadovaný název (například v tomto příkladu „Arial“). `TransferEncoding` by mělo být také nastaveno tak, aby se zajistilo správné kódování dat písma při ukládání dokumentu.

## Krok 4: Uložte aktualizovaný soubor MHT

Po úpravě písem je čas uložit upravený soubor MHT. Ujistěte se, že používáte správné možnosti ukládání, abyste zachovali integritu souboru.

```csharp
message.Save("output.mht", SaveOptions.DefaultMhtml);
```

Vysvětlení: V tomto řádku kódu `"output.mht"` je název souboru, kam chcete uložit aktualizovaný obsah. Použití `SaveOptions.DefaultMhtml` zajišťuje, že nový soubor zachová formát MHT.

## Závěr

Změna písem v souborech MHT může výrazně vylepšit vzhled a dojem z vašich dokumentů. Využitím Aspose.Email pro .NET můžete snadno načítat soubory MHT, upravovat jejich obsah a ukládat změny pomocí několika řádků kódu. Ať už pracujete na osobním projektu nebo na větší aplikaci, zvládnutí těchto dovedností může zlepšit způsob, jakým prezentujete informace.

## Často kladené otázky

### Co je formát MHT?
MHT je formát archivu webových stránek, který ukládá HTML dokumenty, obrázky a další zdroje do jednoho souboru.

### Mohu pomocí Aspose změnit další aspekty souborů MHT?
Rozhodně! Aspose.Email vám umožňuje upravovat téměř všechny aspekty souborů MHT, včetně příloh, záhlaví a dalších.

### Je Aspose.Email pro .NET zdarma?
Aspose nabízí bezplatnou zkušební verzi, ale plná verze vyžaduje licenci. Dočasnou licenci můžete získat od [zde](https://purchase.aspose.com/temporary-license/).

### Kde najdu další dokumentaci k Aspose.Email?
Komplexní dokumentaci a příklady naleznete na [Stránka s dokumentací k e-mailu Aspose](https://reference.aspose.com/email/net/).

### Co když se při používání Aspose setkám s problémy?
Pokud narazíte na jakékoli problémy, můžete se obrátit na podporu na [Fórum podpory Aspose](https://forum.aspose.com/c/email/12/).