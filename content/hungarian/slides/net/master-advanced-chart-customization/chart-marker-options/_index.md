---
"description": "Ismerd meg, hogyan gazdagíthatod PowerPoint-diagramjaidat testreszabott jelölőbeállításokkal az Aspose.Slides for .NET segítségével. Ez a lépésről lépésre haladó útmutató bemutatja az előfeltételeket, a diagramkészítést, az adatpontok formázását és egyebeket."
"linktitle": "Diagramjelölő beállítások adatpontokon az Aspose.Slides .NET-ben"
"second_title": "Aspose.Slides .NET PowerPoint feldolgozási API"
"title": "Diagramjelölő beállítások adatpontokon az Aspose.Slides .NET-ben"
"url": "/hu/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## Bevezetés

A vizuális segédeszközök beépítése a prezentációkba elengedhetetlen a hatásos kommunikációhoz. Az Aspose.Slides for .NET robusztus eszközöket biztosít diagramok létrehozásához és testreszabásához, lehetővé téve a fejlesztők számára az adatprezentációk fejlesztését. Az egyik kiemelkedő funkció a diagramjelölők használata az adatpontokon, ami lehetővé teszi a professzionális megjelenésű diagramok precíz testreszabását. Ez a cikk végigvezeti Önt minden szükséges lépésen.

## Előfeltételek

Mielőtt folytatná, győződjön meg a következőkről:

- Aspose.Slides .NET-hez telepítve: Töltse le innen: [itt](https://releases.aspose.com/slides/net/).
- Alapbeállítás: Egy prezentációs fájl, például a „Test.pptx”, a munkakönyvtáradban.
- Fejlesztői környezet: Visual Studio vagy azzal egyenértékű, .NET-hez konfigurálva.

## Szükséges névterek importálása

Adja hozzá a szükséges névtereket a projekthez a zökkenőmentes fejlesztés érdekében:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## 1. lépés: Diagram létrehozása a prezentációban

Kezdésként hozzon létre egy alapértelmezett diagramot a bemutató első diáján:

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

Ez hozzáad egy `LineWithMarkers` diagramot a diára a megadott méretekkel.

## 2. lépés: A diagramadat-munkalap indexének lekérése

Az alapértelmezett diagramadat-munkalap indexe elengedhetetlen a további testreszabáshoz:

```csharp
int defaultWorksheetIndex = 0;
```

## 3. lépés: A Diagramadatok munkafüzet elérése

A diagramadatok kezeléséhez kérd le a társított munkafüzetet:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## 4. lépés: Diagramsorozat konfigurálása és adatpontok hozzáadása

Töröld az alapértelmezett sorozatot, és adj hozzá új adatpontokat a sorozatodhoz:

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Adatpontok hozzáadása a sorozathoz
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## 5. lépés: Képkitöltések alkalmazása adatpont-jelölőkre

Az egyéni képek vizuálisan vonzóbbá tehetik az adatjelölőket:

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Egyéni képek beállítása a jelölőkhöz
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## 6. lépés: Jelölő méretének testreszabása

Módosítsa a jelölők méretét a láthatóság javítása érdekében:

```csharp
series.Marker.Size = 20;
```

## 7. lépés: Mentse el a frissített prezentációt

Mentse el a testreszabott prezentációt a kívánt helyre:

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Következtetés

Az Aspose.Slides for .NET olyan eszközöket biztosít a fejlesztőknek, amelyekkel professzionális diagramokat hozhatnak létre gazdag testreszabási lehetőségekkel. A diagramjelölő opciók kihasználásával jelentősen javíthatja prezentációi vizuális vonzerejét és érthetőségét. Ez a lépésről lépésre útmutató biztosítja, hogy még az összetett testreszabások is egyszerűen megvalósíthatók legyenek.

## GYIK

### Használhatok bármilyen képformátumot a jelölők testreszabásához?
Igen, az Aspose.Slides különféle képformátumokat támogat, beleértve a JPEG, PNG és BMP formátumokat, a jelölők testreszabásához.

### Hogyan tudom megváltoztatni a diagram típusát a létrehozás után?
A diagram típusának módosításához nyissa meg a `chart.Type` tulajdonságot, és rendeljen hozzá egy másikat `ChartType`.

### Kompatibilis az Aspose.Slides for .NET a régebbi PowerPoint verziókkal?
Igen, támogatja a visszafelé kompatibilitást a régebbi PowerPoint formátumokkal, biztosítva a sokoldalúságot.

### Dinamikusan frissíthetem a diagram adatait?
Feltétlenül. Használd a `IChartDataWorkbook` a diagramadatok programozott frissítéséhez.

### Hol találok további forrásokat?
Fedezze fel a [Aspose.Slides dokumentáció](https://reference.aspose.com/slides/net/) vagy csatlakozz a [közösségi fórumok](https://forum.aspose.com/) támogatásért.