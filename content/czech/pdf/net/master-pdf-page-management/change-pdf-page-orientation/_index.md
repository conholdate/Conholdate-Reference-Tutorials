---
"description": "Zjistěte, jak snadno upravit orientaci stránek PDF souborů pomocí Aspose.PDF pro .NET. Tato podrobná příručka poskytuje jasné pokyny k načítání, otáčení a ukládání dokumentů."
"linktitle": "Změna orientace stránky PDF"
"second_title": "Aspose.PDF pro referenční příručku k .NET API"
"title": "Změna orientace stránky PDF"
"url": "/cs/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Zavedení

Setkali jste se někdy se souborem PDF, který má úplně špatnou orientaci stránky? Ať už se jedná o dokument, který byl nesprávně naskenován, nebo o dokument, který jednoduše potřebuje jiné rozvržení, úprava orientace může mít obrovský význam. Naštěstí Aspose.PDF pro .NET nabízí výkonný a uživatelsky přívětivý způsob manipulace se soubory PDF, včetně změny orientace stránek. V této příručce vás krok za krokem provedeme celým procesem, ať už chcete přepnout z orientace na výšku na šířku nebo naopak.

## Předpoklady

Než se ponoříme do detailů, ujistěte se, že máte připraveno následující:

- Aspose.PDF pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF. Pokud jste tak ještě neučinili, můžete [stáhněte si to zde](https://releases.aspose.com/pdf/net/).
- Vývojové prostředí .NET: Pro vývoj v .NET můžete použít Visual Studio, JetBrains Rider nebo jakékoli jiné IDE, které preferujete.
- Základní znalost C#: Znalost C# vám pomůže snáze se orientovat.
- Soubor PDF: Mějte připravený vzorový soubor PDF pro testování. Můžete si ho vytvořit nebo si vzorek stáhnout online.

Pokud s tím teprve začínáte, zvažte vyzkoušení Aspose.PDF s [bezplatná dočasná licence](https://purchase.aspose.com/temporary-license/) než se rozhodnete [koupit plnou verzi](https://purchase.aspose.com/buy).

## Importovat jmenné prostory

Pro manipulaci se stránkami PDF je nejprve nutné importovat potřebné jmenné prostory do projektu C#. Na začátek souboru s kódem přidejte následující řádky:

```csharp
using System.IO;
using Aspose.Pdf;
```

Teď, když máme vše nastavené, pojďme se do toho pustit!

## Krok 1: Načtěte dokument PDF

Prvním krokem je načtení PDF souboru, který chcete upravit. Použijte `Document` třída z oboru názvů Aspose.PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Nezapomeňte vyměnit `"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu PDF souboru.

## Krok 2: Procházení jednotlivých stránek

Dále projdeme každou stránku v dokumentu PDF. To nám umožní aplikovat změnu orientace na všechny stránky:

```csharp
foreach (Page page in doc.Pages)
{
    // Manipulovat s každou stránkou
}
```

## Krok 3: Přístup k MediaBoxu stránky

Každá stránka PDF má `MediaBox` která definuje jeho hranice. Potřebujeme k tomu přístup, abychom zkontrolovali aktuální orientaci a provedli úpravy:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

Ten/Ta/To `MediaBox` poskytuje rozměry stránky, včetně šířky a výšky.

## Krok 4: Prohoďte šířku a výšku

Chcete-li změnit orientaci stránky, prohodíme hodnoty šířky a výšky. Tato úprava změní rozměry stránky:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Zde vypočítáme nové rozměry a přemístíme levý dolní roh (`LLY`) odpovídajícím způsobem.

## Krok 5: Aktualizace MediaBoxu a CropBoxu

Nyní, když máme nové rozměry, aplikujeme tyto změny na `MediaBox` a `CropBox` aby se stránka zobrazovala správně:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Krok 6: Otočení stránky

Pro dokončení změny orientace stránku otočíme. S Aspose.PDF je to jednoduché:

```csharp
page.Rotate = Rotation.on90; // Otočit o 90 stupňů
```

Tato čára efektivně otočí stránku do požadované orientace.

## Krok 7: Uložení výstupního PDF

Po úpravě orientace všech stránek uložte aktualizovaný dokument do nového souboru:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Nezapomeňte zadat nový název souboru, abyste zabránili přepsání původního dokumentu.

## Závěr

A je to! Změna orientace stránky PDF souboru pomocí Aspose.PDF pro .NET je jednoduchý proces. Načtením dokumentu, procházením stránek, aktualizací MediaBoxu a uložením souboru můžete snadno upravit rozvržení podle svých potřeb. Ať už opravujete špatně naskenovaný dokument nebo formátujete stránky pro prezentaci, tato příručka by vám měla pomoci efektivně zvládnout tuto práci.

## Často kladené otázky

### Mohu v PDF otočit pouze určité stránky místo všech?  
Ano, smyčku můžete upravit tak, aby cílila na konkrétní stránky podle jejich indexu, místo aby iterovala všemi stránkami.

### Co je `MediaBox`?  
Ten/Ta/To `MediaBox` definuje velikost a tvar stránky v souboru PDF a určuje, kam bude obsah umístěn.

### Funguje Aspose.PDF pro .NET s jinými formáty souborů?  
Ano, Aspose.PDF dokáže zpracovat různé formáty souborů, včetně HTML, XML, XPS a dalších.

### Existuje bezplatná verze Aspose.PDF pro .NET?  
Ano, můžete začít s [bezplatná zkušební verze](https://releases.aspose.com/) nebo požádejte o [dočasná licence](https://purchase.aspose.com/temporary-license/).

### Mohu po uložení změny vrátit zpět?  
Jakmile dokument uložíte, změny jsou trvalé. Doporučuje se pracovat na kopii nebo si ponechat zálohu původního souboru.