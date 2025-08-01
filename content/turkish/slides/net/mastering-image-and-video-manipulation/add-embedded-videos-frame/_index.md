---
"description": "Aspose.Slides for .NET kullanarak video yerleştirmeyi öğrenerek sunumlarınızın potansiyelini ortaya çıkarın. Bu kapsamlı eğitim, multimedya öğelerini entegre etme sürecinde size adım adım rehberlik eder."
"linktitle": ".NET Sunumlarına Gömülü Video Çerçevesi Ekleme"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": ".NET Sunumlarına Gömülü Video Çerçevesi Ekleme"
"url": "/tr/slides/net/mastering-image-and-video-manipulation/add-embedded-videos-frame/"
"weight": 19
---

## giriiş

Günümüzün hızlı tempolu sunum ortamında, multimedya öğelerinin entegrasyonu etkileşimi ve izleyici kitlesini elde tutmayı önemli ölçüde artırabilir. Aspose.Slides for .NET, slaytlarınıza video kareleri yerleştirmek için güçlü bir çözüm sunar. Bu eğitim, baştan sona sorunsuz bir deneyim sağlayarak süreci adım adım anlatacaktır.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Slides for .NET Kütüphanesi: Kütüphaneyi şu adresten indirin ve yükleyin: [yayın sayfası](https://releases.aspose.com/slides/net/).
- Medya İçeriği: Sununuza yerleştirmek istediğiniz bir video dosyası (örneğin, "Wildlife.mp4").

## Gerekli Ad Alanlarını İçe Aktar

.NET projenize gerekli ad alanlarını içe aktararak başlayın:

```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Adım 1: Dizinlerinizi Ayarlayın

Projenizin belge ve medya dosyaları için gerekli dizinleri içerdiğinden emin olun:

```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");

// Eğer yoksa dizin oluştur
if (!Directory.Exists(dataDir))
    Directory.CreateDirectory(dataDir);
```

## Adım 2: Sunum Sınıfını Örneklendirin

Bir örneğini oluşturun `Presentation` PPTX dosyanızı temsil edecek sınıf:

```csharp
using (Presentation pres = new Presentation())
{
    // İlk slaydı alın
    ISlide sld = pres.Slides[0];
```

## Adım 3: Videoyu Yerleştirin

Aşağıdaki kodu kullanarak videoyu sununuza yerleştirin:

```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(Path.Combine(videoDir, "Wildlife.mp4"), FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```

## Adım 4: Bir Video Çerçevesi Ekleyin

Daha sonra slayda bir video karesi ekleyin:

```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```

## Adım 5: Video Özelliklerini Yapılandırın

Oynatma modu ve ses seviyesi dahil olmak üzere video özelliklerini ayarlayın:

```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto; // Videoyu otomatik olarak oynat
vf.Volume = AudioVolumeMode.Loud; // Ses seviyesini ayarla
```

## Adım 6: Sununuzu Kaydedin

Son olarak, değiştirilen PPTX dosyasını diske kaydedin:

```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```

Sununuza yerleştirmek istediğiniz her video için bu adımları tekrarlayabilirsiniz.

## Çözüm

Tebrikler! Aspose.Slides for .NET kullanarak sununuza başarıyla bir video karesi yerleştirdiniz. Bu dinamik özellik, kusursuz bir şekilde entegre edilmiş multimedya ile izleyicilerinizi büyüleyerek sunumlarınızı bir üst seviyeye taşıyabilir.

## SSS

### Sunumun herhangi bir slaydına video ekleyebilir miyim?

Evet, dizini ayarlayarak herhangi bir slaydı seçebilirsiniz. `pres.Slides[index]`.

### Hangi video formatları destekleniyor?

Aspose.Slides, MP4, AVI ve WMV dahil olmak üzere çeşitli video formatlarını destekler.

### Video karesinin boyutunu ve konumunu özelleştirebilir miyim?

Kesinlikle! Parametreleri şurada değiştirebilirsiniz: `AddVideoFrame(x, y, width, height, video)` ihtiyaçlarınıza uygun.

### Gömebileceğim video sayısında bir sınırlama var mı?

Gömülü videoların sınırı genellikle sunum yazılımınızın kapasitesine bağlıdır.

### Daha fazla yardıma nereden ulaşabilirim veya deneyimlerimi nerede paylaşabilirim?

Ziyaret etmekten çekinmeyin [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Topluluk desteği ve tartışmaları için.