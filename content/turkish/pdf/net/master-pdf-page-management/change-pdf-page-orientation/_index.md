---
"description": "Aspose.PDF for .NET kullanarak PDF dosyalarının sayfa yönünü nasıl kolayca ayarlayabileceğinizi keşfedin. Bu adım adım kılavuz, belgelerinizi yükleme, döndürme ve kaydetme konusunda net talimatlar sağlar."
"linktitle": "PDF Sayfa Yönünü Değiştir"
"second_title": ".NET API Referansı için Aspose.PDF"
"title": "PDF Sayfa Yönünü Değiştir"
"url": "/tr/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## giriiş

Sayfa yönü tamamen yanlış olan bir PDF dosyasıyla hiç karşılaştınız mı? İster yanlış taranmış bir belge olsun, ister sadece farklı bir düzen gerektiren bir belge olsun, yönü ayarlamak büyük fark yaratabilir. Neyse ki, Aspose.PDF for .NET, sayfa yönünü değiştirmek de dahil olmak üzere PDF dosyalarını düzenlemenin güçlü ve kullanıcı dostu bir yolunu sunuyor. Bu kılavuzda, ister dikeyden yataya ister tam tersine geçiş yapmak isteyin, süreci adım adım anlatacağız.

## Ön koşullar

Ayrıntılara girmeden önce aşağıdakilerin mevcut olduğundan emin olun:

- .NET için Aspose.PDF: Aspose.PDF kitaplığının yüklü olduğundan emin olun. Bunu henüz yapmadıysanız, [buradan indirin](https://releases.aspose.com/pdf/net/).
- .NET Geliştirme Ortamı: .NET geliştirme için Visual Studio, JetBrains Rider veya tercih ettiğiniz herhangi bir IDE'yi kullanabilirsiniz.
- C# Temel Bilgisi: C#'a aşina olmak, konuyu daha kolay takip etmenize yardımcı olacaktır.
- PDF Dosyası: Test için hazır bir örnek PDF dosyası bulundurun. Bir tane oluşturabilir veya çevrimiçi olarak indirebilirsiniz.

Eğer yeni başlıyorsanız, Aspose.PDF'yi denemeyi düşünün [ücretsiz geçici lisans](https://purchase.aspose.com/temporary-license/) karar vermeden önce [tam sürümü satın al](https://purchase.aspose.com/buy).

## Ad Alanlarını İçe Aktar

PDF sayfalarını düzenlemek için öncelikle C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Kod dosyanızın en üstüne aşağıdaki satırları ekleyin:

```csharp
using System.IO;
using Aspose.Pdf;
```

Artık her şey hazır olduğuna göre, başlayalım!

## Adım 1: PDF Belgesini yükleyin

İlk adım, değiştirmek istediğiniz PDF dosyasını yüklemektir. `Document` Aspose.PDF ad alanından sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Değiştirdiğinizden emin olun `"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın gerçek yolunu belirtin.

## Adım 2: Her Sayfada Döngü Yapın

Ardından, PDF belgesindeki her sayfayı dolaşacağız. Bu, yön değişikliğini tüm sayfalara uygulamamızı sağlar:

```csharp
foreach (Page page in doc.Pages)
{
    // Her sayfayı düzenleyin
}
```

## Adım 3: Sayfanın MediaBox'ına erişin

Her PDF sayfasının bir `MediaBox` Sınırlarını tanımlayan bu alana erişmemiz gerekiyor. Mevcut yönelimi kontrol etmek ve ayarlamalar yapmak için buna erişmemiz gerekiyor:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

The `MediaBox` sayfanın genişlik ve yükseklik dahil boyutlarını sağlar.

## Adım 4: Genişlik ve Yüksekliği Değiştirin

Sayfa yönünü değiştirmek için genişlik ve yükseklik değerlerini değiştireceğiz. Bu ayarlama, sayfanın boyutlarını değiştirecektir:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Burada, yeni boyutları hesaplıyoruz ve sol alt köşeyi yeniden konumlandırıyoruz (`LLY`) buna göre.

## Adım 5: MediaBox ve CropBox'ı güncelleyin

Artık yeni boyutlara sahip olduğumuza göre, bu değişiklikleri şuraya uygulayacağız: `MediaBox` Ve `CropBox` sayfanın doğru görüntülenmesini sağlamak için:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Adım 6: Sayfayı Döndürün

Yönlendirme değişikliğini tamamlamak için sayfayı döndüreceğiz. Bu, Aspose.PDF ile oldukça basit:

```csharp
page.Rotate = Rotation.on90; // 90 derece döndür
```

Bu çizgi, sayfayı istenen yöne çevirir.

## Adım 7: Çıktı PDF'sini Kaydedin

Tüm sayfaların yönlendirmesini değiştirdikten sonra güncellenen belgeyi yeni bir dosyaya kaydedin:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Orijinal belgenin üzerine yazılmasını önlemek için yeni bir dosya adı sağladığınızdan emin olun.

## Çözüm

İşte bu kadar! Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa yönünü değiştirmek oldukça basit bir işlemdir. Belgeyi yükleyerek, sayfalar arasında geçiş yaparak, MediaBox'ı güncelleyerek ve dosyayı kaydederek, düzeni ihtiyaçlarınıza göre kolayca ayarlayabilirsiniz. İster kötü taranmış bir belgeyi düzeltiyor olun, ister sunum için sayfaları biçimlendiriyor olun, bu kılavuz işinizi verimli bir şekilde yapmanıza yardımcı olacaktır.

## SSS

### PDF'deki tüm sayfalar yerine belirli sayfaları döndürebilir miyim?  
Evet, tüm sayfalarda yineleme yapmak yerine, döngüyü belirli sayfaları dizinlerine göre hedefleyecek şekilde değiştirebilirsiniz.

### Nedir? `MediaBox`?  
The `MediaBox` PDF dosyasındaki sayfanın boyutunu ve şeklini tanımlar, içeriğin nereye yerleştirileceğini belirler.

### Aspose.PDF for .NET diğer dosya formatlarıyla çalışır mı?  
Evet, Aspose.PDF HTML, XML, XPS ve daha fazlası dahil olmak üzere çeşitli dosya biçimlerini işleyebilir.

### Aspose.PDF'in .NET için ücretsiz bir sürümü var mı?  
Evet, bir ile başlayabilirsiniz [ücretsiz deneme](https://releases.aspose.com/) veya bir talepte bulunun [geçici lisans](https://purchase.aspose.com/temporary-license/).

### Kaydettiğim değişiklikleri geri alabilir miyim?  
Belgeyi kaydettiğinizde değişiklikler kalıcı olur. Orijinal dosyanın bir kopyası üzerinde çalışmanız veya yedeğini almanız önerilir.