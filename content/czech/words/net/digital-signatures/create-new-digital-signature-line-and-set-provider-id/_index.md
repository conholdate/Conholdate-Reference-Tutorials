---
"description": "Zjistěte, jak programově přidávat řádky pro podpis do dokumentů Word pomocí Aspose.Words pro .NET. Tato komplexní příručka pokrývá vše od nastavení vývojového prostředí až po vkládání řádků pro podpis a bezpečné podepisování dokumentů."
"linktitle": "Vytvořit nový řádek digitálního podpisu a nastavit ID poskytovatele"
"second_title": "Rozhraní API pro zpracování dokumentů Aspose.Words"
"title": "Vytvořit nový řádek digitálního podpisu a nastavit ID poskytovatele"
"url": "/cs/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Zavedení

Ahoj, technickí nadšenci! Chtěli jste někdy automatizovat vkládání podpisových řádků do dokumentů Wordu? Dnes se ponoříme do toho, jak toho dosáhnout pomocí Aspose.Words pro .NET. Tento podrobný návod vás provede vytvořením podpisového řádku a nastavením ID poskytovatele, čímž zefektivníte a zjednodušíte zpracování dokumentů.

## Předpoklady

Než se do toho pustíme, ujistěme se, že máte vše nastavené:

1. Aspose.Words pro .NET: Pokud jste si ho ještě nenainstalovali, stáhněte si ho [zde](https://releases.aspose.com/words/net/).
2. Vývojové prostředí: Použijte Visual Studio nebo libovolné vývojové prostředí C#.
3. .NET Framework: Ujistěte se, že máte na svém počítači nainstalovaný .NET Framework.
4. Certifikát PFX: Pro podepisování dokumentů budete potřebovat certifikát PFX, který lze získat od důvěryhodné certifikační autority.

## Import nezbytných jmenných prostorů

Chcete-li začít, importujte požadované jmenné prostory do svého projektu C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Nyní se pojďme ponořit do podrobností vytvoření nového řádku podpisu a nastavení ID poskytovatele.

## Krok 1: Vytvořte nový dokument

Nejprve musíme vytvořit nový dokument Wordu, který bude sloužit jako plátno pro náš podpis:

```csharp
// Zadejte cestu k adresáři s vašimi dokumenty.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zde inicializujeme nový `Document` a `DocumentBuilder`, což nám umožňuje snadno přidávat prvky.

## Krok 2: Definování možností řádku podpisu

Dále definujeme možnosti pro řádek podpisu, včetně jména podepisujícího, titulu, e-mailu a dalších relevantních údajů:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Tyto možnosti pomáhají personalizovat podpisový řádek, díky čemuž je jasný a profesionální.

## Krok 3: Vložte řádek podpisu

S připravenými možnostmi nyní můžeme do dokumentu vložit řádek podpisu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Ten/Ta/To `InsertSignatureLine` Metoda přidá řádek podpisu a my mu přiřadíme jedinečné ID poskytovatele.

## Krok 4: Uložte dokument

Po vložení řádku podpisu uložme dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Tím se dokument uloží s nově přidaným řádkem pro podpis.

## Krok 5: Nastavení možností podepisování

Nyní nakonfigurujeme možnosti podepisování, včetně ID řádku podpisu, ID poskytovatele, komentářů a času podpisu:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Tato nastavení zajišťují, že dokument bude podepsán se správnými údaji.

## Krok 6: Vytvoření držitele certifikátu

Pro podepsání dokumentu musíme vytvořit držitele certifikátu pomocí certifikátu PFX:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Nahradit `"morzal.pfx"` s vaším skutečným názvem souboru certifikátu a `"aw"` s heslem k vašemu certifikátu.

## Krok 7: Podepište dokument

Nakonec dokument podepíšeme pomocí nástroje pro digitální podpis:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Tento proces podepíše dokument a uloží jej jako nový soubor.

## Závěr

Gratulujeme! Úspěšně jste vytvořili řádek pro podpis a nastavili ID poskytovatele v dokumentu Word pomocí knihovny Aspose.Words pro .NET. Tato výkonná knihovna zjednodušuje úlohy zpracování dokumentů a zefektivňuje váš pracovní postup. Vyzkoušejte ji a uvidíte, jak může vylepšit vaše projekty!

## Často kladené otázky

### Mohu si přizpůsobit vzhled podpisového řádku?
Rozhodně! Můžete upravit různé možnosti v `SignatureLineOptions` aby vyhovovaly vašemu stylu a požadavkům.

### Co když nemám certifikát PFX?
Budete si ho muset pořídit od důvěryhodné certifikační autority, protože je nezbytný pro digitální podepisování dokumentů.

### Mohu do dokumentu přidat více řádků podpisu?
Ano, můžete přidat více řádků podpisu opakováním procesu vkládání s různými možnostmi.

### Je Aspose.Words pro .NET kompatibilní s .NET Core?
Ano, Aspose.Words pro .NET podporuje .NET Core, takže je všestranný pro různá vývojová prostředí.

### Jak bezpečné jsou digitální podpisy?
Digitální podpisy vytvořené pomocí Aspose.Words jsou vysoce bezpečné, pokud používáte platný a důvěryhodný certifikát.