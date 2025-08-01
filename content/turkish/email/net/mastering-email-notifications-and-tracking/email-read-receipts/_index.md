---
"description": "Aspose.Email for .NET kullanarak e-posta okundu bilgisi istemeyi öğrenin. Geliştiricilerin C# dilinde okuma izlemeyi uygulamaları için adım adım kılavuz."
"linktitle": "Aspose.Email for .NET ile E-postayla Okundu Bilgileri Gönderin"
"second_title": "Aspose.Email .NET E-posta İşleme API'si"
"title": "Aspose.Email for .NET ile E-postayla Okundu Bilgileri Gönderin"
"url": "/tr/email/net/mastering-email-notifications-and-tracking/email-read-receipts/"
"weight": 11
---

## giriiş

Hiç bir e-posta gönderip alıcının ne zaman açtığını bilmeyi dilediniz mi? E-posta okundu bilgisi girin; bu özellik, mesajınızın okunup okunmadığını takip etmenizi sağlar. Bu eğitimde, .NET için Aspose.Email kullanarak e-posta okundu bilgisi istemeyi adım adım anlatacağız. Bir geliştiriciyseniz, bu, yalnızca birkaç satır kodla e-posta iletişimini kolaylaştırma fırsatınız!

Ortamınızı kurmaktan e-postayı izleme özelliği etkin halde göndermeye kadar her adımı ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bu özelliği uygulamada uzman olacaksınız!

## Ön koşullar

Koda dalmadan önce aşağıdakilerin hazır olduğundan emin olun:

1. Aspose.Email for .NET kütüphanesi kuruldu. [Buradan indirin](https://releases.aspose.com/email/net/).
2. Kimlik bilgilerine sahip geçerli bir SMTP sunucusu (ana bilgisayar, kullanıcı adı, şifre).
3. Visual Studio veya uyumlu herhangi bir IDE.
4. .NET Framework yüklü.
5. A [geçici lisans](https://purchase.aspose.com/temporary-license/) eğer deneme sürümünü kullanıyorsanız.

## Paketleri İçe Aktar

Başlamak için, projenize gerekli ad alanlarını eklemeniz gerekir. Bu ad alanları, e-posta göndermek ve okundu bilgisi istemek için gereken sınıfları ve yöntemleri sağlar.

```csharp
using Aspose.Email;
using Aspose.Email.Clients.Smtp;
using Aspose.Email.Mime;
```

## Adım 1: Bir E-posta Mesajı Oluşturun

İlk adım, bir örnek oluşturmaktır `MailMessage` Göndermek istediğiniz e-postayı temsil eden sınıf.

```csharp
MailMessage message = new MailMessage();
```

The `MailMessage` Nesne, gönderen, alıcı, konu, gövde ve başlıklar gibi özellikleri ayarlayacağınız boş bir tuvaldir. Bunu, en sevdiğiniz istemcide bir e-posta taslağı hazırlamak gibi düşünün.

## Adım 2: Gönderen ve Alıcı Ayrıntılarını Ayarlayın

Gönderenin e-posta adresini, alıcının e-posta adresini ve konu ve gövde gibi diğer önemli özellikleri belirtin.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.Subject = "Requesting Read Receipt";
message.HtmlBody = "<html><body>This is the HTML body</body></html>";
```

Burada, gönderenin ve alıcının e-posta adreslerini atıyoruz. Ayrıca, e-postanın konusunu ve gövdesini de HTML kullanarak tanımlıyor ve şık görünmesini sağlıyoruz.

## Adım 3: Teslimat ve Okundu Bildirimlerini Etkinleştirin

Teslimat ve okundu bilgisi talep etmek için başlıklar ekleyin. Bu başlıklar, alıcının e-posta sunucusuna e-posta teslim edildiğinde veya açıldığında sizi bilgilendirmesini söyler.

```csharp
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

- DeliveryNotificationOptions: E-posta başarıyla teslim edildiğinde bir onay ister.
- Return-Receipt-To: E-posta okunduğunda bir makbuz ister.
- Disposition-Notification-To: Okundu bilgileri için kullanılan belirli bir başlık.

## Adım 4: SMTP İstemcisini Yapılandırın

Bir örneğini oluşturun `SmtpClient` sınıfını oluşturun ve SMTP sunucunuzun ayrıntılarıyla yapılandırın.

```csharp
SmtpClient client = new SmtpClient
{
    Host = "smtp.server.com",
    Username = "Username",
    Password = "Password",
    Port = 25
};
```

The `SmtpClient` E-postanızın gönderilmesini yönetir. Değiştir `"smtp.server.com"`, `"Username"`, Ve `"Password"` SMTP sunucunuzun bilgileriyle.

## Adım 5: E-postayı Gönderin

Kullanın `Send` yöntemi `SmtpClient` E-postanızı göndermek için. Sorunsuz bir yürütme sağlamak için istisnaları işleyin.

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

- client.Send(mesaj): Hazırlanan e-postayı gönderir.
- İstisna İşleme: Hatalı sunucu ayrıntıları veya bağlantı sorunları gibi sorunları günlüğe kaydeder.

## Çözüm

İşte bu kadar! Aspose.Email for .NET kullanarak e-posta okundu bilgisi talep eden bir sistemi başarıyla uyguladınız. Bu özellik, önemli e-postaların hak ettiği ilgiyi görmesini sağlamak için çığır açıcı bir özellik. İster işlemsel e-postalar ister önemli iş güncellemeleri gönderiyor olun, okundu bilgisi takibi ek bir sorumluluk katmanı sağlar.

## SSS

### E-postalarda okundu bilgisi nedir?
Okundu bildirimleri, alıcı e-postanızı açtığında aldığınız bildirimlerdir. Mesajınızın okunduğuna dair onay sağlarlar.

### Tüm e-postalar için okundu bilgisi talep edebilir miyim?
Tüm e-posta istemcileri okundu bildirimlerini desteklemez ve alıcılar bunları göndermeyi reddedebilir.

### Aspose.Email for .NET ücretsiz mi?
Bir tane kullanabilirsiniz [ücretsiz deneme sürümü](https://releases.aspose.com/) veya bir lisans satın alın [Aspose web sitesi](https://purchase.aspose.com/buy).

### Aspose.Email e-posta göndermek için ne kadar güvenli?
Aspose.Email, güvenli e-posta iletişimi için SSL/TLS şifrelemesi de dahil olmak üzere güçlü güvenlik özellikleri sağlar.

### E-posta başlıklarını daha fazla özelleştirebilir miyim?
Evet, Aspose.Email belirli gereksinimler için özel başlıklar eklemenize olanak tanır. [dokümantasyon](https://reference.aspose.com/email/net/) Ayrıntılar için.