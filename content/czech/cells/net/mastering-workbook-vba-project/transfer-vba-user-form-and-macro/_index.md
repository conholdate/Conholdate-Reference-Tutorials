---
"description": "Odemkněte sílu automatizace Excelu s tímto komplexním průvodcem přenosem uživatelských formulářů VBA a maker mezi sešity pomocí Aspose.Cells pro .NET. Ideální pro začátečníky i zkušené vývojáře."
"linktitle": "Přenos uživatelských formulářů a maker VBA mezi sešity aplikace Excel"
"second_title": "Rozhraní API pro zpracování Excelu Aspose.Cells v .NET"
"title": "Přenos uživatelských formulářů a maker VBA mezi sešity aplikace Excel"
"url": "/cs/cells/net/mastering-workbook-vba-project/transfer-vba-user-form-and-macro/"
"weight": 11
---

## Zavedení

Vítejte u vašeho dokonalého průvodce pro vylepšení vašeho zážitku s Excelem pomocí maker VBA a uživatelských formulářů! V tomto tutoriálu se podíváme na to, jak přenést návrhář uživatelských formulářů maker VBA z jednoho sešitu do druhého pomocí výkonné knihovny Aspose.Cells pro .NET. Ať už jste zkušený vývojář nebo teprve začínáte, tento podrobný průvodce vás vybaví znalostmi pro programovou práci se soubory Excelu. Jste připraveni se do toho pustit? Pojďme na to!

## Předpoklady
Než se pustíme do kódování, ujistěte se, že máte vše, co potřebujete:

1. Vývojové prostředí C#: Pracovní prostředí pro vývoj v C#, přičemž vysoce doporučujeme Visual Studio.
2. Knihovna Aspose.Cells pro .NET: Nezapomeňte do svého projektu integrovat knihovnu Aspose.Cells. Můžete snadno [stáhněte si to zde](https://releases.aspose.com/cells/net/).
3. Základní znalost VBA a maker v Excelu: Znalost VBA a fungování maker v Excelu vám pomůže lépe porozumět tomuto tutoriálu.
4. Soubor aplikace Excel s uživatelským formulářem: Vytvořte nebo získejte sešit aplikace Excel obsahující uživatelský formulář (nejlépe s povolenými makry, například `.xlsm` soubory).

## Import požadovaných balíčků
Chcete-li využít funkce poskytované Aspose.Cells, uveďte na začátek souboru C# následující jmenné prostory:

```csharp
using System;
using Aspose.Cells;
using Aspose.Cells.Vba;
```

Tyto jmenné prostory vám poskytnou přístup k výkonným nástrojům obsaženým v knihovně Aspose.Cells.

## Krok 1: Definujte zdrojové a výstupní adresáře
Nejprve si určete umístění souborů:

```csharp
// Definujte zdrojový a výstupní adresář
string sourceDir = @"Your\Source\Directory\";
string outputDir = @"Your\Output\Directory\";
```

Nahraďte zástupné cesty skutečnými adresáři, kde jsou uloženy vaše soubory.

## Krok 2: Vytvořte prázdný cílový sešit
Dále vytvořte nový sešit, do kterého zkopírujete uživatelský formulář a makra:

```csharp
// Vytvoření prázdného cílového sešitu
Workbook target = new Workbook();
```

Tím se inicializuje prázdný sešit, který slouží jako plátno pro nadcházející přenos dat.

## Krok 3: Načtěte si šablonu sešitu
Načtěte sešit obsahující uživatelský formulář a makra:

```csharp
// Načtěte soubor Excel obsahující uživatelský formulář návrháře maker VBA
Workbook templateFile = new Workbook(sourceDir + "sampleDesignerForm.xlsm");
```

Upravit `"sampleDesignerForm.xlsm"` k názvu vašeho skutečného souboru.

## Krok 4: Zkopírování pracovních listů do cílového sešitu
Nyní zkopírujme listy ze šablony do cílového sešitu:

```csharp
// Zkopírovat všechny šablony listů do cílového sešitu
foreach (Worksheet ws in templateFile.Worksheets)
{
    if (ws.Type == SheetType.Worksheet)
    {
        Worksheet s = target.Worksheets.Add(ws.Name);
        s.Copy(ws);
        // Přidat zprávu do buňky A2 cílového listu
        s.Cells["A2"].PutValue("VBA Macro and User Form copied from template to target.");
    }
}
```

Tento kód prochází každý list v šabloně a kopíruje ho do cílového sešitu, čímž zajišťuje bezproblémový přenos všech dat.

## Krok 5: Zkopírujte makra VBA ze šablony
Dále zkopírujeme makra VBA, včetně modulů UserForm Designer, do nového sešitu:

```csharp
// Zkopírujte uživatelský formulář v návrháři maker VBA ze šablony do cíle
foreach (VbaModule vbaItem in templateFile.VbaProject.Modules)
{
    if (vbaItem.Name == "ThisWorkbook")
    {
        // Zkopírovat kód modulu ThisWorkbook
        target.VbaProject.Modules["ThisWorkbook"].Codes = vbaItem.Codes;
    }
    else
    {
        // Zkopírujte kód a data ostatních modulů
        int vbaMod = target.VbaProject.Modules.Add(vbaItem.Type, vbaItem.Name);
        target.VbaProject.Modules[vbaMod].Codes = vbaItem.Codes;

        if (vbaItem.Type == VbaModuleType.Designer)
        {
            // Získejte úložiště pro návrháře uživatelských formulářů
            byte[] designerStorage = templateFile.VbaProject.Modules.GetDesignerStorage(vbaItem.Name);
            // Přidání úložiště návrháře do cílového projektu VBA
            target.VbaProject.Modules.AddDesignerStorage(vbaItem.Name, designerStorage);
        }
    }
}
```

Tento kód zajišťuje, že se zkopíruje nejen kód, ale i návrh uživatelského formuláře, čímž se zachová funkčnost vašich maker.

## Krok 6: Uložení cílového sešitu
Po dokončení kopírování uložte nový sešit:

```csharp
// Uložit cílový sešit
target.Save(outputDir + "outputDesignerForm.xlsm", SaveFormat.Xlsm);
```

Upravte název výstupního souboru podle potřeby. Tento krok vytvoří váš přizpůsobený sešit naplněný makry a uživatelskými formuláři.

## Krok 7: Potvrzení úspěchu
Nakonec vypište do konzole zprávu o úspěchu:

```csharp
Console.WriteLine("CopyVBAMacroUserFormDesignerStorageToWorkbook executed successfully.\r\n");
```

Tato jednoduchá věta vás ujistí, že váš proces proběhl hladce – zásadní potvrzení vaší tvrdé práce!

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak kopírovat návrhář uživatelských formulářů maker VBA z jednoho sešitu do druhého pomocí Aspose.Cells pro .NET. I když se to zpočátku může zdát náročné, cvik vám pomůže zvládnout práci se sešity. Nezapomeňte, že kódování je o experimentování, takže neváhejte prozkoumat různé funkce v souborech Excel. Pokud máte jakékoli dotazy nebo potřebujete pomoc, fóra a dokumentace Aspose jsou vynikajícími zdroji podpory.

## Často kladené otázky

### Jaké verze Excelu podporuje Aspose.Cells?
Aspose.Cells podporuje různé formáty aplikace Excel, včetně XLSX, XLSM, CSV a dalších.

### Mohu používat Aspose.Cells zdarma?
Ano! Můžete začít s bezplatnou zkušební verzí a otestovat knihovnu: [Bezplatná zkušební verze](https://releases.aspose.com/).

### Potřebuji Visual Studio ke spuštění tohoto kódu?
I když se Visual Studio doporučuje pro své uživatelsky přívětivé funkce, postačí jakékoli C# IDE, které podporuje vývoj v .NET.

### Kde najdu další příklady a dokumentaci?
Můžete prozkoumat [Dokumentace k Aspose.Cells](https://reference.aspose.com/cells/net/) pro další příklady a podrobnější vysvětlení.

### Jak vyřeším problémy s používáním Aspose.Cells?
Měli byste navštívit [Fórum podpory Aspose](https://forum.aspose.com/c/cells/9) za pomoc od komunity a podpůrného personálu Aspose.