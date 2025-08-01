---
"description": "تعرّف على كيفية إدارة حالة المشاركين في المواعيد باستخدام C# وAspose.Email لـ .NET. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "تعيين حالة المشارك لحضور الموعد باستخدام C#"
"second_title": "واجهة برمجة تطبيقات معالجة البريد الإلكتروني Aspose.Email .NET"
"title": "تعيين حالة المشارك لحضور الموعد باستخدام C#"
"url": "/ar/email/net/handling-email-events-and-calendar/setting-participant-status-for-appointment-attendees/"
"weight": 16
---

## مقدمة

Aspose.Email لـ .NET هي مكتبة قوية وغنية بالميزات، مصممة لتبسيط إدارة البريد الإلكتروني في تطبيقات .NET. يقدم هذا الدليل شرحًا تفصيليًا لإنشاء وإدارة المواعيد، وإضافة الحضور، وتعيين حالات المشاركين، مما يضمن تكاملًا فعالًا مع مشاريع .NET الخاصة بك.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تثبيت عمل لبرنامج Visual Studio أو C# IDE متوافق.
- الإصدار الأحدث من مكتبة Aspose.Email لـ .NET.
- المعرفة الأساسية بلغة C# والبرمجة الكائنية التوجه.

لتثبيت المكتبة، راجع [صفحة التحميل](https://releases.aspose.com/).

## استيراد مساحات الأسماء المطلوبة

للبدء، قم بتضمين مساحات الأسماء الضرورية للوصول إلى الوظائف اللازمة لإدارة المواعيد ومكونات البريد الإلكتروني.

```csharp
using Aspose.Email;
using Aspose.Email.Calendar;
```

## إنشاء مثيل للموعد

المواعيد في Aspose.Email تُمثّل أحداثًا مُجدولة، مثل الاجتماعات أو المهام. إليك كيفية إنشائها:

```csharp
var appointment = new Appointment(
    "Conference Room 101", 
    DateTime.Now, 
    DateTime.Now.AddHours(1), 
    new MailAddress("organizer@example.com"),
    new MailAddressCollection { "attendee1@example.com", "attendee2@example.com" }
);
```

- الموقع: يحدد المكان الذي سيحدث فيه الموعد.
- وقت البدء ووقت الانتهاء: تحديد مدة الموعد.
- المنظمون والحضور: تحديد المشاركين وأدوارهم.

## إضافة الحضور إلى المواعيد

يتيح لك Aspose.Email إدارة الحضور برمجيًا باستخدام عناوين بريدهم الإلكتروني وحالات مشاركتهم.

```csharp
appointment.Attendees.Add(new MailAddress("john@example.com", "John Doe"));
appointment.Attendees.Add(new MailAddress("jane@example.com", "Jane Smith"));
```

## إدارة حالات المشاركين

ال `ParticipantStatus` تساعد الخاصية في تحديد ما إذا كان الحاضر قد قبل دعوة الموعد، أو رفضها، أو قبلها مبدئيًا. استخدم قيم التعداد التالية:

- مقبول
- انخفض
- مُتَردِّد

مثال:

```csharp
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## إرسال المواعيد كدعوات اجتماعات

بمجرد إعداد الموعد، يمكنك إرساله كرسالة بريد إلكتروني للدعوة:

```csharp
var msg = new MailMessage();
msg.From = "organizer@example.com";
msg.To = new MailAddressCollection { "john@example.com", "jane@example.com" };
msg.Subject = "Team Meeting";
msg.AlternateViews.Add(appointment.RequestApointment());

var client = new SmtpClient("smtp.example.com", 587, "username", "password");
client.Send(msg);
```

## خاتمة

يُبسّط Aspose.Email لـ .NET إدارة المواعيد في تطبيقات .NET، مُوفّرًا أدواتٍ لإنشاء وتخصيص وإدارة الأحداث المجدولة بكفاءة. بفضل واجهة برمجة التطبيقات سهلة الاستخدام، يُمكنك تبسيط سير عمل الاتصالات وضمان التكامل السلس.

## الأسئلة الشائعة

### ما هو Aspose.Email لـ .NET؟

Aspose.Email for .NET عبارة عن مكتبة شاملة للتعامل مع رسائل البريد الإلكتروني والمواعيد والوظائف الأخرى ذات الصلة في تطبيقات .NET.

### هل يمكنني تخصيص خصائص الموعد؟

نعم، يمكن تخصيص خصائص مثل الموقع ووقت البدء والمشاركين بالكامل.

### هل تدعم المكتبة المواعيد المتكررة؟

نعم، يدعم Aspose.Email لـ .NET المواعيد المتكررة باستخدام واجهة برمجة التطبيقات الخاصة بنمط التكرار.

### أين يمكنني الحصول على الدعم لـ Aspose.Email لـ .NET؟

يمكنك الوصول إلى الوثائق التفصيلية ودعم المجتمع على [صفحة الدعم](https://forum.aspose.com/c/email/11).