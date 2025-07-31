---
"description": "Naučte se, jak přidávat a upravovat trendové čáry v grafech pomocí Aspose.Slides pro .NET. Tato komplexní příručka zahrnuje exponenciální, lineární, logaritmické, polynomiální a klouzavé průměrné trendové čáry pro vylepšení vizualizace dat."
"linktitle": "Trendové čáry v grafech s Aspose.Slides pro .NET"
"second_title": "Rozhraní API pro zpracování PowerPointu v aplikaci Aspose.Slides v .NET"
"title": "Trendové čáry v grafech s Aspose.Slides pro .NET"
"url": "/cs/slides/net/master-advanced-chart-customization/trend-lines-in-charts/"
"weight": 12
---

## Zavedení  

Přidávání trendových čar do grafů je klíčovou technikou pro analýzu datových trendů a předpovídání budoucích hodnot. S Aspose.Slides pro .NET můžete bez problémů přidávat a upravovat trendové čáry do prezentačních grafů, čímž vylepšíte vizualizaci dat. Tato příručka poskytuje podrobný návod pro přidávání trendových čar do různých typů grafů v prezentaci PowerPoint pomocí Aspose.Slides pro .NET.  

## Předpoklady  

Než se pustíme do implementace, ujistěte se, že máte následující nastavení:  

1. Aspose.Slides pro .NET: Stáhněte a nainstalujte knihovnu z [stránka ke stažení](https://releases.aspose.com/slides/net/).  
2. Vývojové prostředí: Pro kódování použijte IDE, jako je Visual Studio.  
3. Základní znalost C#: Pro absolvování tohoto tutoriálu je nutná znalost programování v C#.  

## Import požadovaných jmenných prostorů  

Pro začátek importujte základní jmenné prostory do svého projektu:  

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Krok 1: Příprava prezentace  

Nejprve inicializujte prázdnou prezentaci. Ta bude sloužit jako kontejner pro váš graf.  

```csharp
string dataDir = "Your/Documents/Directory";

// Ujistěte se, že adresář existuje
if (!System.IO.Directory.Exists(dataDir))
    System.IO.Directory.CreateDirectory(dataDir);

// Vytvořte novou prezentaci
Presentation presentation = new Presentation();
```

## Krok 2: Přidání grafu do snímku  

Nyní přidejte snímek a vložte seskupený sloupcový graf pro vizualizaci dat.  

```csharp
// Přidat prázdný snímek
ISlide slide = presentation.Slides[0];

// Přidání seskupeného sloupcového grafu
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
```

## Krok 3: Naplnění grafu daty  

Naplňte graf vzorovými daty.  

```csharp
// Přístup k výchozímu sešitu s daty grafu
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// Aktualizovat výchozí hodnoty kategorií a řad
workbook.Clear(0);
workbook.GetCell(0, 0, 1).Value = "Category 1";
workbook.GetCell(0, 0, 2).Value = "Category 2";

chart.ChartData.Series[0].DataPoints[0].Value.Data = 4.5;
chart.ChartData.Series[0].DataPoints[1].Value.Data = 2.8;
```

## Krok 4: Přidání trendových linií  

### Exponenciální trendová linie  

```csharp
ITrendline expTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
expTrendLine.DisplayEquation = true;
expTrendLine.DisplayRSquaredValue = true;
```

### Lineární trendová linie  

```csharp
ITrendline linTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
linTrendLine.Format.Line.FillFormat.FillType = FillType.Solid;
linTrendLine.Format.Line.FillFormat.SolidFillColor.Color = Color.Blue;
```

### Logaritmická trendová linie  

```csharp
ITrendline logTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Logarithmic);
logTrendLine.AddTextFrameForOverriding("Logarithmic Trend");
```

### Trendová linie klouzavého průměru  

```csharp
ITrendline movAvgTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.MovingAverage);
movAvgTrendLine.Period = 3;
movAvgTrendLine.TrendlineName = "3-Point Moving Average";
```

### Polynomiální trendová linie  

```csharp
ITrendline polyTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Polynomial);
polyTrendLine.Order = 2;
polyTrendLine.Forward = 1;
```

### Trendová linie výkonu  

```csharp
ITrendline powerTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Power);
powerTrendLine.DisplayEquation = true;
powerTrendLine.Backward = 1;
```

## Krok 5: Uložení prezentace  

Nakonec uložte prezentaci se všemi trendovými liniemi přidanými do grafu.  

```csharp
presentation.Save(dataDir + "TrendLinesPresentation.pptx", SaveFormat.Pptx);
```

## Závěr  

Díky Aspose.Slides pro .NET se přidávání trendových čar do grafů stává snadným úkolem. Tato funkce vám umožňuje efektivně prezentovat trendy v datech a dodat vašim prezentacím profesionální nádech. Postupujte podle výše uvedených kroků a začleňte různé typy trendových čar a vylepšete vizualizaci dat.  

## Často kladené otázky  

### Mohu si přizpůsobit vzhled trendových linií?  
Ano, barvu, tloušťku a styl trendových čar si můžete přizpůsobit pomocí `Format.Line` vlastnictví.  

### Existuje podpora i pro jiné typy grafů?  
Ano, Aspose.Slides pro .NET podporuje různé typy grafů, včetně sloupcových, koláčových a spojnicových grafů.  

### Jak zobrazím rovnice a hodnoty R-kvadrátu?  
Umožnit `DisplayEquation` a `DisplayRSquaredValue` vlastnosti trendové linie pro zobrazení těchto hodnot v grafu.  

### Mohu používat Aspose.Slides pro .NET s jinými jazyky?  
Ano, knihovna je kompatibilní s jakýmkoli jazykem podporovaným .NET, včetně VB.NET a F#.  

### Kde najdu další dokumentaci?  
Navštivte [Dokumentace k Aspose.Slides pro .NET](https://reference.aspose.com/slides/net/) pro více informací.