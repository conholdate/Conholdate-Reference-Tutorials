---
"description": "Aspose.Cells for .NET kullanarak mevcut imzalı bir Excel dosyasına yeni bir dijital imza eklemeyi öğrenin. Bu kapsamlı kılavuz, tüm ön koşulları, adım adım talimatları ve kod örneklerini kapsar."
"linktitle": "İmzalanmış Excel Dosyasına Yeni Bir Dijital İmza Ekleme"
"second_title": "Aspose.Cells .NET Excel İşleme API'si"
"title": "İmzalanmış Excel Dosyasına Yeni Bir Dijital İmza Ekleme"
"url": "/tr/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## giriiş

Günümüzün dijital dünyasında, belgelerin gerçekliğini ve bütünlüğünü sağlamak her zamankinden daha önemli. Dijital imzalar, bir belgenin değiştirilmediğini ve meşru bir kaynaktan geldiğini doğrulamanın güvenilir bir yolunu sunar. .NET'te Excel dosyalarıyla çalışıyorsanız ve önceden imzalanmış bir dosyaya yeni bir dijital imza eklemeniz gerekiyorsa, bu kılavuz tam size göre! .NET için Aspose.Cells kullanarak mevcut imzalı bir Excel dosyasına dijital imza ekleme sürecini adım adım inceleyeceğiz.

## Ön koşullar

Uygulamaya geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

1. .NET için Aspose.Cells: Aspose.Cells'i indirin ve yükleyin [yayın sayfası](https://releases.aspose.com/cells/net/).
2. .NET Framework: Makinenizde .NET Framework'ün kurulu olduğundan ve temel .NET programlama kavramlarına aşina olduğunuzdan emin olun.
3. Dijital Sertifika: .pfx formatında geçerli bir dijital sertifika edinin. Test için kendi imzalı bir sertifika oluşturabilirsiniz.
4. Geliştirme Ortamı: C# kodunuzu yazmak ve çalıştırmak için Visual Studio gibi bir IDE kullanın.
5. Örnek Excel Dosyası: Dijital olarak imzalanmış mevcut bir Excel dosyanız olsun; bu dosya, yeni bir imza eklemenin hedefi olacaktır.

Bu ön koşullar sağlandıktan sonra koda geçelim!

## Gerekli Paketleri İçe Aktar

C# dosyanızın en üstüne, gerekli sınıflara ve yöntemlere erişmek için aşağıdaki ad alanlarını ekleyin:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Adım 1: Dizinlerinizi Tanımlayın

Kaynak dosyalarınızın dizinlerini ve çıktı dosyasının nereye kaydedileceğini belirtin:

```csharp
// Kaynak dizini
string sourceDir = "Your Document Directory"; // Gerçek dizininizle değiştirin
// Çıktı dizini
string outputDir = "Your Document Directory"; // Gerçek dizininizle değiştirin
```

## Adım 2: Mevcut İmzalı Çalışma Kitabını Yükleyin

Zaten imzalanmış olan Excel çalışma kitabını yükleyin:

```csharp
// Zaten dijital olarak imzalanmış olan çalışma kitabını yükleyin
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## Adım 3: Dijital İmza Koleksiyonu Oluşturun

Dijital imzalarınızı yönetmek için bir koleksiyon oluşturun:

```csharp
// Dijital imza koleksiyonunu oluşturun
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## Adım 4: Sertifikanızı Yükleyin

Yeni imzayı oluşturmak için kullanılacak dijital sertifikanızı yükleyin:

```csharp
// Sertifika dosyası ve şifresi
string certFileName = sourceDir + "AsposeDemo.pfx"; // Sertifika dosyanız
string password = "aspose"; // Sertifika şifreniz

// Yeni sertifika oluştur
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## Adım 5: Yeni Bir Dijital İmza Oluşturun

Şimdi yeni bir dijital imza oluşturun ve koleksiyonunuza ekleyin:

```csharp
// Yeni dijital imza oluşturun ve koleksiyona ekleyin
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## Adım 6: İmza Koleksiyonunu Çalışma Kitabına Ekleyin

Dijital imza koleksiyonunu çalışma kitabına ekleyin:

```csharp
// Dijital imza koleksiyonunu çalışma kitabına ekleyin
workbook.AddDigitalSignature(dsCollection);
```

## Adım 7: Çalışma Kitabını Kaydedin

Çalışma kitabını yeni dijital imzayla birlikte kaydedin:

```csharp
// Çalışma kitabını kaydet
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## Adım 8: Başarılı Olduğunu Onaylayın

Başarılı uygulama sonrasında geri bildirim sağlayın:

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## Çözüm

Tebrikler! Aspose.Cells for .NET kullanarak imzalanmış bir Excel dosyasına başarıyla yeni bir dijital imza eklediniz. Bu işlem, belgelerinizin güvenliğini artırır ve orijinalliklerini ve bütünlüklerini garanti altına alır.

## SSS

### Dijital imza nedir?

Dijital imza, dijital mesajların veya belgelerin gerçekliğini ve bütünlüğünü doğrulayan, bunların değiştirilmediğini ve imzalayanın kimliğini doğrulayan matematiksel bir şemadır.

### Dijital imza oluşturmak için özel bir sertifikaya ihtiyacım var mı?

Evet, geçerli bir dijital imza oluşturmak için güvenilir bir sertifika yetkilisi (CA) tarafından verilen bir dijital sertifika gereklidir.

### Test için kendi imzalı sertifikayı kullanabilir miyim?

Kesinlikle! Geliştirme ve test amaçlı olarak kendi imzalı bir sertifika kullanabilirsiniz, ancak üretim için güvenilir bir CA'dan sertifika kullanmanız önerilir.

### İmzalanmamış bir belgeye imza eklemeye çalışırsam ne olur?

İmzalanmamış bir belgeye dijital imza eklemeye çalışırsanız sorunsuz çalışacaktır ancak orijinal imza mevcut olmayacaktır.

### Aspose.Cells hakkında daha fazla bilgiyi nerede bulabilirim?

Ayrıntılı kılavuzlar ve API referansları için şuraya bakın: [Aspose.Cells belgeleri](https://reference.aspose.com/cells/net/).