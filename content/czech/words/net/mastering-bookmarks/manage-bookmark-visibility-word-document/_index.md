---
"description": "Zjistěte, jak odborně ovládat viditelnost obsahu v dokumentech Wordu pomocí Aspose.Words pro .NET. Tento podrobný návod."
"linktitle": "Správa viditelnosti záložek v dokumentech Wordu"
"second_title": "Rozhraní API pro zpracování dokumentů Aspose.Words"
"title": "Správa viditelnosti záložek v dokumentech Wordu"
"url": "/cs/words/net/mastering-bookmarks/manage-bookmark-visibility-word-document/"
"weight": 10
---

## Zavedení

Jste připraveni vylepšit své dovednosti v oblasti manipulace s dokumenty s Aspose.Words pro .NET? Ať už jste zkušený vývojář automatizující úlohy s dokumenty, nebo zvědavý jedinec zkoumající programové ovládání souborů Wordu, tato příručka je určena právě vám. Dnes se ponoříme do toho, jak zobrazit a skrýt obsah na základě záložek v dokumentu Wordu. Pojďme na to!

## Předpoklady

Než se do toho pustíme, ujistěte se, že máte následující:

1. Visual Studio: Jakákoli verze kompatibilní s .NET.
2. Aspose.Words pro .NET: Stáhněte si jej [zde](https://releases.aspose.com/words/net/).
3. Základní znalost C#: Postačí znalost psaní jednoduchých programů v C#.
4. Ukázkový dokument Wordu: Připravte si dokument Wordu (např. „Bookmarks.docx“) obsahující záložky pro tento tutoriál.

### Vytvořit nový projekt

1. Otevřete Visual Studio a vytvořte nový projekt konzolové aplikace (.NET Core). Pojmenujte ho například „BookmarkVisibilityManager“.

### Instalace Aspose.Words pro .NET

Přidejte Aspose.Words do svého projektu pomocí Správce balíčků NuGet:

1. Přejděte do nabídky Nástroje > Správce balíčků NuGet > Spravovat balíčky NuGet pro řešení.
2. Hledat „Aspose.Words“.
3. Nainstalujte balíček.

Po nastavení projektu můžeme pokračovat v načítání dokumentu.

## Import jmenných prostorů

Začněte importem základních jmenných prostorů. Ty poskytují třídy a metody potřebné pro manipulaci s dokumenty Wordu pomocí Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

## Krok 1: Načtení dokumentu

Abychom mohli manipulovat s dokumentem Wordu, musíme ho nejprve načíst. Zde je návod, jak to udělat:

```csharp
// Definujte cestu k adresáři s dokumenty.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

Tento úryvek kódu nastaví cestu k adresáři s dokumenty a načte dokument do `Document` objekt.

## Krok 2: Zobrazit/skrýt obsah uložený v záložkách

Nyní si vytvořme metodu pro přepínání viditelnosti obsahu na základě záložek. Tuto metodu nazveme `ShowHideBookmarkedContent`.

Zde je implementace metody:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    if (bm != null)
    {
        Node currentNode = bm.BookmarkStart;
        while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
        {
            if (currentNode.NodeType == NodeType.Run)
            {
                Run run = (Run)currentNode;
                run.Font.Hidden = isHidden;
            }
            currentNode = currentNode.NextSibling;
        }
    }
}
```

- Vyhledávání záložek: `Bookmark bm = doc.Range.Bookmarks[bookmarkName];` načte zadanou záložku.
- Průchod uzlem: Iterujeme uzly v záložce.
- Přepínání viditelnosti: Pro každý `Run` uzel (reprezentující segment textu), nastavíme jeho `Hidden` majetek na základě `isHidden` parametr.

## Krok 3: Použití metody

Nyní, když máme naši metodu připravenou, pojďme ji použít k zobrazení nebo skrytí obsahu v rámci konkrétní záložky:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true); // Skrývá obsah v záložce „Moje záložka1“
```

Tento řádek skryje obsah spojený se záložkou s názvem „MyBookmark1“.

## Krok 4: Uložení dokumentu

Jakmile provedete změny, nezapomeňte upravený dokument uložit:

```csharp
doc.Save(dataDir + "UpdatedBookmarks.docx");
```

Tím se dokument uloží s aktualizovaným nastavením viditelnosti.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak zobrazit a skrýt obsah záložek v dokumentu Word pomocí knihovny Aspose.Words pro .NET. Tato výkonná knihovna zjednodušuje manipulaci s dokumenty, takže je ideální pro automatizaci sestav, vytváření šablon nebo experimentování se soubory Word. Přejeme vám příjemné programování!

## Často kladené otázky

### Mohu přepínat více záložek najednou?
Ano, stačí zavolat `ShowHideBookmarkedContent` pro každou záložku, kterou chcete přepnout.

### Ovlivňuje skrytí obsahu strukturu dokumentu?
Ne, skrytí obsahu ovlivňuje pouze jeho viditelnost; obsah v dokumentu zůstává nedotčen.

### Mohu tuto metodu použít i pro jiné typy obsahu?
Tato metoda je speciálně navržena pro textové běhy. Pro ostatní typy obsahu budete muset odpovídajícím způsobem upravit logiku procházení uzlů.

### Je Aspose.Words pro .NET zdarma?
Aspose.Words nabízí bezplatnou zkušební verzi [zde](https://releases.aspose.com/), ale pro produkční použití je vyžadována plná licence. Můžete si ji zakoupit [zde](https://purchase.aspose.com/buy).

### Jak mohu získat podporu, pokud narazím na problémy?
Pro podporu navštivte fórum komunity Aspose [zde](https://forum.aspose.com/c/words/8).