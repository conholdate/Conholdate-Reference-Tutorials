---
"description": "Aspose.Cells for .NET ile Excel'den PDF'e dönüştürmelerinizin tüm potansiyelini ortaya çıkarın. Bu kapsamlı kılavuzda, görseller gibi harici kaynakları nasıl yöneteceğinizi ve PDF'lerinizin biçimlendirme gereksinimlerinizi tam olarak yansıtmasını nasıl sağlayacağınızı öğrenin."
"linktitle": ".NET için Aspose.Cells ile Harici Kaynakları Kontrol Edin"
"second_title": "Aspose.Cells .NET Excel İşleme API'si"
"title": ".NET için Aspose.Cells ile Harici Kaynakları Kontrol Edin"
"url": "/tr/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## giriiş

Günümüzün dijital dünyasında, Excel elektronik tablolarını PDF belgelerine dönüştürmek yaygın ve önemli bir iştir. İster raporlar, ister finansal veriler veya sunum materyalleri hazırlıyor olun, PDF'lerinizin istediğiniz formatı yansıttığından emin olmak çok önemlidir. .NET için Aspose.Cells, özellikle görseller gibi harici kaynaklarla çalışırken bu dönüştürme sürecini ayrıntılı olarak kontrol etmenizi sağlayan güçlü bir kütüphane sunar. Bu kılavuzda, Aspose.Cells kullanarak Excel'den PDF'ye dönüştürme işlemi sırasında harici kaynakları nasıl etkili bir şekilde yöneteceğinizi inceleyeceğiz. Hadi başlayalım!

## Ön koşullar

Başlamadan önce aşağıdakilerin hazır olduğundan emin olun:

1. Visual Studio veya herhangi bir .NET uyumlu IDE: Bu sizin geliştirme ortamınız olacaktır.
2. Aspose.Cells for .NET: Henüz yüklemediyseniz, şu adresi ziyaret edin: [Aspose İndirmeleri](https://releases.aspose.com/cells/net/) En son sürümü almak için sayfaya gidin.
3. Temel C# Bilgisi: C#'a aşina olmak faydalı olacaktır. Herhangi bir kavram hakkında açıklamaya ihtiyacınız varsa, bunları araştırmaktan çekinmeyin.
4. Örnek Excel Dosyası: Dönüştürmek istediğiniz harici kaynakları içeren "samplePdfSaveOptions_StreamProvider.xlsx" gibi bir Excel dosyası hazırlayın.
5. Test İçin Görüntü Dosyası: Dönüştürme sırasında harici kaynak olarak "newPdfSaveOptions_StreamProvider.png" gibi bir görüntü dosyası kullanın.

## Gerekli Paketleri İçe Aktar

Başlamak için, Aspose.Cells kitaplığından gerekli ad alanlarını içe aktarmanız gerekecek. C# dosyanızın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

Bu ad alanları görevleriniz için gerekli sınıfları ve yöntemleri sağlar.

## Adım 1: Bir Akış Sağlayıcı Sınıfı Oluşturun

İlk olarak, akış sağlayıcı sınıfını uygulayın `IStreamProvider` arayüz. Bu sınıf, harici kaynakların nasıl yükleneceğini kontrol etmenizi sağlayacaktır.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // Görüntüyü bir bellek akışına yükleyin
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: Bu yöntem, akış kapatıldığında ve şu anda bir hata ayıklama mesajı kaydedildiğinde çağrılır.
- InitStream: Bu yöntem harici görüntü dosyasını bir bayt dizisi olarak okur, onu bir bellek akışına dönüştürür ve onu `options.Stream` mülk.

## Adım 2: Kaynak ve Çıktı Dizinlerini Ayarlayın

Daha sonra Excel dosyanız ve çıktı PDF'iniz için dizinleri tanımlayın.

```csharp
// Kaynak dizini
string sourceDir = "Your Document Directory";
// Çıktı dizini
string outputDir = "Your Document Directory";
```

Yer değiştirmek `"Your Document Directory"` Dosyalarınızın sisteminizde bulunduğu gerçek yol ile.

## Adım 3: Excel Dosyanızı Yükleyin

Şimdi PDF'ini oluşturmak istediğiniz Excel dosyasını yükleyin.

```csharp
// Harici görselleri içeren kaynak Excel dosyasını yükleyin
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

The `Workbook` Aspose.Cells'den alınan sınıf, resimler gibi çeşitli harici kaynakları içerebilen Excel dosyanızı temsil eder.

## Adım 4: PDF Kaydetme Seçeneklerini Ayarlayın

Çalışma kitabını PDF olarak kaydetmeden önce, istediğiniz kaydetme seçeneklerini belirtin.

```csharp
// PDF Kaydetme Seçeneklerini Belirleyin - Akış Sağlayıcısı
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // Her sayfayı yeni bir sayfaya kaydedin
};
```

Bu, bir örnek oluşturur `PdfSaveOptions`PDF formatını özelleştirmenize olanak tanır. `OnePagePerSheet` Bu seçenek, her Excel sayfasının nihai PDF'de ayrı bir sayfada görünmesini sağlar.

## Adım 5: Akış Sağlayıcınızı Atayın

Bağlanın `Workbook` örnek ile `MyStreamProvider` daha önce oluşturduğunuz sınıf.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

Bu satır, dönüştürme sırasında harici kaynaklarla karşılaşıldığında, özel sağlayıcınızın bunları buna göre yönetmesini sağlar.

## Adım 6: Çalışma Kitabını PDF olarak kaydedin

Şimdi Excel çalışma kitabınızı PDF olarak kaydedin.

```csharp
// Çalışma kitabını PDF'e kaydedin
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

Arayarak `Save` Çalışma kitabı nesnesindeki yöntemi kullanarak ve çıktı dizinini PDF seçenekleriyle birlikte geçirerek, Excel dosyasını iyi biçimlendirilmiş bir PDF'ye dönüştürürsünüz.

## Adım 7: Başarılı Yürütmeyi Onaylayın

Son olarak, sürecin başarıyla tamamlandığını teyit etmek iyi bir uygulamadır.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

Bu mesaj, operasyonunuzun durumu hakkında sizi bilgilendirecek ve faydalı geri bildirimler sağlayacaktır.

## Çözüm

Artık Aspose.Cells kullanarak Excel'den PDF'e dönüştürme sırasında harici kaynakları kontrol etme sürecinde ustalaştınız! Bu adımları izleyerek, belgelerinizin görselleri ve diğer harici öğeleri doğru bir şekilde içermesini sağlayabilir ve her seferinde kusursuz bir son ürün elde edebilirsiniz.

## SSS

### Aspose.Cells nedir?
Aspose.Cells, çeşitli formatlardaki Excel dosyalarının oluşturulmasını, işlenmesini, dönüştürülmesini ve işlenmesini sağlayan .NET geliştiricileri için güçlü bir kütüphanedir.

### Aspose.Cells'i nasıl indirebilirim?
En son sürümü şu adresten indirebilirsiniz: [İndirme bağlantısı](https://releases.aspose.com/cells/net/).

### Aspose.Cells'i ücretsiz deneyebilir miyim?
Evet! Ücretsiz denemeye erişmek için şu adresi ziyaret edebilirsiniz: [Ücretsiz deneme sayfası](https://releases.aspose.com/).

### Aspose.Cells için desteği nerede bulabilirim?
Destekle ilgili sorularınız için şu adresi ziyaret edin: [Aspose Destek forumu](https://forum.aspose.com/c/cells/9).

### Aspose.Cells için geçici lisansı nasıl alabilirim?
Geçici lisans başvurusunda bulunabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).