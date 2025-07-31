---
"description": "Ismerje meg, hogyan valósíthatja meg az optikai karakterfelismerést (OCR) .NET alkalmazásaiban az Aspose.OCR segítségével. Ez az átfogó útmutató végigvezeti Önt a felismert vonalak téglalapjainak kinyerésének folyamatán."
"linktitle": "Vonaltéglalapok kinyerése képekből Felismerés"
"second_title": "Aspose.OCR .NET API"
"title": "Vonaltéglalapok kinyerése képekből Felismerés"
"url": "/hu/ocr/net/master-image-and-drawing-recognition/line-rectangles-from-images-recognition/"
"weight": 10
---

## Bevezetés

Üdvözlünk az Aspose.OCR for .NET világában, egy lenyűgöző eszközben, amelyet az optikai karakterfelismerés (OCR) integrálására terveztek a .NET alkalmazásokba. Akár tapasztalt fejlesztő, akár kíváncsi kezdő, ez az útmutató végigvezet a képeken található felismert szövegből vonalak ábrázolására szolgáló téglalapok létrehozásának lépésein.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következők a helyén vannak:

- C# és .NET fejlesztési alapismeretek.
- Integrált fejlesztői környezet (IDE), mint például a Visual Studio.
- Az Aspose.OCR for .NET könyvtár telepítve van. Letöltheti. [itt](https://releases.aspose.com/ocr/net/).
- Egy felismerhető szöveget tartalmazó mintakép.

## Kötelező névterek

Kezdéshez hozzá kell adnod a szükséges névtereket a projektedhez. Írd be ezeket a sorokat a C# fájlod elejére:

```csharp
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using Aspose.OCR;
```

Kövesse az alábbi lépéseket az OCR-képben lévő vonalak téglalapjainak lekéréséhez.

## 1. lépés: Dokumentumkönyvtár beállítása

Add meg a képfájl mappáját:

```csharp
// Adja meg a dokumentumkönyvtár elérési útját
string dataDir = "Your Document Directory";
```

Mindenképpen cserélje ki `"Your Document Directory"` a tényleges úttal.

## 2. lépés: Az Aspose.OCR inicializálása

Hozz létre egy példányt a `AsposeOcr` osztály a funkcióinak eléréséhez:

```csharp
// Az Aspose.OCR API inicializálása
AsposeOcr api = new AsposeOcr();
```

## 3. lépés: Adja meg a kép elérési útját

Adja meg a feldolgozni kívánt képfájl teljes elérési útját:

```csharp
// Adja meg a kép teljes elérési útját
string fullPath = dataDir + "sample.png";
```

## 4. lépés: Kép felismerése és téglalapok lekérése vonalakhoz

Most már használhatod a `GetRectangles` metódus a felismert szövegsorok téglalapjainak kinyerésére:

```csharp
// Téglalapok lekérése a megadott kép vonalaihoz
List<Rectangle> lines = api.GetRectangles(fullPath, AreasType.LINES, false);
```

## 5. lépés: Az eredmények kimenete

Végül írasd ki az egyes detektált vonaltéglalapok koordinátáit a konzolra:

```csharp
// A detektált téglalapok koordinátáinak megjelenítése
Console.WriteLine("Areas coordinates:");
lines.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
```

## Következtetés

Gratulálunk! Sikeresen visszakerested a téglalapokat egy OCR kép vonalaihoz az Aspose.OCR for .NET segítségével. Ez a technológia számos lehetőséget nyit meg a szöveg kinyerésére és feldolgozására az alkalmazásaidban.

## GYIK

### Használhatom az Aspose.OCR for .NET-et bármilyen típusú képpel?

Igen, az Aspose.OCR különféle képformátumokat támogat, rugalmasságot biztosítva az OCR alkalmazások számára.

### Mekkora az OCR-felismerés pontossági aránya?

Az Aspose.OCR fejlett algoritmusokat használ a szövegfelismerés nagy pontosságának eléréséhez, így sokféle helyzetben alkalmazható.

### Elérhető próbaverzió?

Igen, az Aspose.OCR for .NET funkcióit a következő letöltésével fedezheti fel: [ingyenes próba](https://releases.aspose.com/).

### Hol találok részletes dokumentációt?

Átfogó dokumentáció található [itt](https://reference.aspose.com/ocr/net/), részletes információkat és útmutatásokat kínálva.

### További segítségre van szüksége, vagy kérdései vannak?

Csatlakozzon a beszélgetéshez a [Aspose.OCR fórum](https://forum.aspose.com/c/ocr/16) közösségi támogatásért.