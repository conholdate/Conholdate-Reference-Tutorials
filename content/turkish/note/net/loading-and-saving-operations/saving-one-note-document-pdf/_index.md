---
"description": "Aspose.Note for .NET kullanarak Microsoft OneNote belgelerini PDF dosyaları olarak nasıl verimli bir şekilde kaydedeceğinizi öğrenin. Bu kılavuz, gerekli ön koşulları ele alıyor ve faydalı SSS'ler sunuyor."
"linktitle": "OneNote Belgelerini PDF Olarak Kaydetme"
"second_title": "Aspose.Note .NET API"
"title": "Aspose.Note for .NET Kullanarak OneNote Belgelerini PDF Olarak Kaydetme"
"url": "/tr/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## giriiş

Bu eğitimde, .NET için Aspose.Note kullanarak belgeleri PDF formatına nasıl kaydedeceğimizi inceleyeceğiz. Aspose.Note, geliştiricilerin Microsoft OneNote dosyalarıyla programatik olarak çalışmasını sağlayan güçlü bir kütüphanedir. Ön koşulları ele alacağız, ad alanlarını içe aktaracağız ve belgeleri çeşitli sayfa düzenlerinde PDF'ye kaydetmek için adım adım kılavuzlar sunacağız.

## Ön koşullar
1. Visual Studio: Kurulu olduğundan emin olun.
2. Aspose.Note for .NET: Kütüphaneyi indirin ve kurun.
3. C# Bilgisi: Dilin temel düzeyde anlaşılması gerekmektedir.

## Gerekli Ad Alanlarını İçe Aktarma
Devam etmeden önce, aşağıdaki ad alanlarını kodunuza aktarın:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Adım 1: Mektup Sayfası Ayarlarıyla PDF'e Kaydet
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Bu yolu güncelle
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
OneNote belgesini yükler ve letter boyutlu sayfa ayarlarını kullanarak PDF olarak kaydeder.

## Adım 2: A4 Sayfa Ayarlarıyla PDF'e Kaydet (Yükseklik Sınırı Yok)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Bu yolu güncelle
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
1. Adıma benzer ancak yükseklik sınırlaması olmadan A4 sayfa ayarlarını kullanır.

## Çözüm
Eğitim, OneNote dosyalarının Aspose.Note kullanılarak PDF formatına nasıl dönüştürüleceğini başarıyla göstermektedir. Geliştiriciler, farklı sayfa ayarlarını kullanarak belge yönetiminde esneklik kazanırlar.

## SSS
### Aspose.Note karmaşık OneNote dosyalarını işleyebilir mi?
Evet, karmaşık OneNote dosyalarının çeşitli özelliklerini etkili bir şekilde yönetir.

### Aspose.Note ticari projeler için uygun mudur?
Evet, lisans satın aldıktan sonra ticari uygulamalarda kullanabilirsiniz.

### Aspose.Note ücretsiz deneme sürümü sunuyor mu?
Evet, ücretsiz deneme sürümü mevcuttur.

### Aspose.Note'a ilişkin dokümanları nerede bulabilirim?
Ayrıntılı dokümanlar Aspose referans sitesinde mevcuttur.

### Daha fazla yardıma mı ihtiyacınız var?
Sorularınız ve destek için Aspose.Note forumuna başvurun.