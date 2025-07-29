---
"description": "Fedezze fel, hogyan hozhat létre szépen számozott listákat PDF-dokumentumaiban az Aspose.PDF for .NET segítségével. Ez az útmutató végigvezeti Önt a különböző számozási stílusok – például a római számok – alkalmazásának folyamatán."
"linktitle": "Stílusos számozott listák az Aspose.PDF for .NET használatával"
"second_title": "Aspose.PDF .NET API referenciafájlhoz"
"title": "Stílusos számozott listák az Aspose.PDF for .NET használatával"
"url": "/hu/net/programming-with-headings/stylish-numbered-lists/"
"weight": 10
---

## Bevezetés

Előfordult már, hogy jól strukturált, számozott listákat kellett létrehoznia PDF-dokumentumaiban? Legyen szó jogi dokumentumokról, jelentésekről vagy prezentációkról, a hatékony számozási stílusok elengedhetetlenek a tartalom rendszerezéséhez. Az Aspose.PDF for .NET segítségével könnyedén alkalmazhat különféle számozási stílusokat PDF-címsoraira, ami letisztult és professzionális dokumentumokat eredményez.

## Előfeltételek

Mielőtt belevágnánk a kódolásba, győződjünk meg róla, hogy a következők készen állnak:

1. Aspose.PDF .NET-hez: Töltse le a legújabb verziót innen: [itt](https://releases.aspose.com/pdf/net/).
2. Fejlesztői környezet: Szükséged lesz a Visual Studio-ra vagy bármilyen .NET-kompatibilis IDE-re.
3. .NET-keretrendszer: Győződjön meg arról, hogy telepítve van a .NET-keretrendszer 4.0-s vagy újabb verziója.
4. Licenc: Használhat egy ideiglenes licencet a következőtől: [itt](https://purchase.aspose.com/temporary-license/) vagy fedezd fel a [ingyenes próba](https://releases.aspose.com/) opciók.

## Szükséges csomagok importálása

Kezdje a szükséges névterek importálásával a projektjébe:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 1. lépés: A dokumentum beállítása

Kezdjük egy új PDF dokumentum létrehozásával és az elrendezésének konfigurálásával, beleértve az oldalméretet és a margókat.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Oldalméretek és margók beállítása
pdfDoc.PageInfo.Width = 612.0; // 8,5 hüvelyk
pdfDoc.PageInfo.Height = 792.0; // 11 hüvelyk
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo(72, 72, 72, 72); // 2,5 cm-es margók
```

Ez a beállítás szabványos levélméretű dokumentumot biztosít, minden oldalon egy hüvelykes margókkal.

## 2. lépés: Oldal hozzáadása a PDF-hez

Ezután hozzáadunk egy üres oldalt a PDF dokumentumhoz, ahol később a számozási stílusokat fogjuk alkalmazni.

```csharp
// Új oldal hozzáadása a PDF dokumentumhoz
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo = pdfDoc.PageInfo; // Használja ugyanazokat a beállításokat, mint a dokumentum
```

## 3. lépés: Lebegő doboz létrehozása

A FloatingBox lehetővé teszi a tartalom elhelyezését az oldal folyásától függetlenül, így nagyobb kontrollt biztosít az elrendezés felett.

```csharp
// Hozz létre egy FloatingBox-ot strukturált tartalomhoz
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox
{
    Margin = pdfPage.PageInfo.Margin
};
pdfPage.Paragraphs.Add(floatBox);
```

## 4. lépés: Címsorok hozzáadása római számokkal

Most adjuk hozzá az első címsort kisbetűs római számokkal.

```csharp
// Hozd létre az első címsort római számokkal
Aspose.Pdf.Heading heading1 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 1,
    Text = "List 1",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading1);
```

## 5. lépés: Második címsor hozzáadása egyéni kezdőszámmal

Ezután hozzáadunk egy második címsort, a római 13-as számmal kezdve.

```csharp
// Hozz létre egy második címsort, amely a római 13-as számmal kezdődik
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 13,
    Text = "List 2",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading2);
```

## 6. lépés: Címsor hozzáadása betűrendes számozással

A változatosság kedvéért adjunk hozzá egy harmadik címsort, amely kisbetűs betűrendes számozást használ.

```csharp
// Hozzon létre egy címsort betűrendes számozással
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2)
{
    IsInList = true,
    StartNumber = 1,
    Text = "The value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed",
    Style = NumberingStyle.LettersLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading3);
```

## 7. lépés: A PDF mentése

Végül mentsük el a PDF fájlt a kívánt könyvtárba.

```csharp
// PDF dokumentum mentése
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine($"\nNumber style applied successfully in headings.\nFile saved at {dataDir}");
```

## Következtetés

Gratulálunk! Sikeresen alkalmaztál különböző számozási stílusokat – római számokat és betűrendet – egy PDF fájl címsoraira az Aspose.PDF for .NET segítségével. Az Aspose.PDF rugalmassága lehetővé teszi az oldalelrendezés, a számozási stílusok és a tartalom elhelyezésének szabályozását, így jól szervezett és professzionális PDF dokumentumokat hozhatsz létre.

## GYIK

### Alkalmazhatok különböző számstílusokat ugyanarra a PDF dokumentumra?  
Igen, ugyanazon dokumentumon belül keverhet különböző számozási stílusokat, például római számokat, arab számokat és betűrendes számozást.

### Hogyan tudom testreszabni a címsorok kezdőszámát?  
Bármely címsor kezdőszámát beállíthatja a `StartNumber` ingatlan.

### Van mód a számozási sorrend visszaállítására?  
Igen, a számozást visszaállíthatja a `StartNumber` tulajdonság minden címsorhoz.

### Alkalmazhatok félkövér vagy dőlt betűstílust a címsorokra a számozás mellett?  
Természetesen! A címsorstílusokat testreszabhatja olyan tulajdonságok módosításával, mint a betűtípus, méret, félkövér és dőlt betűtípus a `TextState` objektum.

### Hogyan szerezhetek ideiglenes licencet az Aspose.PDF fájlhoz?  
Ideiglenes jogosítványt igényelhetsz [itt](https://purchase.aspose.com/temporary-license/) az Aspose.PDF korlátozás nélküli tesztelésére.