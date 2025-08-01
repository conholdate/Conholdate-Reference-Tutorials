---
"description": "Aspose.Words for .NET kullanarak Word belgelerindeki içeriklerin görünürlüğünü nasıl uzmanca kontrol edeceğinizi adım adım öğrenin."
"linktitle": "Word Belgelerinde Yer İşareti Görünürlüğünü Yönetme"
"second_title": "Aspose.Words Belge İşleme API'si"
"title": "Word Belgelerinde Yer İşareti Görünürlüğünü Yönetme"
"url": "/tr/words/net/mastering-bookmarks/manage-bookmark-visibility-word-document/"
"weight": 10
---

## giriiş

Aspose.Words for .NET ile belge düzenleme becerilerinizi geliştirmeye hazır mısınız? İster belge görevlerini otomatikleştiren deneyimli bir geliştirici olun, ister Word dosyaları üzerinde programatik kontrolü araştıran meraklı bir kişi olun, bu kılavuz tam size göre. Bugün, bir Word belgesindeki yer imlerine göre içeriğin nasıl gösterilip gizleneceğini inceleyeceğiz. Haydi başlayalım!

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: .NET ile uyumlu herhangi bir sürüm.
2. Aspose.Words for .NET: İndirin [Burada](https://releases.aspose.com/words/net/).
3. Temel C# Bilgisi: Basit C# programları yazma konusunda bilgi sahibi olmak yeterli olacaktır.
4. Örnek Bir Word Belgesi: Bu eğitim için yer imlerini içeren bir Word belgesi hazırlayın (örneğin, "Bookmarks.docx").

### Yeni Bir Proje Oluşturun

1. Visual Studio'yu açın ve yeni bir Konsol Uygulaması (.NET Core) projesi oluşturun. Projeye "BookmarkVisibilityManager" gibi bir isim verin.

### .NET için Aspose.Words'ü yükleyin

Aspose.Words'ü NuGet Paket Yöneticisi aracılığıyla projenize ekleyin:

1. Araçlar > NuGet Paket Yöneticisi > Çözüm için NuGet Paketlerini Yönet'e gidin.
2. "Aspose.Words" ifadesini arayın.
3. Paketi kurun.

Projeniz hazır olduğuna göre, belgeyi yüklemeye geçelim.

## Ad Alanlarını İçe Aktarma

Temel ad alanlarını içe aktararak başlayın. Bunlar, Word belgelerini Aspose.Words ile düzenlemek için gerekli sınıfları ve yöntemleri sağlar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

## Adım 1: Belgeyi Yükleme

Word belgesini düzenlemek için önce yüklememiz gerekiyor. Bunu şu şekilde yapabilirsiniz:

```csharp
// Belge dizininize giden yolu tanımlayın.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

Bu kod parçası belge dizininize giden yolu ayarlar ve belgeyi bir `Document` nesne.

## Adım 2: Yer İşaretli İçeriği Göster/Gizle

Şimdi, yer imlerine göre içerik görünürlüğünü değiştirecek bir yöntem oluşturalım. Bu yönteme şu adı vereceğiz: `ShowHideBookmarkedContent`.

İşte yöntemin uygulanması:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    if (bm != null)
    {
        Node currentNode = bm.BookmarkStart;
        while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
        {
            if (currentNode.NodeType == NodeType.Run)
            {
                Run run = (Run)currentNode;
                run.Font.Hidden = isHidden;
            }
            currentNode = currentNode.NextSibling;
        }
    }
}
```

- Yer İmi Alma: `Bookmark bm = doc.Range.Bookmarks[bookmarkName];` belirtilen yer imini getirir.
- Düğüm Gezintisi: Yer imi içindeki düğümler arasında yineleme yaparız.
- Görünürlük Açma/Kapatma: Her biri için `Run` (Metnin bir bölümünü temsil eden) düğümü ayarlıyoruz `Hidden` mülkiyete dayalı `isHidden` parametre.

## Adım 3: Yöntemin Uygulanması

Artık metodumuz hazır olduğuna göre, onu belirli bir yer imindeki içeriği göstermek veya gizlemek için kullanabiliriz:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true); // "MyBookmark1" içindeki içeriği gizler
```

Bu satır "MyBookmark1" adlı yer imiyle ilişkili içeriği gizleyecektir.

## Adım 4: Belgeyi Kaydetme

Değişikliklerinizi yaptıktan sonra, değiştirilen belgeyi kaydetmeyi unutmayın:

```csharp
doc.Save(dataDir + "UpdatedBookmarks.docx");
```

Bu, belgeyi güncellenmiş görünürlük ayarlarıyla kaydeder.

## Çözüm

Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesinde yer imlerine eklenen içeriği nasıl gösterip gizleyeceğinizi başarıyla öğrendiniz. Bu güçlü kütüphane, belge düzenlemeyi basitleştirerek raporları otomatikleştirmek, şablon oluşturmak veya Word dosyalarıyla denemeler yapmak için idealdir. Keyifli kodlamalar!

## SSS

### Birden fazla yer imini aynı anda açıp kapatabilir miyim?
Evet, sadece arayın `ShowHideBookmarkedContent` Geçiş yapmak istediğiniz her yer imi için bir yöntem.

### İçeriği gizlemek belgenin yapısını etkiler mi?
Hayır, içeriği gizlemek yalnızca görünürlüğünü etkiler; içerik belge içerisinde bozulmadan kalır.

### Bu yöntemi diğer içerik türleri için de kullanabilir miyim?
Bu yöntem özellikle metin çalıştırmaları için tasarlanmıştır. Diğer içerik türleri için, düğüm geçiş mantığını buna göre uyarlamanız gerekecektir.

### Aspose.Words for .NET ücretsiz mi?
Aspose.Words ücretsiz deneme sunuyor [Burada](https://releases.aspose.com/)Ancak üretim amaçlı kullanım için tam lisans gereklidir. Satın alabilirsiniz [Burada](https://purchase.aspose.com/buy).

### Sorun yaşarsam nasıl destek alabilirim?
Destek için Aspose topluluk forumunu ziyaret edin [Burada](https://forum.aspose.com/c/words/8).