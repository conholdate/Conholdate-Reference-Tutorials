---
"description": "Aspose.Cells for .NET kullanarak Excel çalışma sayfalarınızdaki hassas bilgileri belirli satırları koruyarak nasıl güvence altına alacağınızı öğrenin. Bu kapsamlı eğitim, ortamınızı kurmaktan her şeyi kapsar."
"linktitle": "Aspose.Cells Kullanarak Çalışma Sayfasındaki Satırları Koruma"
"second_title": "Aspose.Cells .NET Excel İşleme API'si"
"title": "Aspose.Cells Kullanarak Çalışma Sayfasındaki Satırları Koruma"
"url": "/tr/cells/net/mastering-worksheet-security/protecting-rows/"
"weight": 18
---

## giriiş

Excel dosyalarıyla programatik olarak çalışmak genellikle yalnızca veri işlemeyi değil, aynı zamanda veri korumasını da gerektirir. Bir çalışma sayfasındaki belirli satırları korumak, hassas bilgileri korumak veya yanlışlıkla düzenlemeleri önlemek için çok önemli olabilir. Bu eğitimde, .NET için Aspose.Cells kullanarak bir Excel çalışma sayfasındaki satırları nasıl koruyacağımızı inceleyeceğiz. Ortamınızı kurmaktan satır koruma özelliklerini basit bir şekilde uygulamaya kadar gerekli adımlarda size rehberlik edeceğiz.

## Ön koşullar
Başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:

1. Aspose.Cells for .NET: İndirin ve yükleyin [Aspose Cells indirme sayfası](https://releases.aspose.com/cells/net/).
2. Visual Studio veya Herhangi Bir .NET IDE: Bir geliştirme ortamına ihtiyacınız var. Visual Studio önerilir, ancak herhangi bir .NET uyumlu IDE yeterli olacaktır.
3. Temel C# Bilgisi: C# programlamaya aşinalık, örnek kodu takip etmenize ve gerektiğinde değiştirmenize yardımcı olacaktır.
4. Aspose.Cells API Belgeleri: İnceleme [Aspose.Cells for .NET belgeleri](https://reference.aspose.com/cells/net/) Sınıf yapısı ve yöntemlerine genel bir bakış için.

Ön koşullar hazır olduğunda uygulamaya geçebiliriz.

## Gerekli Paketleri İçe Aktar
Öncelikle C# projenize gerekli paketleri aktarın. Bu kütüphaneler, Excel dosyalarıyla etkileşim kurmak için olmazsa olmazdır.

```csharp
using System.IO;
using Aspose.Cells;
```

## Adım 1: Yeni bir Çalışma Kitabı ve Çalışma Sayfası Oluşturun
Herhangi bir koruma ayarını uygulamadan önce yeni bir çalışma kitabı oluşturun ve üzerinde çalışmak istediğiniz çalışma sayfasını seçin.

```csharp
// Belgeler dizinine giden yolu tanımlayın.
string dataDir = "Your Document Directory";
// Eğer dizin yoksa oluşturun.
if (!Directory.Exists(dataDir))
    Directory.CreateDirectory(dataDir);

// Yeni bir çalışma kitabı oluşturun ve ilk çalışma sayfasını seçin.
Workbook wb = new Workbook();
Worksheet sheet = wb.Worksheets[0];
```

## Adım 2: Stil ve Stil Bayrağı Nesnelerini Tanımlayın
Hücre özelliklerini değiştirmenize (örneğin, kilitleme veya kilidini açma) olanak sağlayacak stil ve stil bayrağı nesnelerini tanımlayın.

```csharp
// Stil ve stil bayrağı nesnelerini tanımlayın.
Style style;
StyleFlag flag;
```

## Adım 3: Çalışma Sayfasındaki Tüm Sütunların Kilidini Açın
Varsayılan olarak, bir Excel çalışma sayfasındaki tüm hücreler kilitlidir. Yalnızca belirli satırları korumak için önce tüm sütunların kilidini açın.

```csharp
// Tüm sütunları dolaşın ve kilidini açın.
for (int i = 0; i <= 255; i++)
{
    style = sheet.Cells.Columns[i].Style;
    style.IsLocked = false;
    flag = new StyleFlag { Locked = true };
    sheet.Cells.Columns[i].ApplyStyle(style, flag);
}
```

## Adım 4: Belirli Satırları Kilitle
Şimdi, korumak istediğiniz satırları kilitleyin. Bu örnekte, ilk satırı kilitleyeceğiz.

```csharp
// İlk satırı kilitle.
style = sheet.Cells.Rows[0].Style;
style.IsLocked = true;
flag = new StyleFlag { Locked = true };
sheet.Cells.ApplyRowStyle(0, style, flag);
```

Kilitlemek istediğiniz ek satırlar için bu adımı tekrarlayabilirsiniz.

## Adım 5: Sayfayı Koruyun
Gerekli satırlar kilitlendikten sonra, çalışma sayfasını koruma zamanı geldi. Bu, koruma kaldırılmadığı sürece kilitli satırlarda değişiklik yapılmasını engelleyecektir.

```csharp
// Sayfayı koruyun.
sheet.Protect(ProtectionType.All);
```

## Adım 6: Çalışma Kitabını Kaydedin
Son olarak, çalışma kitabını uygulanan değişikliklerle kaydedin. Excel 97-2003 veya daha yeni sürümler gibi çeşitli biçimlerden birini seçebilirsiniz.

```csharp
// Excel dosyasını kaydedin.
wb.Save(dataDir + "output.out.xls", SaveFormat.Excel97To2003);
```

## Çözüm
Tebrikler! Aspose.Cells for .NET kullanarak bir Excel çalışma sayfasındaki satırları nasıl koruyacağınızı başarıyla öğrendiniz. Bu adımları izleyerek, gerektiğinde satır veya sütunların kilidini açabilir veya kilitleyebilir ve verilerinizin bütünlüğünü korumak için koruma uygulayabilirsiniz.

## SSS
### Birden fazla satırı aynı anda nasıl koruyabilirim?
Birden fazla satır indeksi arasında döngü oluşturabilir ve kilitleme stilini her birine ayrı ayrı uygulayabilirsiniz.

### Sayfa koruması için şifre belirleyebilir miyim?
Evet, bir şifreyi şuraya iletebilirsiniz: `sheet.Protect()` Şifre korumasını zorunlu kılma yöntemi.

### Tüm sütunlar yerine belirli hücrelerin kilidini açabilir miyim?
Evet, tüm sütunların kilidini açmak yerine, stil özelliklerini değiştirerek tek tek hücrelerin kilidini açabilirsiniz.

### Korunan bir satırı düzenlemeye çalışırsam ne olur?
Bir satır korunduğunda, Excel, sayfa korumasız olmadığı sürece kilitli hücrelerde herhangi bir düzenleme yapılmasını engeller.

### Bir satırdaki belirli aralıkları koruyabilir miyim?
Evet! Tek tek aralıkları, şu ayarı yaparak arka arkaya kilitleyebilirsiniz: `IsLocked` Bu aralıktaki belirli hücreler için özellik.