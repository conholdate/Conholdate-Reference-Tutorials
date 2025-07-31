---
"description": "Naučte se, jak vytvářet a upravovat primitivní 3D modely, včetně krabic a válců, a jak je bez námahy ukládat ve formátu FBX."
"linktitle": "Vytvořte primitivní 3D modelování"
"second_title": "Rozhraní Aspose.3D .NET API"
"title": "Vytvořte primitivní 3D modelování"
"url": "/cs/3d/net/guide-to-3d-modeling/create-primitive-3d-modeling/"
"weight": 10
---

## Zavedení

Vítejte v pohlcujícím světě 3D modelování pomocí Aspose.3D pro .NET! V tomto komplexním tutoriálu vás krok za krokem provedeme procesem vytváření primitivních 3D modelů. Ať už jste zkušený vývojář nebo začátečník, který se chce učit, tento průvodce vám pomůže vytvářet vizuálně ohromující 3D prvky pro vaše projekty.

## Předpoklady

Než se pustíte do 3D modelování, ujistěte se, že máte splněny následující předpoklady:

- Aspose.3D pro .NET: Stáhněte a nainstalujte knihovnu Aspose.3D pro .NET z [stránka ke stažení](https://releases.aspose.com/3d/net/).
  
- Vývojové prostředí .NET: Nastavte prostředí kompatibilní s Aspose.3D, například Visual Studio.

Se vším připraveným se pojďme vydat na naše 3D modelovací dobrodružství!

## Import požadovaných jmenných prostorů

Začněte importem potřebných jmenných prostorů pro přístup k funkcím Aspose.3D:

```csharp
using System;
using System.IO;
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
```

Tyto jmenné prostory vám poskytnou nástroje potřebné k manipulaci s 3D modely a ukládání vašich výtvorů.

## Krok 1: Inicializace objektu scény

Vytvořte nový objekt scény, který bude sloužit jako plátno pro vaše 3D modely:

```csharp
// Inicializace objektu Scene
Scene scene = new Scene();
```

Tato scéna bude obsahovat primitivní tvary, které se chystáte vytvořit.

## Krok 2: Vytvořte krabicový model

Dále přidáme do vaší scény krabicový model:

```csharp
// Vytvořte krabicový model
scene.RootNode.CreateChildNode("box", new Box());
```

Rozměry a vlastnosti krabice si můžete přizpůsobit podle své kreativní vize.

## Krok 3: Vytvořte model válce

Nyní vylepšete svou scénu přidáním válce:

```csharp
// Vytvořte model válce
scene.RootNode.CreateChildNode("cylinder", new Cylinder());
```

Stejně jako u krabice můžete upravit parametry válce tak, abyste dosáhli požadovaného vzhledu.

## Krok 4: Uložení scény ve formátu FBX

Chcete-li zachovat svůj 3D model, uložte jej ve formátu FBX:

```csharp
// Uložit výkres ve formátu FBX
var output = Path.Combine("Your Output Directory", "test.fbx");
scene.Save(output, FileFormat.FBX7500ASCII);
```

Ujistěte se, že jste pro váš model vybrali vhodný výstupní adresář a název souboru.

## Krok 5: Zobrazení zprávy o úspěchu

Nakonec oslavte svůj úspěch zobrazením zprávy:

```csharp
// Zobrazit zprávu o úspěchu
Console.WriteLine($"\nBuilding a scene from primitive 3D models was successful.\nFile saved at {output}");
```

Vaše 3D scéna složená z primitivních modelů je nyní dokončena a uložena!

## Závěr

Gratulujeme k vytvoření úžasných 3D modelů pomocí Aspose.3D pro .NET! Tento tutoriál se zabýval základy primitivního modelování, ale možnosti jsou nekonečné. Prozkoumejte více o pokročilých funkcích a technikách v... [dokumentace](https://reference.aspose.com/3d/net/).

## Často kladené otázky

### Mohu použít Aspose.3D pro .NET s jinými programovacími jazyky než .NET?

Aspose.3D podporuje hlavně .NET, ale existují verze pro Javu a další platformy.

### Je k dispozici bezplatná zkušební verze?

Ano, můžete si vyzkoušet možnosti Aspose.3D s [bezplatná zkušební verze](https://releases.aspose.com/).

### Kde najdu podporu pro Aspose.3D pro .NET?

Pro podporu komunity navštivte [Fórum Aspose.3D](https://forum.aspose.com/c/3d/18).

### Jak mohu získat dočasnou licenci?

Můžete požádat o dočasnou licenci [zde](https://purchase.conholdate.com/temporary-license/).

### Jsou k dispozici další tutoriály?

Ano! Prozkoumejte další návody a příklady v [dokumentace](https://reference.aspose.com/3d/net/).