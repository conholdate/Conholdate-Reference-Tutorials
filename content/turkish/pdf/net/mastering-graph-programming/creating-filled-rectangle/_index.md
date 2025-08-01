---
"description": "Bu adım adım eğitimde, .NET için Aspose.PDF ile PDF düzenlemenin gücünü keşfedin. Dolu dikdörtgenler çizerek görsel olarak çekici PDF belgelerini programatik olarak nasıl oluşturacağınızı öğrenin."
"linktitle": "Dolu Dikdörtgen Oluşturma"
"second_title": ".NET API Referansı için Aspose.PDF"
"title": "Dolu Dikdörtgen Oluşturma"
"url": "/tr/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## giriiş

Hiç görsel olarak çarpıcı PDF'leri programatik olarak oluşturmak istediniz mi? Öyleyse, doğru yerdesiniz! Bu eğitimde, PDF belgelerini düzenlemeyi kolaylaştıran güçlü bir kütüphane olan .NET için Aspose.PDF'yi inceleyeceğiz. Bugün, bir PDF dosyası içinde dolu bir dikdörtgen oluşturmaya odaklanacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz her adımda size samimi ve ilgi çekici bir şekilde yol gösterecek. Öyleyse, kodlama şapkanızı kapın ve başlayalım!

## Ön koşullar

Koda dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: .NET geliştirme için mükemmel bir IDE olan Visual Studio'yu makinenize kurun.
2. .NET için Aspose.PDF: Aspose.PDF kitaplığını şu adresten indirin ve yükleyin: [Burada](https://releases.aspose.com/pdf/net/).
3. C# Temel Bilgisi: C# programlamaya aşinalık, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Adım 1: Yeni Bir Proje Oluşturun

1. Visual Studio'yu açın ve yeni bir Konsol Uygulaması projesi oluşturun.
2. Projenize uygun bir isim verin.

## Adım 2: Aspose.PDF Referansını Ekleyin

1. Çözüm Gezgini'nde projenize sağ tıklayın.
2. NuGet Paketlerini Yönet'i seçin.
3. Aspose.PDF dosyasını arayın ve en son sürümü yükleyin.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Artık her şeyi ayarladığımıza göre koda geçelim!

## Adım 3: Belge Dizininizi Ayarlayın

PDF'nizin kaydedileceği yolu belirtin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Yer değiştirmek `"YOUR DOCUMENT DIRECTORY"` PDF'yi kaydetmek istediğiniz makinenizdeki gerçek yol ile.

## Adım 4: Bir Belge Örneği Oluşturun

Yeni bir PDF belgesi başlatın:

```csharp
// Belge örneği oluştur
Document doc = new Document();
```

## Adım 5: Belgeye Bir Sayfa Ekleyin

Her PDF'in en az bir sayfaya ihtiyacı vardır. Hadi bir tane ekleyelim:

```csharp
// PDF dosyası koleksiyonuna sayfa sayfa ekle
Page page = doc.Pages.Add();
```

## Adım 6: Bir Grafik Örneği Oluşturun

A `Graph` örnek, şekillerin çizilmesi için bir tuval görevi görür:

```csharp
// Grafik örneği oluştur
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## Adım 7: Grafiği Sayfaya Ekleyin

Grafiği sayfaya ekleyin:

```csharp
// Sayfa örneğinin paragraf koleksiyonuna grafik nesnesi ekle
page.Paragraphs.Add(graph);
```

## Adım 8: Dikdörtgen Örneği Oluşturun

Dikdörtgenin konumunu ve boyutunu tanımlayın:

```csharp
// Dikdörtgen örneği oluştur
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## Adım 9: Dolgu Rengini Belirleyin

Dikdörtgeniniz için bir renk seçin. Bu örnekte kırmızıyı kullanacağız:

```csharp
// Grafik nesnesi için dolgu rengini belirtin
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Adım 10: Grafiğe Dikdörtgeni Ekleyin

Grafiğe dikdörtgeni ekleyin:

```csharp
// Grafik nesnesinin şekiller koleksiyonuna dikdörtgen nesnesi ekle
graph.Shapes.Add(rect);
```

## Adım 11: PDF Belgesini Kaydedin

Son olarak belgenizi belirtilen dizine kaydedin:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
```

## Adım 12: Onay Mesajı

Başarılı olduğunuzu belirtmek için bir onay mesajı yazdırın:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde dolu bir dikdörtgen oluşturmayı başardınız. Bu güçlü kütüphane, PDF düzenleme için bir dünya olasılık sunarak, programatik olarak çarpıcı belgeler oluşturmanıza olanak tanır. İster rapor, ister fatura veya başka herhangi bir PDF türü oluşturuyor olun, Aspose.PDF size yardımcı olur.

## SSS

### .NET için Aspose.PDF nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
Evet, Aspose, kütüphanenin özelliklerini keşfetmeniz için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. İndirebilirsiniz [Burada](https://releases.aspose.com/).

### Aspose.PDF desteği almanın bir yolu var mı?
Kesinlikle! Aspose forumundan destek alabilirsiniz. [Burada](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF'yi nasıl satın alabilirim?
Aspose.PDF'yi satın alma sayfasını ziyaret ederek satın alabilirsiniz [Burada](https://purchase.aspose.com/buy).

### Aspose.PDF ile hangi tür şekiller oluşturabilirim?
Aspose.PDF kütüphanesini kullanarak dikdörtgenler, daireler, çizgiler ve daha fazlası dahil olmak üzere çeşitli şekiller oluşturabilirsiniz.