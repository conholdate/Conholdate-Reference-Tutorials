---
"description": "Aspose.Words for .NET kullanarak bir Word belgesinin her sayfasını ayrı PNG görüntülerine nasıl kolayca dönüştürebileceğinizi öğrenin. Bu kılavuz, kod örnekleri de dahil olmak üzere adım adım talimatlar sunar."
"linktitle": "Word Belgelerinde Sayfa Kaydetme Geri Araması"
"second_title": "Aspose.Words Belge İşleme API'si"
"title": "Word Belgelerinde Sayfa Kaydetme Geri Araması"
"url": "/tr/words/net/guide-to-image-save-options/page-saving-callback-word-document/"
"weight": 10
---

## giriiş

Bir Word belgesinin her sayfasını ayrı ayrı görsellere dönüştürmeniz gerekti mi? İster önizleme için küçük resimler oluşturmak, ister uzun bir raporu anlaşılır görsellere bölmek isteyin, Aspose.Words for .NET bu görevi basit ve verimli hale getirir. Bu kılavuzda, belgenizin her sayfasını PNG resmi olarak kaydetmek için bir sayfa kaydetme geri araması oluşturma sürecini adım adım anlatacağız. Haydi başlayalım!

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET: İndirin ve kurun [Burada](https://releases.aspose.com/words/net/).
2. Visual Studio: Herhangi bir sürüm işe yarayacaktır, ancak bu kılavuz için Visual Studio 2019'u kullanacağız.
3. Temel C# Bilgisi: C#'a aşina olmanız, konuyu rahatça takip etmenize yardımcı olacaktır.

## Adım 1: Gerekli Ad Alanlarını İçe Aktarın

Öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor. Bu, her seferinde tam ad alanını yazmadan gerekli sınıflara ve yöntemlere erişmemizi sağlar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Adım 2: Belge Dizininizi Tanımlayın

Ardından, belge dizininizin yolunu ayarlayın. Giriş Word belgenizin bulunduğu ve çıktı görsellerinin kaydedileceği yer burasıdır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 3: Belgenizi Yükleyin

Şimdi, işlemek istediğiniz belgeyi yükleyelim. "Rendering.docx" adlı belgenizin belirtilen dizinde olduğundan emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Adım 4: Görüntü Kaydetme Seçeneklerini Yapılandırın

Sayfaları PNG dosyası olarak kaydetmek istediğimizi belirterek, resimleri kaydetme seçeneklerini ayarlayacağız.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

Burada, `PageSet` kaydedilecek sayfa aralığını tanımlar ve `PageSavingCallback` özel geri çağırma sınıfımıza işaret eder.

## Adım 5: Sayfa Kaydetme Geri Aramasını Uygulayın

Şimdi, her sayfanın nasıl kaydedileceğini işleyen geri çağırma sınıfını uygulamamız gerekiyor.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

Bu sınıf şunları uygular: `IPageSavingCallback` arayüz. İçinde `PageSaving` yönteminde, kaydedilen her sayfa için adlandırma desenini belirtiriz.

## Adım 6: Belgeyi Resim Olarak Kaydedin

Son olarak yapılandırılan seçenekleri kullanarak belgeyi kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Çözüm

Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesinin her sayfasını ayrı bir PNG resmi olarak kaydetmek için sayfa kaydetme geri aramasını başarıyla ayarladınız. Bu teknik, sayfa önizlemeleri oluşturmaktan raporlar için ayrı sayfa resimleri oluşturmaya kadar çeşitli uygulamalar için inanılmaz derecede kullanışlıdır.

## SSS

### Sayfaları PNG dışındaki formatlarda kaydedebilir miyim?
Evet! Sayfaları JPEG, BMP ve TIFF gibi formatlarda kaydedebilirsiniz. `SaveFormat` içinde `ImageSaveOptions`.

### Sadece belirli sayfaları nasıl kaydedebilirim?
Belirli sayfaları kaydetmek için, `PageSet` parametre içinde `ImageSaveOptions` sadece istenilen sayfaları dahil etmek için.

### Görüntü kalitesini özelleştirmek mümkün mü?
Kesinlikle! Çıktı görüntü kalitesini şu gibi özellikleri ayarlayarak kontrol edebilirsiniz: `ImageSaveOptions.JpegQuality`.

### Büyük belgeleri nasıl verimli bir şekilde yönetebilirim?
Büyük belgeler için, bellek kullanımını etkili bir şekilde yönetmek amacıyla sayfaları toplu olarak işlemeyi düşünün.

### Aspose.Words for .NET hakkında daha fazla bilgiyi nerede bulabilirim?
Kapsamlı kılavuzlar ve örnekler için şuraya göz atın: [Aspose.Words belgeleri](https://reference.aspose.com/words/net/).