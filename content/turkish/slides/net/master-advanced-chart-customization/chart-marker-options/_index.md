---
"description": "Aspose.Slides for .NET kullanarak PowerPoint grafiklerinizi özelleştirilmiş işaretçi seçenekleriyle nasıl zenginleştireceğinizi öğrenin. Bu adım adım kılavuz, ön koşulları, grafik oluşturmayı, veri noktası biçimlendirmeyi ve daha fazlasını kapsar."
"linktitle": "Aspose.Slides .NET'te Veri Noktalarında Grafik İşaretleyici Seçenekleri"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides .NET'te Veri Noktalarında Grafik İşaretleyici Seçenekleri"
"url": "/tr/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## giriiş

Sunumlara görsel yardımcılar eklemek, etkili iletişim için olmazsa olmazdır. Aspose.Slides for .NET, grafikler oluşturmak ve özelleştirmek için güçlü araçlar sunarak geliştiricilerin veri sunumlarını geliştirmelerine olanak tanır. Öne çıkan özelliklerinden biri, veri noktalarında grafik işaretleyici seçeneklerinin kullanılabilmesi ve profesyonel görünümlü grafikler için hassas özelleştirme olanağı sağlamasıdır. Bu makale, bunu başarmak için gereken her adımda size yol gösterecektir.

## Ön koşullar

Devam etmeden önce aşağıdakilerden emin olun:

- .NET için Aspose.Slides Yüklendi: Şuradan indirin: [Burada](https://releases.aspose.com/slides/net/).
- Temel Kurulum: Çalışma dizininizde "Test.pptx" gibi bir sunum dosyası.
- Geliştirme Ortamı: .NET için yapılandırılmış Visual Studio veya eşdeğeri.

## Gerekli Ad Alanlarını İçe Aktarma

Kusursuz geliştirme için projenize gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Adım 1: Sununuzda Bir Grafik Oluşturun

Sunumunuzun ilk slaydında varsayılan bir grafik oluşturarak başlayın:

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

Bu bir şey ekler `LineWithMarkers` Slaydınıza belirtilen ölçülerde grafik ekleyin.

## Adım 2: Grafik Veri Çalışma Sayfası Dizinini Alın

Varsayılan grafik veri çalışma sayfası dizini, daha fazla özelleştirme için önemlidir:

```csharp
int defaultWorksheetIndex = 0;
```

## Adım 3: Grafik Veri Çalışma Kitabına Erişim

Grafik verilerini düzenlemek için ilişkili çalışma kitabını alın:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## Adım 4: Grafik Serilerini Yapılandırın ve Veri Noktalarını Ekleyin

Varsayılan seriyi temizleyin ve seriniz için yeni veri noktaları ekleyin:

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Seriye veri noktaları ekleyin
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## Adım 5: Veri Noktası İşaretleyicilerine Resim Dolguları Uygulayın

Özel görseller veri işaretleyicilerini görsel olarak çekici hale getirebilir:

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// İşaretleyiciler için özel resimler ayarlayın
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## Adım 6: İşaretçi Boyutunu Özelleştirin

Görünürlüğü artırmak için işaretçilerin boyutunu değiştirin:

```csharp
series.Marker.Size = 20;
```

## Adım 7: Güncellenen Sunumu Kaydedin

Özelleştirilmiş sunumu istediğiniz yere kaydedin:

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Çözüm

Aspose.Slides for .NET, geliştiricilere zengin özelleştirme seçenekleriyle profesyonel grafikler oluşturmaları için araçlar sunar. Grafik işaretleyici seçeneklerinden yararlanarak sunumlarınızın görsel çekiciliğini ve netliğini önemli ölçüde artırabilirsiniz. Bu adım adım kılavuz, karmaşık özelleştirmelerin bile kolayca uygulanmasını sağlar.

## SSS

### İşaretçi özelleştirmesi için herhangi bir resim formatını kullanabilir miyim?
Evet, Aspose.Slides işaretleyici özelleştirmesi için JPEG, PNG ve BMP dahil olmak üzere çeşitli görüntü formatlarını destekler.

### Grafik oluşturulduktan sonra türünü nasıl değiştirebilirim?
Grafik türünü değiştirmek için şuraya erişin: `chart.Type` mülkiyet ve farklı bir atama `ChartType`.

### Aspose.Slides for .NET eski PowerPoint sürümleriyle uyumlu mudur?
Evet, eski PowerPoint formatlarıyla geriye dönük uyumluluğu destekleyerek çok yönlülüğü garanti altına alır.

### Grafik verilerini dinamik olarak güncelleyebilir miyim?
Kesinlikle. Kullanın `IChartDataWorkbook` grafik verilerini programlı olarak güncellemek için.

### Daha fazla kaynağı nerede bulabilirim?
Keşfet [Aspose.Slides belgeleri](https://reference.aspose.com/slides/net/) veya katılın [topluluk forumları](https://forum.aspose.com/) destek için.