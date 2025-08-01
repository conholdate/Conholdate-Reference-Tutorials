---
"description": "Tanuld meg, hogyan hozhatsz létre és szabhatsz testre primitív 3D modelleket, beleértve a dobozokat és a hengereket, és hogyan mentheted el őket könnyedén FBX formátumban."
"linktitle": "Primitív 3D modellezés létrehozása"
"second_title": "Aspose.3D .NET API"
"title": "Primitív 3D modellezés létrehozása"
"url": "/hu/3d/net/guide-to-3d-modeling/create-primitive-3d-modeling/"
"weight": 10
---

## Bevezetés

Üdvözlünk a 3D modellezés magával ragadó világában az Aspose.3D for .NET használatával! Ebben az átfogó oktatóanyagban lépésről lépésre végigvezetünk a primitív 3D modellek létrehozásának folyamatán. Akár tapasztalt fejlesztő, akár tanulni vágyó kezdő, ez az útmutató segít abban, hogy vizuálisan lenyűgöző 3D elemeket hozzon létre projektjeihez.

## Előfeltételek

Mielőtt belevágna a 3D modellezésbe, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Aspose.3D .NET-hez: Töltse le és telepítse az Aspose.3D .NET-hez könyvtárat a következő helyről: [letöltési oldal](https://releases.aspose.com/3d/net/).
  
- .NET fejlesztői környezet: Állítson be egy Aspose.3D-vel kompatibilis környezetet, például a Visual Studio-t.

Mindennel előkészülve, vágjunk bele a 3D modellezési kalandunkba!

## Szükséges névterek importálása

Kezdje a szükséges névterek importálásával az Aspose.3D funkcióinak eléréséhez:

```csharp
using System;
using System.IO;
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
```

Ezek a névterek biztosítják a 3D modellek kezeléséhez és alkotásaid mentéséhez szükséges eszközöket.

## 1. lépés: Jelenetobjektum inicializálása

Hozz létre egy új jelenetobjektumot, amely a 3D modellek vászonjaként szolgál:

```csharp
// Jelenet objektum inicializálása
Scene scene = new Scene();
```

Ez a jelenet fogja tartalmazni a létrehozni kívánt primitív formákat.

## 2. lépés: Dobozmodell létrehozása

Következő lépésként adjunk hozzá egy dobozmodellt a jelenethez:

```csharp
// Dobozmodell létrehozása
scene.RootNode.CreateChildNode("box", new Box());
```

A doboz méreteit és tulajdonságait testreszabhatod a kreatív elképzeléseidnek megfelelően.

## 3. lépés: Hengermodell létrehozása

Most pedig egészítsd ki a jelenetedet egy henger hozzáadásával:

```csharp
// Hengermodell létrehozása
scene.RootNode.CreateChildNode("cylinder", new Cylinder());
```

A dobozhoz hasonlóan a henger paramétereit is szabadon állíthatod a kívánt megjelenés eléréséhez.

## 4. lépés: Mentse el a jelenetet FBX formátumban

A 3D modell megőrzéséhez mentse el FBX formátumban:

```csharp
// Rajz mentése FBX formátumban
var output = Path.Combine("Your Output Directory", "test.fbx");
scene.Save(output, FileFormat.FBX7500ASCII);
```

Győződjön meg róla, hogy a modelljének megfelelő kimeneti könyvtárat és fájlnevet választ.

## 5. lépés: Sikeres üzenet megjelenítése

Végül ünnepelje meg sikerét egy üzenet megjelenítésével:

```csharp
// Sikeres üzenet megjelenítése
Console.WriteLine($"\nBuilding a scene from primitive 3D models was successful.\nFile saved at {output}");
```

primitív modellekből összeállított 3D-s jelenet elkészült és mentésre került!

## Következtetés

Gratulálunk a lenyűgöző 3D modellek létrehozásához az Aspose.3D for .NET segítségével! Ez az oktatóanyag a primitív modellezés alapjait ismertette, de a lehetőségek végtelenek. Fedezzen fel többet a haladó funkciókról és technikákról a következőben: [dokumentáció](https://reference.aspose.com/3d/net/).

## GYIK

### Használhatom az Aspose.3D for .NET-et .NET-től eltérő programozási nyelvekkel?

Az Aspose.3D főként .NET-et támogat, de vannak Java és más platformokra készült verziók is.

### Ingyenes próbaverzió elérhető?

Igen, kipróbálhatod az Aspose.3D képességeit egy [ingyenes próba](https://releases.aspose.com/).

### Hol találok támogatást az Aspose.3D for .NET-hez?

Közösségi támogatásért látogassa meg a [Aspose.3D fórum](https://forum.aspose.com/c/3d/18).

### Hogyan szerezhetek ideiglenes jogosítványt?

Ideiglenes jogosítványt kérhetsz [itt](https://purchase.conholdate.com/temporary-license/).

### Vannak további oktatóanyagok?

Igen! További oktatóanyagokat és példákat itt találsz: [dokumentáció](https://reference.aspose.com/3d/net/).