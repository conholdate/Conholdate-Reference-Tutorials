---
"description": "Naučte se, jak efektivně ukládat dokumenty Microsoft OneNote jako soubory PDF pomocí Aspose.Note pro .NET. Tato příručka vás provede nezbytnými předpoklady a nabízí užitečné odpovědi na často kladené otázky."
"linktitle": "Ukládání dokumentů OneNote do PDF"
"second_title": "Rozhraní Aspose.Note .NET API"
"title": "Ukládání dokumentů OneNote do PDF pomocí Aspose.Note pro .NET"
"url": "/cs/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Zavedení

V tomto tutoriálu se podíváme na to, jak ukládat dokumenty do formátu PDF pomocí knihovny Aspose.Note pro .NET. Aspose.Note je výkonná knihovna, která umožňuje vývojářům programově pracovat se soubory aplikace Microsoft OneNote. Probereme předpoklady, importujeme jmenné prostory a poskytneme podrobné návody pro ukládání dokumentů do formátu PDF v různých rozvrženích stránek.

## Předpoklady
1. Visual Studio: Ujistěte se, že je nainstalováno.
2. Aspose.Note pro .NET: Stáhněte a nainstalujte knihovnu.
3. Znalost C#: Vyžaduje se základní znalost jazyka.

## Import nezbytných jmenných prostorů
Než budete pokračovat, importujte do kódu následující jmenné prostory:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Krok 1: Uložení do PDF s nastavením stránky typu Letter
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Aktualizovat tuto cestu
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Načte dokument OneNote a uloží ho jako PDF s nastavením velikosti stránky Letter.

## Krok 2: Uložení do PDF s nastavením velikosti stránky A4 (bez omezení výšky)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Aktualizovat tuto cestu
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Podobné jako krok 1, ale používá nastavení stránky A4 bez omezení výšky.

## Závěr
Tento tutoriál úspěšně ukazuje, jak převést soubory OneNote do formátu PDF pomocí Aspose.Note. Využitím různých nastavení stránek získají vývojáři flexibilitu ve správě dokumentů.

## Často kladené otázky
### Dokáže Aspose.Note zpracovat složité soubory OneNote?
Ano, efektivně zvládá různé funkce složitých souborů OneNote.

### Je Aspose.Note vhodný pro komerční projekty?
Ano, po zakoupení licence jej můžete použít pro komerční aplikace.

### Nabízí Aspose.Note bezplatnou zkušební verzi?
Ano, k dispozici je bezplatná zkušební verze.

### Kde najdu dokumentaci k Aspose.Note?
Podrobná dokumentace je k dispozici na referenčních stránkách Aspose.

### Potřebujete další pomoc?
V případě dotazů a potřeby podpory se obraťte na fórum Aspose.Note.