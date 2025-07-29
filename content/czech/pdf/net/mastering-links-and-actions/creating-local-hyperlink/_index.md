---
"description": "Zjistěte, jak vylepšit navigaci v dokumentech PDF vytvořením lokálních hypertextových odkazů pomocí Aspose.PDF pro .NET. Tento podrobný návod vás provede celým procesem."
"linktitle": "Vytvoření lokálního hypertextového odkazu v souboru PDF"
"second_title": "Aspose.PDF pro referenční příručku k .NET API"
"title": "Vytvoření lokálního hypertextového odkazu v souboru PDF"
"url": "/cs/pdf/net/mastering-links-and-actions/creating-local-hyperlink/"
"weight": 40
---

## Zavedení

V této příručce vás provedeme procesem vytváření lokálních hypertextových odkazů v souboru PDF pomocí Aspose.PDF pro .NET. Každý krok si jasně rozebereme, abyste i v případě, že s manipulací s PDF začínáte, mohli bez námahy sledovat postup.

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte následující:

1. Visual Studio: Stáhněte si ho z [Webové stránky Visual Studia](https://visualstudio.microsoft.com/).
2. Aspose.PDF pro .NET: Stáhněte si knihovnu přes [Webové stránky Aspose](https://releases.aspose.com/pdf/net/)Tato knihovna poskytuje bohatou sadu funkcí pro manipulaci s PDF.
3. Základní znalost C#: Znalost programování v C# vám pomůže, ale nebojte se, kód vám vysvětlíme řádek po řádku.
4. .NET Framework: Ujistěte se, že máte na svém počítači nainstalovaný .NET Framework. Zkontrolujte požadavky v souboru Aspose.PDF. [dokumentace](https://reference.aspose.com/pdf/net/).

S těmito předpoklady jste připraveni naučit se, jak vytvářet lokální hypertextové odkazy ve vašich PDF dokumentech!

## Import požadovaných balíčků

Nyní, když máte vše nastavené, je čas importovat potřebné balíčky do vašeho projektu v C#.

### Otevřete svůj projekt

Otevřete stávající projekt .NET nebo vytvořte nový ve Visual Studiu. Pokud začínáte znovu, vyberte na úvodní obrazovce možnost „Vytvořit nový projekt“.

### Přidat odkaz na Aspose.PDF

Průzkumníku řešení klikněte pravým tlačítkem myši na „Závislosti“ ve složce projektu. Vyberte „Spravovat balíčky NuGet“ a vyhledejte `Aspose.PDF`a nainstalujte nejnovější dostupnou verzi. Tím získáte všechny nástroje, které potřebujete pro vytváření a manipulaci s PDF soubory.

### Importovat jmenné prostory

Na začátek souboru .cs přidejte pomocí direktiv následující:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Tyto direktivy vám umožňují bezproblémový přístup k funkcím knihovny.

Pojďme si rozebrat proces vytváření lokálních hypertextových odkazů do jednoduchých kroků.

## Krok 1: Nastavení instance dokumentu

Vytvořte novou instanci `Document` třída, která představuje soubor PDF, se kterým budete pracovat.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Nastavení adresáře dokumentů
Document doc = new Document(); // Vytvořit instanci dokumentu
```

Nahradit `"YOUR_DOCUMENT_DIRECTORY"` se skutečnou cestou ve vašem systému, kam bude PDF uložen.

## Krok 2: Přidání stránky do dokumentu

Dále přidejte stránku do dokumentu PDF.

```csharp
Page page = doc.Pages.Add(); // Přidat novou stránku
```

Tento řádek přidá do dokumentu novou stránku, na kterou bude umístěn veškerý váš obsah.

## Krok 3: Vytvořte textový fragment

Nyní si vytvořme text, který bude fungovat jako klikatelný odkaz.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7"); // Vytvořte fragment textu
```

Tento `TextFragment` zobrazí text, na který mohou uživatelé kliknout.

## Krok 4: Vytvořte lokální hypertextový odkaz

Nyní vytvořte lokální hypertextový odkaz, který bude odkazovat na stránku 7.

```csharp
LocalHyperlink link = new LocalHyperlink(); // Vytvořit lokální hypertextový odkaz
link.TargetPageNumber = 7; // Nastavte cílovou stránku pro odkaz
text.Hyperlink = link; // Nastavení hypertextového odkazu pro textový fragment
```

Ten/Ta/To `LocalHyperlink` třída umožňuje zadat číslo cílové stránky pro hypertextový odkaz.

## Krok 5: Přidání fragmentu textu na stránku

Přidejte klikatelný text na stránku, kterou jste vytvořili.

```csharp
page.Paragraphs.Add(text); // Přidejte fragment textu na stránku
```

Tento řádek přidá váš text do kolekce odstavců na stránce.

## Krok 6: Vytvořte další textový fragment (volitelné)

Přidejme další hypertextový odkaz pro navigaci zpět na stránku 1.

```csharp
TextFragment textBack = new TextFragment("Link to page 1"); // Vytvořte nový textový fragment
textBack.IsInNewPage = true; // Uveďte, že by to mělo být na nové stránce
```

## Krok 7: Nastavení druhého lokálního hypertextového odkazu

Vytvořte další lokální hypertextový odkaz pro stránku 1.

```csharp
Aspose.Pdf.LocalHyperlink linkBack = new Aspose.Pdf.LocalHyperlink(); // Vytvořit další lokální hypertextový odkaz
linkBack.TargetPageNumber = 1; // Nastavit cílovou stránku pro druhý hypertextový odkaz
textBack.Hyperlink = linkBack; // Nastavení hypertextového odkazu pro druhý textový fragment
```

## Krok 8: Přidání druhého textového fragmentu na novou stránku

Přidejte druhý textový fragment na jeho stránku.

```csharp
Page newPage = doc.Pages.Add(); // Přidat novou stránku pro druhý odkaz
newPage.Paragraphs.Add(textBack); // Přidejte fragment textu na novou stránku
```

## Krok 9: Uložte dokument

Nakonec dokument uložte.

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Zadejte název výstupního souboru
doc.Save(dataDir); // Uložit aktualizovaný dokument
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```

Tento řádek kombinuje cestu k adresáři s názvem souboru a `Save()` Metoda uloží váš dokument.

## Závěr

Vytváření lokálních hypertextových odkazů v souborech PDF pomocí Aspose.PDF pro .NET je praktická funkce, která vylepšuje navigaci a uživatelský zážitek. Nyní máte znalosti, které pomohou čtenáře přímo k informacím, které potřebují, a vaše PDF soubory tak budou interaktivnější a uživatelsky přívětivější.

## Často kladené otázky

### Co je Aspose.PDF pro .NET?
Aspose.PDF pro .NET je knihovna, která umožňuje vývojářům programově vytvářet, manipulovat a převádět PDF dokumenty pomocí frameworku .NET.

### Mohu vytvářet hypertextové odkazy na externí webové stránky?
Ano, Aspose.PDF také podporuje vytváření hypertextových odkazů na externí URL adresy kromě lokálních hypertextových odkazů v PDF.

### Existuje bezplatná zkušební verze pro Aspose.PDF?
Rozhodně! Bezplatnou zkušební verzi si můžete vyzkoudat zde [Webové stránky Aspose](https://releases.aspose.com/).

### Jaké programovací jazyky Aspose podporuje?
Aspose nabízí knihovny pro různé programovací jazyky, včetně Javy, C++ a Pythonu, mimo jiné.

### Jak získám podporu pro produkty Aspose?
Podporu můžete vyhledat prostřednictvím [Fórum Aspose](https://forum.aspose.com/c/pdf/10).