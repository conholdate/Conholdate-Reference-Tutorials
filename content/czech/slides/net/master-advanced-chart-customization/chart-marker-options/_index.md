---
"description": "Naučte se, jak vylepšit své grafy PowerPoint pomocí přizpůsobených možností značek pomocí Aspose.Slides pro .NET. Tato podrobná příručka zahrnuje předpoklady, vytváření grafů, formátování datových bodů a další."
"linktitle": "Možnosti značek grafu na datovém bodě v Aspose.Slides .NET"
"second_title": "Rozhraní API pro zpracování PowerPointu v aplikaci Aspose.Slides v .NET"
"title": "Možnosti značek grafu na datovém bodě v Aspose.Slides .NET"
"url": "/cs/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## Zavedení

Začlenění vizuálních pomůcek do prezentací je nezbytné pro působivou komunikaci. Aspose.Slides pro .NET poskytuje robustní nástroje pro vytváření a úpravu grafů, které vývojářům umožňují vylepšit jejich prezentace dat. Jednou z vynikajících funkcí je možnost používat možnosti značek grafu na datových bodech, což umožňuje přesné přizpůsobení pro profesionálně vypadající grafy. Tento článek vás provede každým krokem potřebným k dosažení tohoto cíle.

## Předpoklady

Než budete pokračovat, ujistěte se, že:

- Aspose.Slides pro .NET nainstalován: Stáhněte si jej z [zde](https://releases.aspose.com/slides/net/).
- Základní nastavení: Soubor prezentace, například „Test.pptx“, ve vašem pracovním adresáři.
- Vývojové prostředí: Visual Studio nebo ekvivalent, konfigurované pro .NET.

## Import požadovaných jmenných prostorů

Pro bezproblémový vývoj přidejte do projektu potřebné jmenné prostory:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Krok 1: Vytvořte v prezentaci graf

Začněte vytvořením výchozího grafu na prvním snímku prezentace:

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

Toto přidává `LineWithMarkers` graf na snímek se zadanými rozměry.

## Krok 2: Načtení indexu pracovního listu s daty grafu

Výchozí index listu s daty grafu je nezbytný pro další přizpůsobení:

```csharp
int defaultWorksheetIndex = 0;
```

## Krok 3: Přístup k sešitu s daty grafů

Chcete-li manipulovat s daty grafu, načtěte příslušný sešit:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## Krok 4: Konfigurace řady grafů a přidání datových bodů

Vymazat výchozí řadu a přidat nové datové body pro vaši řadu:

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Přidání datových bodů do řady
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## Krok 5: Použití obrázkových výplní na značky datových bodů

Vlastní obrázky mohou datové značky zatraktivnit:

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Nastavení vlastních obrázků pro značky
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## Krok 6: Úprava velikosti značky

Upravte velikost značek pro lepší viditelnost:

```csharp
series.Marker.Size = 20;
```

## Krok 7: Uložte aktualizovanou prezentaci

Uložte si upravenou prezentaci do požadovaného umístění:

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Závěr

Aspose.Slides pro .NET poskytuje vývojářům nástroje pro vytváření profesionálních grafů s bohatými možnostmi přizpůsobení. Využitím možností značek grafů můžete výrazně zlepšit vizuální atraktivitu a srozumitelnost vašich prezentací. Tato podrobná příručka zajišťuje, že i složité úpravy budou snadno implementovatelné.

## Často kladené otázky

### Mohu pro přizpůsobení značky použít jakýkoli formát obrázku?
Ano, Aspose.Slides podporuje různé obrazové formáty, včetně JPEG, PNG a BMP, pro přizpůsobení značek.

### Jak změním typ grafu po vytvoření?
Chcete-li změnit typ grafu, přejděte na `chart.Type` vlastnost a přiřadit jinou `ChartType`.

### Je Aspose.Slides pro .NET kompatibilní se staršími verzemi PowerPointu?
Ano, podporuje zpětnou kompatibilitu se staršími formáty PowerPointu, což zajišťuje všestrannost.

### Mohu dynamicky aktualizovat data grafu?
Rozhodně. Použijte `IChartDataWorkbook` programově aktualizovat data grafu.

### Kde najdu další zdroje?
Prozkoumejte [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/net/) nebo se připojte k [komunitní fóra](https://forum.aspose.com/) pro podporu.