---
"description": "C# ve Aspose.Email for .NET kullanarak randevu katılımcılarının durumunu nasıl yöneteceğinizi öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "C# ile Randevu Katılımcıları için Katılımcı Durumunu Ayarlama"
"second_title": "Aspose.Email .NET E-posta İşleme API'si"
"title": "C# ile Randevu Katılımcıları için Katılımcı Durumunu Ayarlama"
"url": "/tr/email/net/handling-email-events-and-calendar/setting-participant-status-for-appointment-attendees/"
"weight": 16
---

## giriiş

Aspose.Email for .NET, .NET uygulamalarında e-posta yönetimini kolaylaştırmak için tasarlanmış, güçlü ve özellik açısından zengin bir kitaplıktır. Bu kılavuz, randevu oluşturma ve yönetme, katılımcı ekleme ve katılımcı durumlarını ayarlama konusunda adım adım bir yol gösterici sunarak .NET projelerinize verimli bir şekilde entegre olmasını sağlar.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Çalışan bir Visual Studio kurulumu veya uyumlu bir C# IDE.
- Aspose.Email for .NET kütüphanesinin en son sürümü.
- C# ve nesne yönelimli programlamanın temel bilgisi.

Kütüphane kurulumu için bkz. [indirme sayfası](https://releases.aspose.com/).

## Gerekli Ad Alanlarını İçe Aktar

Başlamak için randevuları ve e-posta bileşenlerini yönetme işlevlerine erişmek için gerekli ad alanlarını ekleyin.

```csharp
using Aspose.Email;
using Aspose.Email.Calendar;
```

## Bir Randevu Örneği Oluşturun

Aspose.Email'deki randevular, toplantılar veya görevler gibi planlanmış etkinlikleri temsil eder. Randevuları şu şekilde oluşturabilirsiniz:

```csharp
var appointment = new Appointment(
    "Conference Room 101", 
    DateTime.Now, 
    DateTime.Now.AddHours(1), 
    new MailAddress("organizer@example.com"),
    new MailAddressCollection { "attendee1@example.com", "attendee2@example.com" }
);
```

- Yer: Randevunun nerede gerçekleşeceğini belirtir.
- BaşlangıçZamanı ve BitişZamanı: Randevunun süresini tanımlayın.
- Düzenleyici ve Katılımcılar: Katılımcıları ve rollerini tanımlayın.

## Randevulara Katılımcı Ekleme

Aspose.Email, katılımcıları e-posta adresleri ve katılım durumlarıyla programlı bir şekilde yönetmenize olanak tanır.

```csharp
appointment.Attendees.Add(new MailAddress("john@example.com", "John Doe"));
appointment.Attendees.Add(new MailAddress("jane@example.com", "Jane Smith"));
```

## Katılımcı Durumlarını Yönetme

The `ParticipantStatus` özelliği, bir katılımcının randevu davetini kabul edip etmediğini, reddettiğini veya geçici olarak kabul edip etmediğini belirlemeye yardımcı olur. Aşağıdaki numaralandırma değerlerini kullanın:

- Kabul edildi
- Reddedildi
- Geçici

Örnek:

```csharp
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## Randevuları Toplantı Davetiyesi Olarak Gönderme

Randevu hazırlandıktan sonra bunu davet e-postası olarak gönderebilirsiniz:

```csharp
var msg = new MailMessage();
msg.From = "organizer@example.com";
msg.To = new MailAddressCollection { "john@example.com", "jane@example.com" };
msg.Subject = "Team Meeting";
msg.AlternateViews.Add(appointment.RequestApointment());

var client = new SmtpClient("smtp.example.com", 587, "username", "password");
client.Send(msg);
```

## Çözüm

Aspose.Email for .NET, .NET uygulamalarında randevu yönetimini basitleştirerek, planlanmış etkinlikleri verimli bir şekilde oluşturmak, özelleştirmek ve yönetmek için araçlar sunar. Sezgisel API'si sayesinde iletişim iş akışlarını kolaylaştırabilir ve sorunsuz entegrasyon sağlayabilirsiniz.

## SSS

### Aspose.Email for .NET nedir?

Aspose.Email for .NET, .NET uygulamalarında e-posta mesajlarını, randevuları ve diğer ilgili işlevleri yönetmek için kapsamlı bir kütüphanedir.

### Randevu özelliklerini özelleştirebilir miyim?

Evet, lokasyon, başlangıç saati, katılımcılar gibi özellikler tamamen özelleştirilebilir.

### Kütüphane tekrarlayan randevuları destekliyor mu?

Evet, Aspose.Email for .NET, yineleme deseni API'sini kullanarak yinelenen randevuları destekler.

### Aspose.Email for .NET için desteği nereden alabilirim?

Ayrıntılı dokümantasyona ve topluluk desteğine şu adresten erişebilirsiniz: [destek sayfası](https://forum.aspose.com/c/email/11).