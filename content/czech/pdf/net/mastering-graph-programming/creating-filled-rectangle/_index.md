---
"description": "Odemkněte sílu manipulace s PDF pomocí Aspose.PDF pro .NET v tomto podrobném tutoriálu. Naučte se, jak programově vytvářet vizuálně přitažlivé PDF dokumenty kreslením vyplněných obdélníků."
"linktitle": "Vytvoření vyplněného obdélníku"
"second_title": "Aspose.PDF pro referenční příručku k .NET API"
"title": "Vytvoření vyplněného obdélníku"
"url": "/cs/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## Zavedení

Chtěli jste někdy programově vytvářet vizuálně ohromující PDF soubory? Pokud ano, jste na správném místě! V tomto tutoriálu prozkoumáme Aspose.PDF pro .NET, výkonnou knihovnu, která zjednodušuje manipulaci s PDF dokumenty. Dnes se zaměříme na vytvoření vyplněného obdélníku v PDF souboru. Ať už jste zkušený vývojář, nebo teprve začínáte, tento průvodce vás provede každým krokem přátelským a poutavým způsobem. Takže, vezměte si programátorskou čepici a pojďme na to!

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte následující:

1. Visual Studio: Nainstalujte si Visual Studio na svůj počítač, protože je to vynikající IDE pro vývoj v .NET.
2. Aspose.PDF pro .NET: Stáhněte a nainstalujte knihovnu Aspose.PDF z [zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.

## Krok 1: Vytvořte nový projekt

1. Otevřete Visual Studio a vytvořte nový projekt konzolové aplikace.
2. Pojmenujte svůj projekt vhodně.

## Krok 2: Přidání odkazu na Aspose.PDF

1. Klikněte pravým tlačítkem myši na svůj projekt v Průzkumníku řešení.
2. Vyberte Spravovat balíčky NuGet.
3. Vyhledejte soubor Aspose.PDF a nainstalujte nejnovější verzi.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Teď, když máme vše nastavené, pojďme se ponořit do kódu!

## Krok 3: Nastavení adresáře dokumentů

Zadejte cestu, kam bude váš PDF soubor uložen:

```csharp
// Cesta k adresáři s dokumenty.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Nahradit `"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou na vašem počítači, kam chcete PDF uložit.

## Krok 4: Vytvoření instance dokumentu

Inicializace nového PDF dokumentu:

```csharp
// Vytvořit instanci dokumentu
Document doc = new Document();
```

## Krok 5: Přidání stránky do dokumentu

Každý PDF soubor potřebuje alespoň jednu stránku. Pojďme jednu přidat:

```csharp
// Přidat stránku do kolekce stránek souboru PDF
Page page = doc.Pages.Add();
```

## Krok 6: Vytvoření instance grafu

A `Graph` instance funguje jako plátno pro kreslení tvarů:

```csharp
// Vytvořit instanci grafu
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## Krok 7: Přidání grafu na stránku

Přiložte graf na stránku:

```csharp
// Přidat objekt grafu do kolekce odstavců instance stránky
page.Paragraphs.Add(graph);
```

## Krok 8: Vytvořte instanci obdélníku

Definujte polohu a velikost obdélníku:

```csharp
// Vytvořit instanci obdélníku
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## Krok 9: Určete barvu výplně

Vyberte barvu pro váš obdélník. V tomto příkladu použijeme červenou:

```csharp
// Zadejte barvu výplně pro objekt Graf
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Krok 10: Přidání obdélníku do grafu

Přidejte obdélník do grafu:

```csharp
// Přidat objekt obdélník do kolekce tvarů objektu Graph
graph.Shapes.Add(rect);
```

## Krok 11: Uložení dokumentu PDF

Nakonec uložte dokument do zadaného adresáře:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Uložit PDF soubor
doc.Save(dataDir);
```

## Krok 12: Potvrzovací zpráva

Vytiskněte potvrzovací zprávu pro indikaci úspěchu:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Závěr

Gratulujeme! Úspěšně jste vytvořili vyplněný obdélník v dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Tato výkonná knihovna otevírá svět možností pro manipulaci s PDF a umožňuje vám programově generovat úžasné dokumenty. Ať už vytváříte zprávy, faktury nebo jakýkoli jiný typ PDF, Aspose.PDF vám s tím pomůže.

## Často kladené otázky

### Co je Aspose.PDF pro .NET?
Aspose.PDF pro .NET je knihovna, která umožňuje vývojářům programově vytvářet, manipulovat a převádět PDF dokumenty.

### Mohu používat Aspose.PDF zdarma?
Ano, Aspose nabízí bezplatnou zkušební verzi, kterou můžete použít k prozkoumání funkcí knihovny. Můžete si ji stáhnout. [zde](https://releases.aspose.com/).

### Existuje způsob, jak získat podporu pro Aspose.PDF?
Rozhodně! Podporu můžete získat prostřednictvím fóra Aspose. [zde](https://forum.aspose.com/c/pdf/10).

### Jak si mohu zakoupit Aspose.PDF?
Soubor Aspose.PDF si můžete zakoupit na stránce nákupu. [zde](https://purchase.aspose.com/buy).

### Jaké typy tvarů mohu vytvářet pomocí Aspose.PDF?
Pomocí knihovny Aspose.PDF můžete vytvářet různé tvary, včetně obdélníků, kruhů, čar a dalších.