---
"description": "Ismerje meg, hogyan mentheti hatékonyan a Microsoft OneNote dokumentumokat PDF-fájlként az Aspose.Note for .NET segítségével. Ez az útmutató végigvezeti a szükséges előfeltételeken, és hasznos GYIK-et is tartalmaz."
"linktitle": "OneNote dokumentumok mentése PDF formátumban"
"second_title": "Aspose.Note .NET API"
"title": "OneNote dokumentumok mentése PDF formátumban az Aspose.Note for .NET használatával"
"url": "/hu/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Bevezetés

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan menthetünk dokumentumokat PDF formátumba az Aspose.Note for .NET segítségével. Az Aspose.Note egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft OneNote fájlokkal. Áttekintjük az előfeltételeket, importáljuk a névtereket, és lépésről lépésre bemutatjuk a dokumentumok PDF formátumba mentéséhez különböző oldalelrendezésekben.

## Előfeltételek
1. Visual Studio: Győződjön meg róla, hogy telepítve van.
2. Aspose.Note .NET-hez: Töltse le és telepítse a könyvtárat.
3. C# ismeretek: A nyelv alapvető ismerete szükséges.

## Szükséges névterek importálása
A folytatás előtt importálja a következő névtereket a kódjába:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## 1. lépés: Mentés PDF-be Letter oldalbeállításokkal
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Frissítse ezt az elérési utat
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Betölti a OneNote dokumentumot, és PDF formátumban menti el Letter méretű oldalbeállításokkal.

## 2. lépés: Mentés PDF-be A4-es oldalbeállításokkal (nincs magasságkorlát)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Frissítse ezt az elérési utat
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Hasonló az 1. lépéshez, de A4-es papírbeállításokat használ magasságkorlátozás nélkül.

## Következtetés
Az oktatóanyag sikeresen bemutatja, hogyan lehet OneNote fájlokat PDF formátumba konvertálni az Aspose.Note segítségével. A különböző oldalbeállítások használatával a fejlesztők rugalmasságot nyerhetnek a dokumentumkezelésben.

## GYIK
### Az Aspose.Note képes kezelni az összetett OneNote fájlokat?
Igen, hatékonyan kezeli az összetett OneNote fájlok különféle funkcióit.

### Alkalmas az Aspose.Note kereskedelmi projektekhez?
Igen, licenc megvásárlása után kereskedelmi célokra is használhatja.

### Az Aspose.Note kínál ingyenes próbaverziót?
Igen, ingyenes próbaverzió áll rendelkezésre a felfedezéshez.

### Hol találok dokumentációt az Aspose.Note-hoz?
Részletes dokumentáció az Aspose referenciaoldalán érhető el.

### További segítségre van szüksége?
Kérdésekért és támogatásért tekintse meg az Aspose.Note fórumot.