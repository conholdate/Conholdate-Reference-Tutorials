---
"description": ".NET için GroupDocs.Annotation'ı kullanarak etkileşimli Düğme Bileşenleri ekleyerek PDF belgelerinizi nasıl daha üst düzeye çıkaracağınızı adım adım anlatan bu eğitimde keşfedin."
"linktitle": "Düğme Bileşenleri Ekleme"
"second_title": "GroupDocs.Annotation .NET API"
"title": ".NET için GroupDocs.Annotation ile Düğme Bileşenleri Ekleme"
"url": "/tr/annotation/net/guide-to-document-components/adding-button-component/"
"weight": 10
---

## giriiş

Bu eğitimde, .NET için GroupDocs.Annotation kütüphanesini kullanarak bir PDF belgesine Düğme Bileşeni eklemenin basit sürecini adım adım anlatacağız. Bu kılavuzun sonunda, PDF belgelerinizi etkileşimli özelliklerle zenginleştirebilecek donanıma sahip olacaksınız.

## Ön koşullar

Başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:

1. GroupDocs.Annotation for .NET: GroupDocs.Annotation for .NET kitaplığını şu adresten indirin ve yükleyin: [Burada](https://releases.groupdocs.com/annotation/net/).
2. Geliştirme Ortamı: .NET framework'ün yüklü olduğu uygun bir geliştirme ortamı kurun.

## Adım 1: Gerekli Ad Alanlarını İçe Aktarın

Öncelikle gerekli ad alanlarını projenize aktarın:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Annotation.Models;
using GroupDocs.Annotation.Models.AnnotationModels;
using GroupDocs.Annotation.Models.FormatSpecificComponents.Pdf;
using GroupDocs.Annotation.Options;
```

## Adım 2: Çıkış Yolunu Başlatın

Değiştirilen PDF'nin kaydedileceği çıktı yolunu tanımlayın:

```csharp
string outputPath = Path.Combine("Your Document Directory", "result" + Path.GetExtension("input.pdf"));
```

## Adım 3: Bir Düğme Bileşeni Ekleyin

Şimdi Düğme Bileşenini oluşturalım ve PDF'inize ekleyelim:

```csharp
using (Annotator annotator = new Annotator("input.pdf"))
{
    ButtonComponent button = new ButtonComponent
    {
        Box = new Rectangle(100, 100, 100, 100), // Düğmenin konumu ve boyutu
        PenColor = 65535,                       // Düğme kenarlık rengi
        Style = BorderStyle.Dashed,             // Sınır stili
        BorderWidth = 0,                        // Sınır genişliği
        BorderColor = 0,                        // Sınır rengi
        AlternateName = "Name",                 // Düğme için alternatif ad
        PartialName = "Partial Name",           // Düğme için kısmi ad
        NormalCaption = "Caption",               // Butonda görüntülenen metin
        ButtonColor = 16761035,                 // Düğmenin arka plan rengi
        Replies = new List<Reply>
        {
            new Reply { Comment = "First comment", RepliedOn = DateTime.Now },
            new Reply { Comment = "Second comment", RepliedOn = DateTime.Now }
        }
    };

    annotator.Add(button); // Düğmeyi açıklama kısmına ekleyin
    annotator.Save("result.pdf"); // Değiştirilen PDF'yi kaydedin
}
```

## Adım 4: Çıkış Yolunu Görüntüle

Son olarak kullanıcıya çıktı dosyasının nereye kaydedildiğini bildirin:

```csharp
Console.WriteLine($"\nDocument saved successfully.\nCheck output in {outputPath}.");
```

Tebrikler! GroupDocs.Annotation for .NET kullanarak bir PDF belgesine Düğme Bileşeni'ni başarıyla eklediniz.

## Çözüm

Bu eğitimde, .NET için GroupDocs.Annotation ile Düğme Bileşenlerini PDF belgelerine nasıl entegre edeceğinizi gösterdik. Bu adımları izleyerek PDF belgelerinizin etkileşimini önemli ölçüde artırabilirsiniz.

## SSS

### Butonun görünümünü özelleştirebilir miyim?

Kesinlikle! Boyut, renk ve stil gibi çeşitli özellikleri ihtiyaçlarınıza göre değiştirebilirsiniz.

### GroupDocs.Annotation for .NET tüm PDF sürümleriyle uyumlu mudur?

Evet, GroupDocs.Annotation for .NET çok çeşitli PDF sürümlerini destekler ve çoğu belgeyle uyumluluğu garanti eder.

### Tek bir PDF belgesine birden fazla düğme bileşeni ekleyebilir miyim?

Evet, bir PDF belgesine ihtiyacınız olduğu kadar çok düğme bileşeni ekleyebilirsiniz.

### GroupDocs.Annotation for .NET diğer dosya biçimlerini destekliyor mu?

Evet, PDF'nin yanı sıra DOCX, PPTX ve XLSX gibi çeşitli belge formatlarını destekler.

### Test amaçlı bir deneme sürümü mevcut mu?

Evet, GroupDocs.Annotation for .NET'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz: [Burada](https://releases.groupdocs.com/).