---
"description": "Ez az útmutató lépésről lépésre bemutatja az utasításokat és a mintakódot, amelyek segítenek hatékonyan létrehozni 1Bpp indexelt képeket archiváláshoz, nyomtatáshoz vagy helytakarékossági célokra."
"linktitle": "1Bpp indexelt létrehozása"
"second_title": "Aspose.Words dokumentumfeldolgozó API"
"title": "1Bpp indexelt létrehozása"
"url": "/hu/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## Bevezetés

Előfordult már, hogy fekete-fehér képpé kellett konvertálnod egy Word-dokumentumot? Akár digitális archiválásról, nyomtatásról vagy egyszerűen helytakarékosságról van szó, a dokumentumok 1 Bpp-s indexelt képpé konvertálása hihetetlenül hasznos lehet. Ebben az útmutatóban egy egyszerű módszert mutatunk be, amellyel ezt az Aspose.Words for .NET használatával érheted el. Kezdjük is!

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjünk meg arról, hogy a következőkkel rendelkezünk:

- Aspose.Words .NET-hez: Töltse le és telepítse a könyvtárat innen: [itt](https://releases.aspose.com/words/net/).
- .NET fejlesztői környezet: Bár a Visual Studio népszerű választás, bármilyen .NET-et támogató IDE működni fog.
- C# alapismeretek: A C# ismerete előnyös, de a dolgokat egyszerűen fogjuk tartani.
- Minta Word-dokumentum: Készítsen elő egy dokumentumot az átalakításhoz.

## 1. lépés: A szükséges névterek importálása

Az Aspose.Words használatához importálni kell a vonatkozó névtereket. Ez elengedhetetlen a dokumentumkezeléshez szükséges osztályok és metódusok eléréséhez.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 2. lépés: Dokumentumkönyvtár beállítása

Adja meg annak a könyvtárnak az elérési útját, ahol a Word-dokumentumot tárolja, és azt a helyet, ahová a konvertált képet menteni szeretné.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## 3. lépés: Töltse be a Word dokumentumot

Töltsd be a Word dokumentumodat egy `Aspose.Words.Document` objektum. Ez az objektum lehetővé teszi a dokumentum programozott kezelését.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4. lépés: Képmentési beállítások konfigurálása

Ezután állítsa be a `ImageSaveOptions` ..., hogy meghatározza, hogyan kerüljön mentésre a dokumentum képként. PNG formátumban fogjuk menteni 1Bpp indexelt színmóddal.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // Csak az első oldal konvertálása
    ImageColorMode = ImageColorMode.BlackAndWhite, // Fekete-fehérre állítva
    PixelFormat = ImagePixelFormat.Format1bppIndexed // 1Bpp indexelt formátum használata
};
```

- SaveFormat.Png: Megadja, hogy a kimeneti formátum PNG lesz.
- PageSet(1): Azt jelzi, hogy a dokumentumnak csak az első oldala kerül konvertálásra.
- ImageColorMode.BlackAndWhite: Biztosítja, hogy a kép fekete-fehér legyen.
- ImagePixelFormat.Format1bppIndexed: A pixelformátumot 1Bpp indexelt értékre állítja be, optimalizálva a helykihasználást.

## 5. lépés: Mentse el a dokumentumot képként

Végül használd a `Save` a módszer `Document` objektum a konvertált kép mentéséhez.

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## Következtetés

Gratulálunk! Sikeresen konvertáltál egy Word dokumentumot 1 Bpp méretű indexelt képpé az Aspose.Words for .NET segítségével. Ez a módszer nemcsak hatékony, de segít nagy kontrasztú képek létrehozásában is, amelyek különféle alkalmazásokhoz alkalmasak. Nyugodtan integráld ezt a funkciót a projektjeidbe. Jó kódolást!

## GYIK

### Mi az az 1Bpp indexelt kép?
Az 1Bpp (1 bit pixelenként) indexelt kép egy fekete-fehér képformátum, ahol minden pixelt egyetlen bit, 0 vagy 1 jelöl. Ez a formátum rendkívül helytakarékos, így ideális archiváláshoz.

### Konvertálhatok egyszerre több oldalt egy Word dokumentumból?
Igen! Egyszerűen módosítsa a `PageSet` ingatlan a `ImageSaveOptions` több oldal beillesztéséhez, vagy a teljes dokumentum konvertálásának beállításához.

### Szükségem van licencre az Aspose.Words for .NET használatához?
Igen, a teljes funkcionalitáshoz licenc szükséges. Szerezhet egyet. [ideiglenes jogosítvány itt](https://purchase.aspose.com/temporary-license/).

### Milyen más képformátumokba konvertálhatom a Word-dokumentumomat?
Az Aspose.Words számos formátumot támogat, beleértve a JPEG, BMP és TIFF formátumokat. Csak változtassa meg a `SaveFormat` a `ImageSaveOptions` a kívánt formátumba.

### Hol találok további dokumentációt az Aspose.Words for .NET-ről?
Átfogó dokumentációért látogassa meg a [Aspose.Words .NET dokumentációs oldal](https://reference.aspose.com/words/net/).