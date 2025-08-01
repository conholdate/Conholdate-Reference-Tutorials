---
"description": "Aspose.Words for .NET kullanarak Word belgelerinize programatik olarak imza satırları eklemeyi öğrenin. Bu kapsamlı kılavuz, geliştirme ortamınızı kurmaktan imza satırları eklemeye ve belgeleri güvenli bir şekilde imzalamaya kadar her şeyi kapsar."
"linktitle": "Yeni Dijital İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın"
"second_title": "Aspose.Words Belge İşleme API'si"
"title": "Yeni Dijital İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın"
"url": "/tr/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## giriiş

Merhaba teknoloji meraklıları! Word belgelerinize imza satırlarının eklenmesini otomatikleştirmek istediniz mi? Bugün, Aspose.Words for .NET kullanarak bunu nasıl başaracağınızı adım adım ele alacağız. Bu adım adım kılavuz, imza satırı oluşturma ve sağlayıcı kimliğini ayarlama konusunda size yol gösterecek ve belge işleme görevlerinizi daha verimli ve sorunsuz hale getirecek.

## Ön koşullar

Başlamadan önce her şeyin ayarlandığından emin olalım:

1. Aspose.Words for .NET: Henüz yüklemediyseniz indirin [Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir C# geliştirme kurulumunu kullanın.
3. .NET Framework: Bilgisayarınızda .NET Framework'ün yüklü olduğundan emin olun.
4. PFX Sertifikası: Belgeleri imzalamak için güvenilir bir sertifika yetkilisinden edinebileceğiniz bir PFX sertifikasına ihtiyacınız olacak.

## Gerekli Ad Alanlarını İçe Aktarma

Başlamak için gerekli ad alanlarını C# projenize aktarın:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Şimdi yeni imza satırı oluşturmanın ve sağlayıcı kimliğini ayarlamanın detaylarına geçelim.

## Adım 1: Yeni Bir Belge Oluşturun

Öncelikle imza satırımızın tuvali olarak kullanılacak yeni bir Word belgesi oluşturmamız gerekiyor:

```csharp
// Belgelerinizin dizinine giden yolu belirtin.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Burada yeni bir tane başlatıyoruz `Document` ve bir `DocumentBuilder`, öğeleri kolayca eklememizi sağlar.

## Adım 2: İmza Satırı Seçeneklerini Tanımlayın

Daha sonra imza satırımız için imzalayanın adı, ünvanı, e-postası ve diğer ilgili ayrıntılar dahil olmak üzere seçenekleri tanımlayacağız:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Bu seçenekler imza satırının kişiselleştirilmesine, net ve profesyonel hale getirilmesine yardımcı olur.

## Adım 3: İmza Satırını Ekleyin

Seçeneklerimiz hazır olduğuna göre artık imza satırını belgeye ekleyebiliriz:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

The `InsertSignatureLine` metodu imza satırını ekler ve buna benzersiz bir sağlayıcı kimliği atarız.

## Adım 4: Belgeyi Kaydedin

İmza satırını ekledikten sonra belgeyi kaydedelim:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Bu, belgenizi yeni eklenen imza satırıyla kaydeder.

## Adım 5: İmzalama Seçeneklerini Ayarlayın

Şimdi, imza satırı kimliği, sağlayıcı kimliği, yorumlar ve imzalama zamanı dahil olmak üzere imzalama seçeneklerini yapılandıracağız:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Bu ayarlar belgenin doğru bilgilerle imzalanmasını sağlar.

## Adım 6: Sertifika Sahibi Oluşturun

Belgeyi imzalamak için PFX sertifikasını kullanarak bir sertifika sahibi oluşturmamız gerekiyor:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Yer değiştirmek `"morzal.pfx"` gerçek sertifika dosya adınızla ve `"aw"` sertifika şifrenizle.

## 7. Adım: Belgeyi İmzalayın

Son olarak dijital imza aracını kullanarak belgeyi imzalayacağız:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Bu işlem belgeyi imzalar ve yeni bir dosya olarak kaydeder.

## Çözüm

Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesinde imza satırı oluşturdunuz ve sağlayıcı kimliğini başarıyla ayarladınız. Bu güçlü kütüphane, belge işleme görevlerini basitleştirerek iş akışınızı daha verimli hale getirir. Deneyin ve projelerinizi nasıl geliştirebileceğini görün!

## SSS

### İmza satırının görünümünü özelleştirebilir miyim?
Kesinlikle! Çeşitli seçenekleri ayarlayabilirsiniz. `SignatureLineOptions` tarzınıza ve ihtiyaçlarınıza uyacak şekilde.

### PFX sertifikam yoksa ne olur?
Belgeleri dijital olarak imzalamak için gerekli olduğundan, güvenilir bir sertifika yetkilisinden bir sertifika edinmeniz gerekecektir.

### Bir belgeye birden fazla imza satırı ekleyebilir miyim?
Evet, ekleme işlemini farklı seçeneklerle tekrarlayarak birden fazla imza satırı ekleyebilirsiniz.

### Aspose.Words for .NET, .NET Core ile uyumlu mudur?
Evet, Aspose.Words for .NET, .NET Core'u destekler ve bu da onu çeşitli geliştirme ortamları için çok yönlü kılar.

### Dijital imzalar ne kadar güvenli?
Aspose.Words ile oluşturulan dijital imzalar, geçerli ve güvenilir bir sertifika kullanmanız koşuluyla son derece güvenlidir.