---
"description": "Naučte se, jak bezproblémově přidávat text ze záložek v dokumentu Word pomocí Aspose.Words pro .NET. Tento podrobný návod."
"linktitle": "Přidání textu ze záložek v dokumentech Word"
"second_title": "Rozhraní API pro zpracování dokumentů Aspose.Words"
"title": "Přidání textu ze záložek v dokumentech Word"
"url": "/cs/words/net/mastering-bookmarks/append-text-from-bookmarked-sections/"
"weight": 10
---

## Zavedení

Už se vám někdy stávalo, že je náročné přidávat text ze záložkové sekce v dokumentu Wordu? Jste na správném místě! Tento tutoriál vás krok za krokem provede celým procesem s využitím Aspose.Words pro .NET. Na konci budete schopni přidávat text ze záložek jako profesionál. Pojďme na to!

## Předpoklady

Než se do toho pustíme, ujistěte se, že máte následující:

- Aspose.Words pro .NET: Pokud jste si ho ještě nenainstalovali, můžete [stáhněte si to zde](https://releases.aspose.com/words/net/).
- Vývojové prostředí: Vývojové prostředí pro .NET, jako je Visual Studio.
- Základní znalost C#: Znalost základních programovacích konceptů v C# bude výhodou.
- Dokument aplikace Word se záložkami: Dokument aplikace Word obsahující záložky, ze kterých budeme přidávat text.

## Importovat nezbytné jmenné prostory

Nejprve musíme importovat požadované jmenné prostory pro přístup k funkcím Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

## Krok 1: Načtení dokumentu a inicializace proměnných

Začněme načtením zdrojového a cílového dokumentu Word a inicializací potřebných proměnných.

```csharp
// Načtěte zdrojové a cílové dokumenty.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Inicializujte importér dokumentů.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Vyhledejte záložku ve zdrojovém dokumentu.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Krok 2: Určete počáteční a koncový odstavec

Dále musíme najít odstavce, kde záložka začíná a končí. To je nezbytné pro extrakci správného textu.

```csharp
// Určete odstavce na začátku a na konci záložky.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

// Ověřte platnost odstavců.
if (startPara == null || endPara == null)
    throw new InvalidOperationException("Bookmark start or end does not have a valid paragraph parent.");
```

## Krok 3: Ověření rodičů odstavců

Musíme zajistit, aby počáteční i koncový odstavec sdílely stejný nadřazený uzel. Jedná se o zjednodušený přístup, který předejde komplikacím.

```csharp
// Zkontrolujte, zda počáteční a koncový odstavec mají stejného rodiče.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs must have the same parent.");
```

## Krok 4: Identifikace uzlu k zastavení

Nyní musíme určit, kde se má kopírování textu zastavit, což bude uzel bezprostředně za koncovým odstavcem.

```csharp
// Identifikujte uzel bezprostředně za koncovým odstavcem.
Node endNode = endPara.NextSibling;
```

## Krok 5: Přidání textu záložkou do cílového dokumentu

Nakonec projdeme uzly od počátečního odstavce k uzlu za koncovým odstavcem a připojíme je do cílového dokumentu.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Importujte aktuální uzel do cílového dokumentu.
    Node newNode = importer.ImportNode(curNode, true);

    // Připojte importovaný uzel k cílovému dokumentu.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Uložte aktualizovaný cílový dokument.
dstDoc.Save("appended_document.docx");
```

## Závěr

Gratulujeme! Úspěšně jste přidali text ze záložky v dokumentu Wordu pomocí knihovny Aspose.Words pro .NET. Tato výkonná knihovna usnadňuje manipulaci s dokumenty a nyní máte ve své sadě nástrojů další užitečnou dovednost. Přejeme vám hodně štěstí s programováním!

## Často kladené otázky

### Mohu přidat text z více záložek najednou?
Ano, postup můžete opakovat pro každou záložku a podle potřeby doplnit text.

### Co když mají počáteční a koncový odstavec různé nadřazené odstavce?
Aktuální příklad předpokládá, že mají stejného rodiče. Pokud ne, budete muset implementovat složitější zpracování.

### Bude zachováno původní formátování připojeného textu?
Rozhodně! Používání `ImportFormatMode.KeepSourceFormatting` zajišťuje zachování původního formátování.

### Je možné přidat text na určitou pozici v cílovém dokumentu?
Ano, text můžete přidat na libovolnou požadovanou pozici přechodem na příslušný uzel v cílovém dokumentu.

### Mohu přidat text ze záložky do nové sekce?
Ano, v cílovém dokumentu můžete vytvořit novou sekci a text tam přidat.