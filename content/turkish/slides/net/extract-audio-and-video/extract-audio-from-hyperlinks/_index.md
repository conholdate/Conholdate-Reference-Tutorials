---
"description": "Aspose.Slides for .NET ile PowerPoint sunumlarındaki köprülerden ses dosyalarını nasıl çıkaracağınızı öğrenin. Bu adım adım kılavuz, net talimatlar sunar."
"linktitle": "Hiper Bağlantılardan Ses Çıkarma"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides Kullanarak PowerPoint'teki Köprülerden Ses Çıkarma"
"url": "/tr/slides/net/extract-audio-and-video/extract-audio-from-hyperlinks/"
"weight": 12
---

## giriiş

Multimedya sunumlarında ses, slaytlarınızın etkisini önemli ölçüde artırır. Ses bağlantıları içeren bir PowerPoint sunumuyla karşılaştıysanız ve bu sesi başka amaçlar için nasıl çıkaracağınızı merak ediyorsanız, doğru yerdesiniz. Bu kılavuz, Aspose.Slides for .NET kütüphanesini kullanarak bir PowerPoint sunumundaki bağlantılardan ses çıkarma sürecini adım adım açıklayacaktır.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### .NET için Aspose.Slides Kütüphanesi

Aspose.Slides for .NET kütüphanesinin yüklü olduğundan emin olun. Henüz yüklemediyseniz, şu adresten indirebilirsiniz: [.NET Belgeleri için Aspose.Slides](https://reference.aspose.com/slides/net/).

### Sesli Bağlantılı PowerPoint Sunumu

Bağlantılı ses dosyaları içeren bir PowerPoint sunumuna (PPTX) ihtiyacınız olacak. Bu sunum, ses dosyası çıkarma kaynağınız olacak.

## Gerekli Ad Alanlarını İçe Aktarma

Aspose.Slides for .NET'i etkili bir şekilde kullanmak için, aşağıdaki ad alanlarını C# projenize aktarmanız gerekir:

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

Artık her şey yerli yerinde olduğuna göre, çıkarma işlemini kolay adımlara bölelim.

## Adım 1: Belge Dizinini Tanımlayın

PowerPoint sunumunuzun bulunduğu dizini belirterek başlayın. Değiştir `"Your Document Directory"` gerçek yol ile.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: PowerPoint Sunumunu Yükleyin

Ardından, ses bağlantısını içeren PowerPoint sunumunu (PPTX) yükleyin. Değiştir `"HyperlinkSound.pptx"` gerçek sunum dosya adınızla.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // Bir sonraki adıma geçin.
}
```

## Adım 3: Hiper Bağlantı Sesi'ne erişin

İlk slayttaki ilk şekilden köprü metnini alın. Bu köprü metninin ilişkili bir sesi varsa, onu çıkarmaya devam edebiliriz.

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // Bir sonraki adıma geçin.
}
```

## Adım 4: Köprüden Sesi Çıkarın

Eğer hiperlink ses içeriyorsa bunu bayt dizisi olarak çıkarıp medya dosyası olarak kaydedebiliriz.

```csharp
// Köprü sesini bir bayt dizisi olarak çıkarın
byte[] audioData = link.Sound.BinaryData;

// Çıkarılan sesi kaydetmek istediğiniz yolu belirtin
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// Çıkarılan sesi bir medya dosyasına kaydedin
File.WriteAllBytes(outMediaPath, audioData);
```

Tebrikler! Aspose.Slides for .NET kullanarak bir PowerPoint sunumundaki köprüden sesi başarıyla çıkardınız. Artık bu sesi multimedya projelerinizde kullanabilirsiniz.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarındaki köprülerden ses çıkarmak için güçlü ve kullanıcı dostu bir yol sunar. Bu kılavuzda açıklanan adımlarla, projelerinizi geliştirmek için sunumlarınızdaki ses içeriklerini kolayca yeniden kullanabilirsiniz.

## SSS

### Aspose.Slides for .NET ücretsiz bir kütüphane midir?
Hayır, Aspose.Slides for .NET ticari bir kütüphanedir, ancak özelliklerini keşfetmek için ücretsiz deneme sürümünü indirebilirsiniz. [Burada](https://releases.aspose.com/).

### PPT gibi eski PowerPoint formatlarından ses çıkarabilir miyim?
Evet, Aspose.Slides for .NET ses çıkarma için hem PPTX hem de PPT formatlarını destekler.

### Aspose.Slides desteği için bir topluluk forumu var mı?
Kesinlikle! Yardım alabilir ve deneyimlerinizi paylaşabilirsiniz. [Aspose.Slides topluluk forumu](https://forum.aspose.com/).

### Kısa süreli bir proje için Aspose.Slides için geçici bir lisans satın alabilir miyim?
Evet, kısa vadeli proje ihtiyaçlarınız için geçici lisans almak için şu adresi ziyaret edebilirsiniz: [bu bağlantı](https://purchase.aspose.com/temporary-license/).

### MPG dışında çıkarım için desteklenen başka ses formatları var mı?
Evet, Aspose.Slides for .NET çeşitli ses formatlarında çıkarma yapmanıza olanak tanır. Çıkardıktan sonra sesi tercih ettiğiniz formata dönüştürebilirsiniz.