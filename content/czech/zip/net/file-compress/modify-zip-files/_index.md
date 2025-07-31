---
"description": "Naučte se, jak efektivně programově extrahovat, mazat a přidávat položky do zip souborů a vylepšit tak své schopnosti manipulace se soubory."
"linktitle": "Úprava souborů ZIP"
"second_title": "Aspose.Zip .NET API pro kompresi a archivaci souborů"
"title": "Úprava souborů ZIP pomocí Aspose.Zip pro .NET"
"url": "/cs/zip/net/file-compress/modify-zip-files/"
"weight": 15
---

## Zavedení

Soubory ZIP jsou nezbytné pro organizaci a kompresi dat, ale jak programově upravit jejich obsah? Řešení spočívá v Aspose.Zip pro .NET, robustní knihovně, která zjednodušuje manipulaci se soubory ZIP pomocí C#. V tomto tutoriálu vás krok za krokem provedeme extrakcí, mazáním a přidáváním položek do souborů ZIP.

## Předpoklady

Než se do toho pustíme, ujistěte se, že máte následující:

1. Aspose.Zip pro .NET knihovnu: Nainstalujte si knihovnu do svého projektu. Můžete si ji stáhnout. [zde](https://releases.aspose.com/zip/net/).
   
2. Adresář dokumentů: Nastavte adresář pro ukládání souborů ZIP. Nahraďte `"Your Document Directory"` v kódu s vaší skutečnou cestou.

## Importovat nezbytné jmenné prostory

Začněte importem požadovaných jmenných prostorů:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Otevřete vnější soubor ZIP

Začněte otevřením hlavního zip souboru (vnější zip):

```csharp
string dataDir = "Your Data Directory";
using (Archive outer = new Archive(dataDir + "outer.zip"))
{
    // Pokračujte v identifikaci vnitřních položek zipu
}
```

## Krok 2: Identifikace vnitřních položek zipu

Dále identifikujte a připravte se k odstranění všech vnitřních souborů zip:

```csharp
List<ArchiveEntry> entriesToDelete = new List<ArchiveEntry>();
List<string> namesToInsert = new List<string>();
List<MemoryStream> contentToInsert = new List<MemoryStream>();

foreach (ArchiveEntry entry in outer.Entries)
{
    if (entry.Name.EndsWith(".zip", StringComparison.InvariantCultureIgnoreCase))
    {
        entriesToDelete.Add(entry);
        
        using (MemoryStream innerCompressed = new MemoryStream())
        {
            entry.Open().CopyTo(innerCompressed);
            
            // Extrahovat vnitřní položky
            using (Archive inner = new Archive(innerCompressed))
            {
                foreach (ArchiveEntry ie in inner.Entries)
                {
                    namesToInsert.Add(ie.Name);
                    MemoryStream content = new MemoryStream();
                    ie.Open().CopyTo(content);
                    contentToInsert.Add(content);
                }
            }
        }
    }
}
```

## Krok 3: Smazání položek vnitřního archivu

Jakmile shromáždíte potřebné položky, odstraňte vnitřní položky zip archivu:

```csharp
foreach (ArchiveEntry e in entriesToDelete)
{
    outer.DeleteEntry(e);
}
```

## Krok 4: Přidání upravených položek do vnějšího PSČ

Nyní můžete nově extrahované položky přidat zpět do vnějšího zip souboru:

```csharp
for (int i = 0; i < namesToInsert.Count; i++)
{
    outer.CreateEntry(namesToInsert[i], contentToInsert[i]);
}
```

## Krok 5: Uložte upravený soubor ZIP

Nakonec uložte změny do nového zip souboru:

```csharp
outer.Save(dataDir + "flatten.zip");
```

## Závěr

Aspose.Zip pro .NET nabízí výkonný a přímočarý způsob programově manipulace se soubory ZIP. Tento tutoriál se zabýval extrakcí, mazáním a přidáváním položek do souboru ZIP a ilustroval všestrannost knihovny. Prozkoumejte různé scénáře a vylepšete si své dovednosti v manipulaci se soubory!

## Často kladené otázky

### Mohu použít Aspose.Zip pro .NET s jinými programovacími jazyky?
Aspose.Zip je primárně určen pro .NET aplikace, ale Aspose nabízí podobné knihovny pro různé programovací jazyky.

### Je k dispozici bezplatná zkušební verze Aspose.Zip pro .NET?
Ano, je k dispozici ke stažení bezplatná zkušební verze. [zde](https://releases.aspose.com/).

### Jak získám podporu pro Aspose.Zip pro .NET?
Navštivte [Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) za podporu a diskuzi.

### Mohu si zakoupit dočasnou licenci pro Aspose.Zip pro .NET?
Ano, můžete získat dočasnou licenci [zde](https://purchase.conholdate.com/temporary-license/).

### Kde najdu dokumentaci k Aspose.Zip pro .NET?
Kompletní dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/).