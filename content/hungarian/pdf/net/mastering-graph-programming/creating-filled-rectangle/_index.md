---
"description": "Engedd szabadjára a PDF-manipuláció erejét az Aspose.PDF for .NET segítségével ebben a lépésről lépésre bemutató oktatóanyagban. Tanuld meg, hogyan hozhatsz létre programozottan vizuálisan vonzó PDF dokumentumokat kitöltött téglalapok rajzolásával."
"linktitle": "Kitöltött téglalap létrehozása"
"second_title": "Aspose.PDF .NET API referenciafájlhoz"
"title": "Kitöltött téglalap létrehozása"
"url": "/hu/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## Bevezetés

Szerettél volna már vizuálisan lenyűgöző PDF-eket készíteni programozottan? Ha igen, akkor jó helyen jársz! Ebben az oktatóanyagban az Aspose.PDF for .NET-et fogjuk megismerni, egy hatékony könyvtárat, amely leegyszerűsíti a PDF-dokumentumok kezelését. Ma egy kitöltött téglalap létrehozására fogunk összpontosítani egy PDF-fájlon belül. Akár tapasztalt fejlesztő vagy, akár most kezded, ez az útmutató végigvezet minden lépésen barátságos és lebilincselő módon. Szóval, ragadd meg a programozó sapkádat, és kezdjük is el!

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjünk meg arról, hogy a következőkkel rendelkezünk:

1. Visual Studio: Telepítsd a Visual Studio-t a gépedre, mivel kiváló IDE a .NET fejlesztéshez.
2. Aspose.PDF .NET-hez: Töltse le és telepítse az Aspose.PDF könyvtárat innen: [itt](https://releases.aspose.com/pdf/net/).
3. C# alapismeretek: A C# programozással való ismeret segít jobban megérteni a kódrészleteket.

## 1. lépés: Új projekt létrehozása

1. Nyissa meg a Visual Studiot, és hozzon létre egy új konzolalkalmazás-projektet.
2. Nevezd el megfelelően a projektedet.

## 2. lépés: Aspose.PDF referencia hozzáadása

1. Kattintson jobb gombbal a projektjére a Megoldáskezelőben.
2. Válassza a NuGet-csomagok kezelése lehetőséget.
3. Keresd meg az Aspose.PDF fájlt, és telepítsd a legújabb verziót.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Most, hogy mindent beállítottunk, vágjunk bele a kódba!

## 3. lépés: Dokumentumkönyvtár beállítása

Adja meg a PDF mentési útvonalát:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Csere `"YOUR DOCUMENT DIRECTORY"` a gépeden található tényleges elérési úttal, ahová a PDF-et menteni szeretnéd.

## 4. lépés: Dokumentumpéldány létrehozása

Új PDF dokumentum inicializálása:

```csharp
// Dokumentumpéldány létrehozása
Document doc = new Document();
```

## 5. lépés: Oldal hozzáadása a dokumentumhoz

Minden PDF-nek legalább egy oldalnak kell lennie. Adjunk hozzá egyet:

```csharp
// Oldal hozzáadása PDF fájl oldalak gyűjteményéhez
Page page = doc.Pages.Add();
```

## 6. lépés: Grafikonpéldány létrehozása

Egy `Graph` a példány vászonként szolgál alakzatok rajzolásához:

```csharp
// Graph-példány létrehozása
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## 7. lépés: Grafikon hozzáadása az oldalhoz

Csatold a grafikont az oldalhoz:

```csharp
// Grafikus objektum hozzáadása az oldalpéldány bekezdésgyűjteményéhez
page.Paragraphs.Add(graph);
```

## 8. lépés: Téglalap alakú példány létrehozása

Adja meg a téglalap helyét és méretét:

```csharp
// Téglalap példány létrehozása
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## 9. lépés: Adja meg a kitöltési színt

Válassz egy színt a téglalapnak. Ebben a példában a pirosat fogjuk használni:

```csharp
// Adja meg a Graph objektum kitöltési színét
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 10. lépés: Téglalap hozzáadása a grafikonhoz

Adjuk hozzá a téglalapot a grafikonhoz:

```csharp
// Téglalap objektum hozzáadása a Graph objektum alakzatgyűjteményéhez
graph.Shapes.Add(rect);
```

## 11. lépés: Mentse el a PDF dokumentumot

Végül mentse el a dokumentumot a megadott könyvtárba:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);
```

## 12. lépés: Megerősítő üzenet

Nyomtasson ki egy visszaigazoló üzenetet a siker jelzésére:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálunk! Sikeresen létrehoztál egy kitöltött téglalapot egy PDF dokumentumban az Aspose.PDF for .NET segítségével. Ez a hatékony könyvtár a PDF-manipuláció új lehetőségeinek tárházát nyitja meg, lehetővé téve lenyűgöző dokumentumok programozott létrehozását. Akár jelentéseket, számlákat vagy bármilyen más típusú PDF-et készítesz, az Aspose.PDF segít neked.

## GYIK

### Mi az Aspose.PDF .NET-hez?
Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan hozzanak létre, szerkesszenek és konvertáljanak PDF dokumentumokat.

### Ingyenesen használhatom az Aspose.PDF fájlt?
Igen, az Aspose ingyenes próbaverziót kínál, amellyel felfedezheted a könyvtár funkcióit. Letöltheted. [itt](https://releases.aspose.com/).

### Van mód támogatást kérni az Aspose.PDF-hez?
Természetesen! Az Aspose fórumon keresztül kaphatsz támogatást. [itt](https://forum.aspose.com/c/pdf/10).

### Hogyan vásárolhatom meg az Aspose.PDF fájlt?
Az Aspose.PDF fájlt a vásárlási oldalon vásárolhatja meg. [itt](https://purchase.aspose.com/buy).

### Milyen típusú alakzatokat hozhatok létre az Aspose.PDF fájllal?
Az Aspose.PDF könyvtár segítségével különféle alakzatokat hozhat létre, beleértve a téglalapokat, köröket, vonalakat és egyebeket.