---
"description": "Aspose.OCR kullanarak .NET uygulamalarınızda Optik Karakter Tanıma (OCR) teknolojisini nasıl uygulayacağınızı öğrenin. Bu kapsamlı kılavuz, tanınan çizgiler için dikdörtgenleri çıkarma sürecinde size yol gösterecektir."
"linktitle": "Görüntülerden Çizgi Dikdörtgenleri Çıkarma Tanıma"
"second_title": "Aspose.OCR .NET API"
"title": "Görüntülerden Çizgi Dikdörtgenleri Çıkarma Tanıma"
"url": "/tr/ocr/net/master-image-and-drawing-recognition/line-rectangles-from-images-recognition/"
"weight": 10
---

## giriiş

Optik Karakter Tanıma (OCR) teknolojisini .NET uygulamalarınıza entegre etmek için tasarlanmış etkileyici bir araç olan Aspose.OCR for .NET dünyasına hoş geldiniz. İster deneyimli bir geliştirici ister meraklı bir yeni başlayan olun, bu kılavuz, görsellerdeki tanınan metinlerden çizgileri temsil eden dikdörtgenler elde etme adımlarında size yol gösterecektir.

## Ön koşullar

Başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:

- C# ve .NET geliştirme konusunda temel bilgi.
- Visual Studio benzeri bir entegre geliştirme ortamı (IDE).
- Aspose.OCR for .NET kütüphanesi yüklü. İndirebilirsiniz [Burada](https://releases.aspose.com/ocr/net/).
- Tanıma amaçlı metin içeren örnek bir resim.

## Gerekli Ad Alanları

Başlamak için projenize gerekli ad alanlarını eklemeniz gerekecek. C# dosyanızın en üstüne şu satırları ekleyin:

```csharp
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using Aspose.OCR;
```

Bir OCR görüntüsündeki çizgiler için dikdörtgenleri almak üzere şu adımları izleyin.

## Adım 1: Belge Dizininizi Ayarlayın

Görüntü dosyanızın bulunduğu dizini belirtin:

```csharp
// Belge dizininize giden yolu tanımlayın
string dataDir = "Your Document Directory";
```

Değiştirdiğinizden emin olun `"Your Document Directory"` gerçek yol ile.

## Adım 2: Aspose.OCR'yi başlatın

Bir örneğini oluşturun `AsposeOcr` özelliklerine erişmek için sınıfa gidin:

```csharp
// Aspose.OCR API'sini başlatın
AsposeOcr api = new AsposeOcr();
```

## Adım 3: Görüntü Yolunu Belirleyin

İşlemek istediğiniz görüntü dosyasının tam yolunu tanımlayın:

```csharp
// Görüntünün tam yolunu belirtin
string fullPath = dataDir + "sample.png";
```

## 4. Adım: Görüntüyü Tanıyın ve Çizgiler İçin Dikdörtgenler Elde Edin

Şimdi, şunu kullanabilirsiniz: `GetRectangles` Tanınan metin satırlarının dikdörtgenlerini çıkarma yöntemi:

```csharp
// Belirtilen görüntüdeki çizgiler için dikdörtgenleri al
List<Rectangle> lines = api.GetRectangles(fullPath, AreasType.LINES, false);
```

## Adım 5: Sonuçları Çıktılayın

Son olarak, tespit edilen her çizgi dikdörtgeninin koordinatlarını konsola yazdırın:

```csharp
// Algılanan dikdörtgenlerin koordinatlarını göster
Console.WriteLine("Areas coordinates:");
lines.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
```

## Çözüm

Tebrikler! Aspose.OCR for .NET kullanarak bir OCR görüntüsündeki çizgiler için dikdörtgenleri başarıyla aldınız. Bu teknoloji, uygulamalarınızda metin çıkarma ve işleme için sayısız olanak sunar.

## SSS

### Aspose.OCR for .NET'i her türlü resimle kullanabilir miyim?

Evet, Aspose.OCR çeşitli görüntü formatlarını destekler ve OCR uygulamalarınıza esneklik sağlar.

### OCR tanıma işleminin doğruluk oranı nedir?

Aspose.OCR, çeşitli senaryolara uygun, metin tanımada yüksek doğruluk elde etmek için gelişmiş algoritmalar kullanır.

### Deneme sürümü mevcut mu?

Evet, Aspose.OCR for .NET'in özelliklerini indirmek için burayı tıklayabilirsiniz. [ücretsiz deneme](https://releases.aspose.com/).

### Ayrıntılı dokümantasyonu nerede bulabilirim?

Kapsamlı dokümantasyon bulunabilir [Burada](https://reference.aspose.com/ocr/net/), derinlemesine bilgi ve rehberlik sunuyor.

### Daha fazla yardıma mı ihtiyacınız var veya sorularınız mı var?

Tartışmaya katılın [Aspose.OCR forumu](https://forum.aspose.com/c/ocr/16) Toplum desteği için.