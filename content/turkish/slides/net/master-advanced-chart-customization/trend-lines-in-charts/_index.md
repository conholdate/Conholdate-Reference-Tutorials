---
"description": "Aspose.Slides for .NET kullanarak grafiklere trend çizgilerinin nasıl ekleneceğini ve özelleştirileceğini öğrenin. Bu kapsamlı kılavuz, veri görselleştirmenizi geliştirmek için üstel, doğrusal, logaritmik, polinom ve hareketli ortalama trend çizgilerini kapsar."
"linktitle": "Aspose.Slides for .NET ile Grafiklerde Trend Çizgileri"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides for .NET ile Grafiklerde Trend Çizgileri"
"url": "/tr/slides/net/master-advanced-chart-customization/trend-lines-in-charts/"
"weight": 12
---

## giriiş  

Grafiklere trend çizgileri eklemek, veri eğilimlerini analiz etmek ve gelecekteki değerleri tahmin etmek için önemli bir tekniktir. Aspose.Slides for .NET ile, sunum grafiklerinize trend çizgilerini sorunsuz bir şekilde ekleyebilir ve özelleştirebilir, böylece veri görselleştirmenizi geliştirebilirsiniz. Bu kılavuz, Aspose.Slides for .NET kullanarak bir PowerPoint sunumunda çeşitli grafik türlerine trend çizgileri ekleme konusunda ayrıntılı bir kılavuz sunar.  

## Ön koşullar  

Uygulamaya geçmeden önce aşağıdaki kuruluma sahip olduğunuzdan emin olun:  

1. Aspose.Slides for .NET: Kütüphaneyi şu adresten indirin ve yükleyin: [indirme sayfası](https://releases.aspose.com/slides/net/).  
2. Geliştirme Ortamı: Kodlama için Visual Studio gibi bir IDE kullanın.  
3. Temel C# Bilgisi: Bu eğitimi takip edebilmek için C# programlamaya aşinalık gerekmektedir.  

## Gerekli Ad Alanlarını İçe Aktarma  

Başlamak için, temel ad alanlarını projenize aktarın:  

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Adım 1: Sunumu Ayarlama  

Öncelikle boş bir sunum başlatın. Bu, grafiğiniz için bir kapsayıcı görevi görecektir.  

```csharp
string dataDir = "Your/Documents/Directory";

// Dizinin mevcut olduğundan emin olun
if (!System.IO.Directory.Exists(dataDir))
    System.IO.Directory.CreateDirectory(dataDir);

// Yeni bir sunum oluştur
Presentation presentation = new Presentation();
```

## Adım 2: Bir Slayda Grafik Ekleme  

Şimdi bir slayt ekleyin ve verilerinizi görselleştirmek için kümelenmiş sütun grafiği ekleyin.  

```csharp
// Boş bir slayt ekle
ISlide slide = presentation.Slides[0];

// Kümelenmiş sütun grafiği ekleyin
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
```

## Adım 3: Grafik Verilerini Doldurma  

Grafiği örnek verilerle doldurun.  

```csharp
// Varsayılan grafik veri çalışma kitabına erişin
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// Varsayılan kategorileri ve seri değerlerini güncelleyin
workbook.Clear(0);
workbook.GetCell(0, 0, 1).Value = "Category 1";
workbook.GetCell(0, 0, 2).Value = "Category 2";

chart.ChartData.Series[0].DataPoints[0].Value.Data = 4.5;
chart.ChartData.Series[0].DataPoints[1].Value.Data = 2.8;
```

## Adım 4: Trend Çizgileri Ekleme  

### Üstel Trend Çizgisi  

```csharp
ITrendline expTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
expTrendLine.DisplayEquation = true;
expTrendLine.DisplayRSquaredValue = true;
```

### Doğrusal Trend Çizgisi  

```csharp
ITrendline linTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
linTrendLine.Format.Line.FillFormat.FillType = FillType.Solid;
linTrendLine.Format.Line.FillFormat.SolidFillColor.Color = Color.Blue;
```

### Logaritmik Trend Çizgisi  

```csharp
ITrendline logTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Logarithmic);
logTrendLine.AddTextFrameForOverriding("Logarithmic Trend");
```

### Hareketli Ortalama Trend Çizgisi  

```csharp
ITrendline movAvgTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.MovingAverage);
movAvgTrendLine.Period = 3;
movAvgTrendLine.TrendlineName = "3-Point Moving Average";
```

### Polinom Trend Çizgisi  

```csharp
ITrendline polyTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Polynomial);
polyTrendLine.Order = 2;
polyTrendLine.Forward = 1;
```

### Güç Trend Çizgisi  

```csharp
ITrendline powerTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Power);
powerTrendLine.DisplayEquation = true;
powerTrendLine.Backward = 1;
```

## Adım 5: Sunumu Kaydetme  

Son olarak, grafiğinize eklenen tüm trend çizgileriyle sunumu kaydedin.  

```csharp
presentation.Save(dataDir + "TrendLinesPresentation.pptx", SaveFormat.Pptx);
```

## Çözüm  

Aspose.Slides for .NET kullanarak, grafiklerinize trend çizgileri eklemek çok kolay bir iş haline gelir. Bu özellik, veri trendlerini etkili bir şekilde sunmanıza ve sunumlarınıza profesyonel dokunuşlar katmanıza olanak tanır. Çeşitli trend çizgisi türlerini birleştirmek ve veri görselleştirmenizi geliştirmek için yukarıdaki adımları izleyin.  

## SSS  

### Trend çizgilerinin görünümünü özelleştirebilir miyim?  
Evet, trend çizgilerinin rengini, kalınlığını ve stilini özelleştirebilirsiniz. `Format.Line` mülk.  

### Diğer grafik türleri için destek var mı?  
Evet, Aspose.Slides for .NET çubuk, pasta ve çizgi grafikleri dahil olmak üzere çeşitli grafik türlerini destekler.  

### Denklemleri ve R kare değerlerini nasıl görüntülerim?  
Olanak vermek `DisplayEquation` Ve `DisplayRSquaredValue` Bu değerleri grafikte görüntülemek için bir trend çizgisinin özelliklerini kullanın.  

### Aspose.Slides for .NET'i diğer dillerle birlikte kullanabilir miyim?  
Evet, kütüphane VB.NET ve F# dahil olmak üzere .NET destekli tüm dillerle uyumludur.  

### Daha fazla dokümanı nerede bulabilirim?  
Ziyaret edin [Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/) Daha fazla bilgi için.