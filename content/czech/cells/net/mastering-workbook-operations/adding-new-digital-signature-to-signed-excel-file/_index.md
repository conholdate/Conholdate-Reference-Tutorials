---
"description": "Naučte se, jak přidat nový digitální podpis do existujícího podepsaného souboru aplikace Excel pomocí nástroje Aspose.Cells pro .NET. Tato komplexní příručka zahrnuje všechny předpoklady, podrobné pokyny a příklad kódu."
"linktitle": "Přidání nového digitálního podpisu do podepsaného souboru Excelu"
"second_title": "Rozhraní API pro zpracování Excelu Aspose.Cells v .NET"
"title": "Přidání nového digitálního podpisu do podepsaného souboru Excelu"
"url": "/cs/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## Zavedení

dnešní digitální krajině je zajištění autenticity a integrity dokumentů důležitější než kdy dříve. Digitální podpisy poskytují spolehlivý způsob, jak ověřit, zda dokument nebyl pozměněn a zda pochází z legitimního zdroje. Pokud pracujete s excelovými soubory v .NET a potřebujete přidat nový digitální podpis k již podepsanému souboru, je tento průvodce určen právě vám! Provedeme vás procesem přidání digitálního podpisu k existujícímu podepsanému excelovému souboru pomocí Aspose.Cells pro .NET.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte následující:

1. Aspose.Cells pro .NET: Stáhněte a nainstalujte Aspose.Cells z [stránka s vydáním](https://releases.aspose.com/cells/net/).
2. .NET Framework: Ujistěte se, že máte na počítači nainstalovaný .NET Framework a že znáte základní programovací koncepty v .NET.
3. Digitální certifikát: Získejte platný digitální certifikát ve formátu .pfx. Pro testování si můžete vytvořit certifikát s vlastním podpisem.
4. Vývojové prostředí: K napsání a spuštění kódu v C# použijte IDE, jako je Visual Studio.
5. Ukázkový soubor aplikace Excel: Mějte existující soubor aplikace Excel, který je již digitálně podepsaný a který bude cílem pro přidání nového podpisu.

S těmito předpoklady se pojďme pustit do kódu!

## Importovat potřebné balíčky

V horní části souboru C# uveďte následující jmenné prostory pro přístup k požadovaným třídám a metodám:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: Definujte své adresáře

Zadejte adresáře pro zdrojové soubory a kam uložit výstupní soubor:

```csharp
// Zdrojový adresář
string sourceDir = "Your Document Directory"; // Nahraďte svým skutečným adresářem
// Výstupní adresář
string outputDir = "Your Document Directory"; // Nahraďte svým skutečným adresářem
```

## Krok 2: Načtení existujícího podepsaného sešitu

Načtěte již podepsaný sešit aplikace Excel:

```csharp
// Načtěte sešit, který je již digitálně podepsaný
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## Krok 3: Vytvořte sbírku digitálních podpisů

Vytvořte kolekci pro správu digitálních podpisů:

```csharp
// Vytvořte kolekci digitálních podpisů
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## Krok 4: Načtěte si certifikát

Načtěte si svůj digitální certifikát, který bude použit k vytvoření nového podpisu:

```csharp
// Soubor certifikátu a jeho heslo
string certFileName = sourceDir + "AsposeDemo.pfx"; // Váš soubor certifikátu
string password = "aspose"; // Heslo k vašemu certifikátu

// Vytvořit nový certifikát
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## Krok 5: Vytvořte nový digitální podpis

Nyní si vytvořte nový digitální podpis a přidejte ho do své sbírky:

```csharp
// Vytvořte nový digitální podpis a přidejte ho do kolekce
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## Krok 6: Přidání kolekce podpisů do sešitu

Přidejte kolekci digitálních podpisů do sešitu:

```csharp
// Přidání kolekce digitálních podpisů do sešitu
workbook.AddDigitalSignature(dsCollection);
```

## Krok 7: Uložení sešitu

Uložte sešit s novým digitálním podpisem:

```csharp
// Uložit sešit
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## Krok 8: Potvrzení úspěchu

Po úspěšném provedení poskytněte zpětnou vazbu:

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## Závěr

Gratulujeme! Úspěšně jste přidali nový digitální podpis do již podepsaného souboru aplikace Excel pomocí nástroje Aspose.Cells for .NET. Tento proces zvyšuje zabezpečení vašich dokumentů a zajišťuje jejich autenticitu a integritu.

## Často kladené otázky

### Co je to digitální podpis?

Digitální podpis je matematický systém, který ověřuje pravost a integritu digitálních zpráv nebo dokumentů, zajišťuje, že nebyly pozměněny, a potvrzuje totožnost podepisujícího.

### Potřebuji k vytvoření digitálního podpisu speciální certifikát?

Ano, k vytvoření platného digitálního podpisu je vyžadován digitální certifikát vydaný důvěryhodnou certifikační autoritou (CA).

### Mohu k testování použít certifikát s vlastním podpisem?

Rozhodně! Pro účely vývoje a testování můžete použít certifikát s vlastním podpisem, ale pro produkční prostředí je vhodné použít certifikát od důvěryhodné certifikační autority.

### Co se stane, když se pokusím přidat podpis k nepodepsanému dokumentu?

Pokud se pokusíte přidat digitální podpis k dokumentu, který ještě není podepsaný, bude to fungovat bez problémů, ale původní podpis nebude přítomen.

### Kde najdu více informací o Aspose.Cells?

Podrobné návody a reference API naleznete v [Dokumentace k Aspose.Cells](https://reference.aspose.com/cells/net/).