---
"description": "Naučte se, jak bez problémů přidat digitální podpis do dokumentů Wordu pomocí Aspose.Words pro .NET. Tento komplexní tutoriál zahrnuje vše od nastavení prostředí a vložení řádku pro podpis až po ukládání a ověřování podepsaných dokumentů."
"linktitle": "Vytvořit a podepsat nový řádek podpisu"
"second_title": "Rozhraní API pro zpracování dokumentů Aspose.Words"
"title": "Vytvořit a podepsat nový řádek podpisu"
"url": "/cs/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## Zavedení

Chcete přidat digitální podpis do dokumentu Wordu? S Aspose.Words pro .NET je to jednodušší, než si myslíte! Tento tutoriál vás provede kroky nastavení prostředí, přidání řádku pro podpis a digitálního podepsání dokumentu. Pojďme na to!

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte následující:

1. Aspose.Words pro .NET - [Stáhněte si to zde](https://releases.aspose.com/words/net/).
2. Vývojové prostředí .NET – Visual Studio je pro tento úkol ideální.
3. Dokument k podpisu – Můžete vytvořit nový dokument aplikace Word nebo použít existující.
4. Soubor certifikátu - A `.pfx` Soubor je nezbytný pro digitální podpisy.
5. Obrázek řádku podpisu (volitelné) – Můžete přidat soubor s obrázkem podpisu.

## Importovat požadované jmenné prostory

Abyste mohli používat funkce Aspose.Words, je třeba importovat následující jmenné prostory:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Krok 1: Nastavení adresáře dokumentů

Začněte definováním cesty k adresáři s dokumenty. Zde budete ukládat a načítat své dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zadejte cestu k adresáři dokumentů
```

## Krok 2: Vytvoření nového dokumentu

Dále si vytvořme nový dokument Wordu. Tento dokument bude sloužit jako plátno pro váš podpisový řádek.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložení řádku pro podpis

Nyní použijte `DocumentBuilder` třída pro vložení řádku podpisu do dokumentu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Krok 4: Uložení dokumentu

Jakmile vložíte řádek pro podpis, uložte dokument. Toto je klíčový krok před podpisem.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Krok 5: Konfigurace možností podepisování

Nastavte možnosti pro proces podepisování. To zahrnuje zadání ID řádku podpisu a volitelného obrázku, který se má zobrazit s podpisem.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // Cesta k vašemu obrázku
};
```

## Krok 6: Načtení certifikátu

Načtěte soubor certifikátu potřebný k podepsání dokumentu:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // Upravte název souboru a heslo
```

## Krok 7: Podepsání dokumentu

Nakonec dokument podepište pomocí `DigitalSignatureUtil` třída. Podepsaný dokument uložte pod novým názvem pro budoucí použití.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## Závěr

Gratulujeme! Úspěšně jste vytvořili dokument Word, přidali řádek pro podpis a digitálně jej podepsali pomocí Aspose.Words pro .NET. Tento výkonný nástroj zjednodušuje automatizaci dokumentů a zajišťuje, že vaše smlouvy a formální dokumenty budou bezpečně podepsány a ověřeny.

## Často kladené otázky

### Mohu pro řádek podpisu použít jiné formáty obrázků?

Ano, můžete použít různé formáty obrázků, včetně PNG, JPG a BMP.

### Je nutné použít `.pfx` soubor pro certifikát?

Ano, a `.pfx` soubor je standardní formát pro ukládání certifikátů a soukromých klíčů pro digitální podpisy.

### Mohu do jednoho dokumentu přidat více řádků podpisu?

Rozhodně! Více řádků podpisu můžete vložit opakováním kroku vkládání podle potřeby.

### Co když nemám digitální certifikát?

Budete muset získat digitální certifikát od důvěryhodné certifikační autority nebo si jej vygenerovat pomocí nástrojů, jako je OpenSSL.

### Jak ověřím digitální podpis v dokumentu?

Digitální podpis můžete ověřit otevřením podepsaného dokumentu ve Wordu a kontrolou údajů o podpisu, abyste potvrdili jeho pravost a integritu.