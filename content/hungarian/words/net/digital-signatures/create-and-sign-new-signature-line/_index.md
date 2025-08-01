---
"description": "Ismerje meg, hogyan adhat zökkenőmentesen digitális aláírást Word-dokumentumaihoz az Aspose.Words for .NET segítségével. Ez az átfogó oktatóanyag mindent lefed a környezet beállításától és az aláírássor beszúrásától kezdve az aláírt dokumentumok mentéséig és ellenőrzéséig."
"linktitle": "Új aláírási sor létrehozása és aláírása"
"second_title": "Aspose.Words dokumentumfeldolgozó API"
"title": "Új aláírási sor létrehozása és aláírása"
"url": "/hu/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## Bevezetés

Szeretne digitális aláírást hozzáadni egy Word-dokumentumhoz? Az Aspose.Words for .NET segítségével ez könnyebb, mint gondolná! Ez az oktatóanyag végigvezeti Önt a környezet beállításának, az aláírási sor hozzáadásának és a dokumentum digitális aláírásának lépésein. Kezdjük is!

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjünk meg arról, hogy a következőkkel rendelkezünk:

1. Aspose.Words .NET-hez - [Töltsd le itt](https://releases.aspose.com/words/net/).
2. A .NET fejlesztői környezet – a Visual Studio – ideális erre a feladatra.
3. Aláírandó dokumentum – Létrehozhat egy új Word-dokumentumot, vagy használhat egy meglévőt.
4. Tanúsítványfájl - A `.pfx` A fájl szükséges a digitális aláírásokhoz.
5. Aláírás sor képe (opcionális) – Mellékelhet egy képfájlt az aláíráshoz.

## Szükséges névterek importálása

Az Aspose.Words funkcióinak használatához a következő névtereket kell importálni:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## 1. lépés: A dokumentumkönyvtár beállítása

Kezd azzal, hogy megadod a dokumentumkönyvtár elérési útját. Ide fogod menteni és ide fogod visszakeresni a dokumentumokat.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Adja meg a dokumentum könyvtárának elérési útját
```

## 2. lépés: Új dokumentum létrehozása

Következő lépésként hozzunk létre egy új Word-dokumentumot. Ez a dokumentum fog szolgálni az aláírássorod vászonként.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Az aláírás sor beszúrása

Most használd a `DocumentBuilder` osztály aláírási sor beszúrásához a dokumentumba:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 4. lépés: A dokumentum mentése

Miután beszúrta az aláírási sort, mentse el a dokumentumot. Ez egy kulcsfontosságú lépés az aláírás előtt.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## 5. lépés: Aláírási beállítások konfigurálása

Állítsa be az aláírási folyamat beállításait. Ez magában foglalja az aláírási sor azonosítójának és az aláírással megjelenítendő opcionális képnek a megadását.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // A képhez vezető út
};
```

## 6. lépés: A tanúsítvány betöltése

Töltse be a dokumentum aláírásához szükséges tanúsítványfájlt:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // Fájlnév és jelszó módosítása
```

## 7. lépés: A dokumentum aláírása

Végül írja alá a dokumentumot a `DigitalSignatureUtil` osztály. Mentse el az aláírt dokumentumot új néven későbbi felhasználás céljából.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## Következtetés

Gratulálunk! Sikeresen létrehoztál egy Word-dokumentumot, hozzáadtál egy aláírási sort, és digitálisan aláírtad az Aspose.Words for .NET segítségével. Ez a hatékony eszköz leegyszerűsíti a dokumentumautomatizálást, biztosítva, hogy a szerződéseid és hivatalos dokumentumaid biztonságosan alá legyenek írva és hitelesítve.

## GYIK

### Használhatok más képformátumokat az aláírássorhoz?

Igen, különféle képformátumokat használhat, beleértve a PNG-t, JPG-t és BMP-t.

### Szükséges-e használni egy `.pfx` fájl a tanúsítványhoz?

Igen, egy `.pfx` A fájl egy szabványos formátum a digitális aláírásokhoz tartozó tanúsítványok és privát kulcsok tárolására.

### Hozzáadhatok több aláírási sort egyetlen dokumentumhoz?

Természetesen! Több aláírási sort is beszúrhat a beszúrási lépés szükség szerinti megismétlésével.

### Mi van, ha nincs digitális tanúsítványom?

Digitális tanúsítványt kell beszereznie egy megbízható hitelesítésszolgáltatótól, vagy létre kell hoznia egyet olyan eszközökkel, mint az OpenSSL.

### Hogyan tudom ellenőrizni a dokumentumban lévő digitális aláírást?

A digitális aláírást úgy ellenőrizheti, hogy megnyitja az aláírt dokumentumot a Wordben, és ellenőrzi az aláírás adatait a hitelesség és az integritás megerősítése érdekében.