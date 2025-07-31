---
"description": "Fedezze fel, hogyan biztosíthatja Word-dokumentumai egységes megjelenését különböző platformokon a célgép-betűtípusok kihasználásával az Aspose.Words for .NET segítségével."
"linktitle": "Célgép betűtípusok"
"second_title": "Aspose.Words dokumentumfeldolgozó API"
"title": "Célgép-betűtípusok az Aspose.Words for .NET segítségével"
"url": "/hu/words/net/html-fixed-save-options/target-machine-font/"
"weight": 10
---

## Bevezetés

Üdvözlünk az Aspose.Words for .NET lenyűgöző világában! Ma felfedezzük, hogyan használhatjuk a célgép betűtípusait Word dokumentumokkal való munka során. Ez a funkció biztosítja, hogy dokumentumai megőrizzék a kívánt megjelenést, függetlenül attól, hogy hol tekintjük meg őket. Vágjunk bele!

## Előfeltételek

Mielőtt belekezdenénk, győződjünk meg róla, hogy a következőkkel rendelkezünk:

1. Aspose.Words .NET-hez: Győződjön meg róla, hogy telepítve van a könyvtár. Ha még nem tette meg, letöltheti. [itt](https://releases.aspose.com/words/net/).
2. Fejlesztői környezet: Elengedhetetlen egy .NET fejlesztői környezet, mint például a Visual Studio.
3. Dolgozható dokumentum: Készítsen elő egy tesztelésre alkalmas Word-dokumentumot, például a „Felsorolásjelek alternatív betűtípussal.docx” fájlt.

Miután ezek az előfeltételek megvannak, ugorjunk bele a kódba!

## Szükséges névterek importálása

Első lépésként importálnunk kell a szükséges névtereket. Ez a lépés összekapcsolja a projekt összes összetevőjét.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1. lépés: Töltse be a Word dokumentumot

Az első lépés a Word-dokumentum betöltése a következővel: `Document` osztály az Aspose.Words könyvtárból.

### 1.1. lépés: A dokumentum elérési útjának meghatározása

Kezdjük a dokumentumok könyvtárának elérési útjának meghatározásával:

```csharp
// A dokumentumok könyvtárának elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 1.2. lépés: A dokumentum betöltése

Most töltsd be a dokumentumot:

```csharp
// Töltsd be a Word dokumentumot
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

## 2. lépés: Mentési beállítások konfigurálása

Ezután be kell állítanunk a mentési beállításokat, hogy a dokumentumban használt betűtípusok a célgépről származzanak. Létrehozunk egy példányt a következőből: `HtmlFixedSaveOptions` és állítsa be a `UseTargetMachineFonts` ingatlan `true`.

```csharp
// Mentési beállítások konfigurálása a célgép betűtípusainak használatához
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
{
    UseTargetMachineFonts = true
};
```

## 3. lépés: A dokumentum mentése

Most mentsük el a dokumentumot rögzített HTML fájlként. Itt történik a varázslat!

```csharp
// Dokumentum konvertálása fix HTML-re
doc.Save(dataDir + "UsingTargetMachineFonts.html", saveOptions);
```

## 4. lépés: Ellenőrizze a kimenetet

Végül fontos ellenőrizni a kimenetet. Nyissa meg a mentett HTML fájlt egy webböngészőben, és ellenőrizze, hogy a betűtípusok helyesen vannak-e alkalmazva a célgépen.

```csharp
// Nyissa meg a HTML fájlt a kimenet ellenőrzéséhez
System.Diagnostics.Process.Start(dataDir + "UsingTargetMachineFonts.html");
```

És íme! Sikeresen használtad a célgép betűtípusait a Word-dokumentumodban az Aspose.Words for .NET segítségével.

## Következtetés

A célgépről származó betűtípusok kihasználásával biztosítható, hogy a Word-dokumentumok egységes és professzionális megjelenésűek legyenek, függetlenül attól, hogy hol tekintik meg őket. Az Aspose.Words for .NET leegyszerűsíti ezt a folyamatot, lehetővé téve a dokumentumok egyszerű betöltését, a mentési beállítások konfigurálását és a kívánt betűtípus-beállításokkal történő mentését.

## GYIK

### Használhatom ezt a módszert más dokumentumformátumokkal?
Igen, az Aspose.Words for .NET számos dokumentumformátumot támogat, és hasonló mentési beállításokat alkalmazhat a különböző formátumokhoz.

### Mi van, ha a célgépen nincsenek meg a szükséges betűtípusok?
Ha a szükséges betűtípusok hiányoznak a célgépről, előfordulhat, hogy a dokumentum nem jelenik meg helyesen. Célszerű betűtípusokat beágyazni, ha szükséges.

### Hogyan ágyazhatok be betűtípusokat egy dokumentumba?
Betűtípusokat ágyazhat be a következővel: `FontSettings` osztály az Aspose.Words .NET-hez. Lásd a [dokumentáció](https://reference.aspose.com/words/net/) további részletekért.

### Van mód a dokumentum előnézetének megtekintésére mentés előtt?
Igen, a `DocumentRenderer` osztály lehetővé teszi a dokumentum előnézetét mentés előtt. Nézze meg az Aspose.Words .NET-hez készült fájlt. [dokumentáció](https://reference.aspose.com/words/net/) további információkért.

### Testreszabhatom tovább a HTML kimenetet?
Abszolút! A `HtmlFixedSaveOptions` osztály különféle tulajdonságokat biztosít a HTML-kimenet testreszabásához. Fedezze fel a [dokumentáció](https://reference.aspose.com/words/net/) az összes elérhető opcióhoz.