---
"description": "Vykreslete události kalendáře do formátu MHTML pomocí Aspose.Email pro .NET. Naučte se krok za krokem, jak upravovat a ukládat soubory MSG pomocí C#."
"linktitle": "Vykreslení událostí kalendáře v MHTML pomocí Aspose.Email"
"second_title": "Rozhraní API pro zpracování e-mailů Aspose.Email v .NET"
"title": "Vykreslení událostí kalendáře v MHTML pomocí Aspose.Email"
"url": "/cs/email/net/handling-email-events-and-calendar/render-calendar-events-in-mhtml/"
"weight": 15
---

## Zavedení

Aspose.Email pro .NET je výkonná knihovna pro zpracování úloh souvisejících s e-mailem v aplikacích .NET. Jedním fascinujícím případem použití je programově vykreslování událostí kalendáře pomocí jazyka C#. Ať už vytváříte funkci pro integraci kalendáře nebo vlastní prohlížeče e-mailů, tento tutoriál vás provede vykreslováním událostí kalendáře do formátu MHTML s přesností a možnostmi přizpůsobení.

## Předpoklady

Než se do toho pustíme, ujistěte se, že máme vše připravené k provedení tohoto tutoriálu:

1. Knihovna Aspose.Email pro .NET: Stáhněte si nejnovější verzi knihovny z [Stránka ke stažení Aspose.Email pro .NET](https://releases.aspose.com/email/net/).
2. Vývojové prostředí: Visual Studio (nebo vámi preferované C# IDE) nainstalované ve vašem systému.
3. Licence: Získejte platnou licenci pro Aspose.Email. Pro účely vyhodnocení můžete použít [dočasná licence](https://purchase.aspose.com/temporary-license/).
4. Ukázkový soubor MSG: Soubor MSG události kalendáře. Můžete použít libovolný `.msg` soubor s událostmi kalendáře, například „Schůzka s opakujícími se událostmi.msg“.

## Importovat balíčky

Chcete-li začít, zahrňte do projektu potřebné jmenné prostory. 

```csharp
using System;
using Aspose.Email;
using Aspose.Email.Mht;
```

A teď se pojďme podívat na podrobný návod!

## Krok 1: Načtěte soubor MSG událostí kalendáře

Nejprve načteme soubor MSG, který obsahuje událost kalendáře. Tento krok je nezbytný, protože slouží jako vstup pro vykreslení události do formátu MHTML.


```csharp
string dataDir = "Your Data Directory";
string fileName = "Meeting with Recurring Occurrences.msg";

// Načtěte soubor MSG
MailMessage msg = MailMessage.Load(dataDir + fileName);
```

- `dataDir`Určuje adresář, kde je uložen soubor MSG.
- `fileName`Název souboru události kalendáře.
- `MailMessage.Load`Přečte soubor a načte ho do `MailMessage` objekt.

## Krok 2: Konfigurace možností ukládání MHTML

Dále nakonfigurujeme možnosti pro vykreslení události kalendáře do formátu MHTML. To zahrnuje povolení specifických formátů, záhlaví a dalších vlastností pro přizpůsobení.

```csharp
MhtSaveOptions options = new MhtSaveOptions
{
    MhtFormatOptions = MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent
};
```

- `MhtSaveOptions`: Představuje nastavení pro ukládání souborů MHTML.
- `MhtFormatOptions`: Konfiguruje možnosti, jako je zahrnutí záhlaví a vykreslování událostí kalendáře.

## Krok 3: Přizpůsobení šablon zobrazení

Zde definujeme, jak by se měly ve výstupu zobrazovat specifické vlastnosti, jako například čas zahájení události. Tento krok umožňuje vysoce přizpůsobitelný a čitelný výstup.


```csharp
if (options.FormatTemplates.ContainsKey(MhtTemplateName.Start))
    options.FormatTemplates[MhtTemplateName.Start] = @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>";
else
    options.FormatTemplates.Add(MhtTemplateName.Start, @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

- `MhtTemplateName.Start`Odkazuje na vlastnost „Start“ události kalendáře.
- `options.FormatTemplates`: Přizpůsobí šablonu zobrazení pro konkrétní vlastnosti.

## Krok 4: Uložení události kalendáře jako MHTML

Nakonec uložte událost kalendáře do souboru MHTML s nakonfigurovanými možnostmi.


```csharp
msg.Save(dataDir + "Meeting with Recurring Occurrences.mhtml", options);
```

- `msg.Save`: Uloží zprávu v zadaném formátu a umístění.
- `Meeting with Recurring Occurrences.mhtml`Název výstupního souboru.

## Závěr

Vykreslování událostí kalendáře pomocí Aspose.Email pro .NET je efektivní a vysoce přizpůsobitelné. Dodržením výše uvedených kroků můžete bez problémů převést události kalendáře do souboru MHTML s přizpůsobeným formátováním.

## Často kladené otázky

### Co je MHTML?
MHTML je formát webového archivu, který obsahuje HTML a související zdroje, jako jsou obrázky, díky čemuž je vhodný pro vykreslování a sdílení událostí kalendáře.

### Mohu vykreslovat opakující se události?
Ano! Aspose.Email podporuje vykreslování opakujících se událostí, což zajišťuje přesné zachycení všech detailů.

### Je vyžadována licence?
Ano, je nutná platná licence. Můžete si o ni požádat [dočasná licence](https://purchase.aspose.com/temporary-license/) pro hodnocení.

### Mohu do výstupu přidat vlastní vlastnosti?
Rozhodně! Šablony pro další vlastnosti si můžete přizpůsobit pomocí `FormatTemplates` sbírka.

### Jak mohu řešit problémy?
Navštivte [Fórum podpory Aspose.Email](https://forum.aspose.com/c/email/12/) pro odbornou pomoc.