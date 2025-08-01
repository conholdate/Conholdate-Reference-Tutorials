---
"description": "Fedezze fel, hogyan adhat hozzá programozott aláírássorokat Word-dokumentumaihoz az Aspose.Words for .NET segítségével. Ez az átfogó útmutató mindent lefed a fejlesztői környezet beállításától kezdve az aláírássorok beszúrásán át a dokumentumok biztonságos aláírásáig."
"linktitle": "Új digitális aláírás sor létrehozása és a szolgáltató azonosítójának beállítása"
"second_title": "Aspose.Words dokumentumfeldolgozó API"
"title": "Új digitális aláírás sor létrehozása és a szolgáltató azonosítójának beállítása"
"url": "/hu/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Bevezetés

Üdvözlünk tech-rajongók! Szeretted volna már automatizálni az aláírási sorok beillesztését a Word-dokumentumaidba? Ma belemerülünk abba, hogyan lehet ezt az Aspose.Words for .NET segítségével elérni. Ez a lépésről lépésre szóló útmutató végigvezet az aláírási sor létrehozásán és a szolgáltatói azonosító beállításán, így a dokumentumfeldolgozási feladataid hatékonyabbak és egyszerűbbek lesznek.

## Előfeltételek

Mielőtt belevágnánk, győződjünk meg róla, hogy minden elő van készítve:

1. Aspose.Words .NET-hez: Ha még nem telepítetted, töltsd le [itt](https://releases.aspose.com/words/net/).
2. Fejlesztői környezet: Használjon Visual Studio-t vagy bármilyen C# fejlesztői környezetet.
3. .NET-keretrendszer: Győződjön meg arról, hogy a .NET-keretrendszer telepítve van a gépén.
4. PFX tanúsítvány: Dokumentumok aláírásához PFX tanúsítványra lesz szüksége, amelyet egy megbízható hitelesítésszolgáltatótól szerezhet be.

## Szükséges névterek importálása

Első lépésként importáld a szükséges névtereket a C# projektedbe:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Most pedig merüljünk el az új aláírási sor létrehozásának és a szolgáltatói azonosító beállításának részleteiben.

## 1. lépés: Új dokumentum létrehozása

Először is létre kell hoznunk egy új Word dokumentumot, amely az aláírási sorunk vászonjaként szolgál majd:

```csharp
// Adja meg a dokumentumok könyvtárának elérési útját.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Itt inicializálunk egy újat `Document` és egy `DocumentBuilder`, ami lehetővé teszi számunkra, hogy könnyen hozzáadjunk elemeket.

## 2. lépés: Aláírási sor beállításainak meghatározása

Ezután meghatározzuk az aláírási sor beállításait, beleértve az aláíró nevét, beosztását, e-mail címét és egyéb releváns adatokat:

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

Ezek a beállítások segítenek személyre szabni az aláírási sort, így az világos és professzionális.

## 3. lépés: Az aláírás sor beillesztése

Miután a lehetőségeink készen állnak, beilleszthetjük az aláírás sort a dokumentumba:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

A `InsertSignatureLine` A metódus hozzáadja az aláírási sort, és hozzárendelünk egy egyedi szolgáltatói azonosítót.

## 4. lépés: Mentse el a dokumentumot

Az aláírás sor beillesztése után mentsük el a dokumentumot:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Ez a dokumentumot az újonnan hozzáadott aláírássorral menti.

## 5. lépés: Aláírási beállítások megadása

Most konfiguráljuk az aláírási beállításokat, beleértve az aláírási sor azonosítóját, a szolgáltató azonosítóját, a megjegyzéseket és az aláírás időpontját:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Ezek a beállítások biztosítják, hogy a dokumentum a megfelelő adatokkal legyen aláírva.

## 6. lépés: Tanúsítványtulajdonos létrehozása

A dokumentum aláírásához létre kell hoznunk egy tanúsítványtulajdonost a PFX tanúsítvány használatával:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Csere `"morzal.pfx"` a tényleges tanúsítványfájl nevével és `"aw"` a tanúsítványod jelszavával.

## 7. lépés: A dokumentum aláírása

Végül aláírjuk a dokumentumot a digitális aláírás segédprogrammal:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Ez a folyamat aláírja a dokumentumot, és új fájlként menti el.

## Következtetés

Gratulálunk! Sikeresen létrehozta az aláírási sort és beállította a szolgáltatói azonosítót egy Word-dokumentumban az Aspose.Words for .NET használatával. Ez a hatékony függvénytár leegyszerűsíti a dokumentumfeldolgozási feladatokat, hatékonyabbá téve a munkafolyamatot. Próbálja ki, és nézze meg, hogyan segíthet a projektjeinek fejlesztésében!

## GYIK

### Testreszabhatom az aláírássor megjelenését?
Természetesen! Különböző beállításokat módosíthatsz a `SignatureLineOptions` hogy illeszkedjen a stílusodhoz és az igényeidhez.

### Mi van, ha nincs PFX tanúsítványom?
Megbízható hitelesítésszolgáltatótól kell beszereznie egyet, mivel ez elengedhetetlen a dokumentumok digitális aláírásához.

### Hozzáadhatok több aláírási sort egy dokumentumhoz?
Igen, több aláírási sort is hozzáadhat a beszúrási folyamat különböző beállításokkal történő megismétlésével.

### Kompatibilis az Aspose.Words for .NET a .NET Core-ral?
Igen, az Aspose.Words for .NET támogatja a .NET Core-t, így sokoldalúan használható különféle fejlesztési környezetekben.

### Mennyire biztonságosak a digitális aláírások?
Az Aspose.Words segítségével létrehozott digitális aláírások rendkívül biztonságosak, feltéve, hogy érvényes és megbízható tanúsítványt használ.