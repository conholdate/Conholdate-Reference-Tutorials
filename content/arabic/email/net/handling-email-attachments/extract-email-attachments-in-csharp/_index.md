---
"description": "تعلّم كيفية استخراج مرفقات البريد الإلكتروني بلغة C# باستخدام Aspose.Email لـ .NET. دليل خطوة بخطوة مع أمثلة لملفات PDF والصور وغيرها."
"linktitle": "استخراج مرفقات البريد الإلكتروني بلغة C# - برنامج تعليمي لـ Aspose.Email"
"second_title": "واجهة برمجة تطبيقات معالجة البريد الإلكتروني Aspose.Email .NET"
"title": "استخراج مرفقات البريد الإلكتروني بلغة C# - برنامج تعليمي لـ Aspose.Email"
"url": "/ar/email/net/handling-email-attachments/extract-email-attachments-in-csharp/"
"weight": 14
---

## مقدمة

هل سبق لك أن وجدت نفسك تُنزّل مرفقات بريد إلكتروني يدويًا، واحدًا تلو الآخر؟ هذا ليس مُستهلكًا للوقت فحسب، بل مُعرّضًا للأخطاء أيضًا. لحسن الحظ، يُقدّم Aspose.Email لـ .NET طريقة فعّالة وفعّالة لأتمتة هذه المهمة. سواء كنت تتعامل مع ملفات PDF أو صور أو أي نوع ملفات آخر، يُمكنك استخراج المرفقات بسهولة باستخدام C#.

في هذا الدليل، سنشرح لك شرحًا شاملًا، بدءًا من المتطلبات الأساسية وصولًا إلى مثال عملي. هل أنت مستعد لتوفير ساعات من العمل اليدوي؟ هيا بنا!

## المتطلبات الأساسية

قبل البدء في الترميز، تأكد من أن لديك ما يلي:

- تم تثبيت Visual Studio على جهازك.
- مكتبة Aspose.Email لـ .NET. يمكنك [قم بتحميله هنا](https://releases.aspose.com/email/net/) أو قم بتثبيته عبر NuGet.
- حساب بريد إلكتروني صالح (يدعم IMAP/POP3).
- فهم أساسي لبرمجة C#.

إذا كنت جديدًا على Aspose.Email، ففكر في طلب [نسخة تجريبية مجانية](https://releases.aspose.com/) أو أ [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لفتح الميزات الكاملة.

## استيراد الحزم

قبل البدء في الكود، تأكد من استيراد مساحات الأسماء اللازمة. أضف ما يلي في أعلى ملف C#:

```csharp
using Aspose.Email;
using Aspose.Email.Clients.Imap;
using Aspose.Email.Clients.Pop3;
```

لنُقسّم العملية إلى خطوات سهلة الفهم. اتبع كل خطوة بعناية لضمان التنفيذ السلس.


## الخطوة 1: إعداد عميل IMAP الخاص بك

الخطوة الأولى هي الاتصال بخادم البريد الإلكتروني الخاص بك باستخدام بروتوكول IMAP. يتيح لنا IMAP الوصول إلى رسائل البريد الإلكتروني واسترجاعها من الخادم.

```csharp
ImapClient client = new ImapClient("imap.example.com", "username", "password");
client.SelectFolder(ImapFolderInfo.InBox);
```

- يستبدل `imap.example.com` مع عنوان خادم IMAP الخاص بمزود البريد الإلكتروني الخاص بك (على سبيل المثال، `imap.gmail.com` (للبريد الإلكتروني Gmail).
- استخدم بريدك الإلكتروني الفعلي `username` و `password`.
- `SelectFolder(ImapFolderInfo.InBox)` يحدد أننا نريد العمل مع البريد الوارد.


## الخطوة 2: استرداد رسائل البريد الإلكتروني من صندوق الوارد

بعد الاتصال، ستحتاج إلى جلب رسائل البريد الإلكتروني من صندوق الوارد. يوفر Aspose.Email طريقة بسيطة لعرض جميع الرسائل.

```csharp
ImapMessageInfoCollection messages = client.ListMessages();
```

- `ListMessages()` يقوم باسترجاع البيانات الوصفية لجميع رسائل البريد الإلكتروني الموجودة في صندوق الوارد.
- ال `ImapMessageInfoCollection` يحتوي الكائن على تفاصيل مثل المرسل والموضوع والمعرفات الفريدة.


## الخطوة 3: جلب كل رسالة بريد إلكتروني

للوصول إلى المحتوى والمرفقات، يتعين عليك جلب كل بريد إلكتروني باستخدام معرفه الفريد.


```csharp
foreach (ImapMessageInfo messageInfo in messages)
{
    MailMessage message = client.FetchMessage(messageInfo.UniqueId);
}
```

- ال `foreach` تكرر الحلقة جميع الرسائل.
- `FetchMessage()` يقوم باسترجاع محتوى البريد الإلكتروني الفعلي لمعرف رسالة معين.


## الخطوة 4: تكرار المرفقات

الآن بعد أن حصلت على محتوى البريد الإلكتروني، حان الوقت لاستخراج المرفقات. كل `MailMessage` يحتوي الكائن على مجموعة من المرفقات.

```csharp
foreach (Attachment attachment in message.Attachments)
{
    Console.WriteLine($"Attachment Name: {attachment.Name}");
}
```

- ال `Attachments` تسرد الخاصية جميع المرفقات الموجودة في البريد الإلكتروني.
- يستخدم `attachment.Name` للحصول على اسم الملف.


## الخطوة 5: حفظ المرفقات على القرص

أخيرًا، احفظ المرفقات على جهازك المحلي. يمكنك تصفية الملفات حسب النوع أو الحجم أو معايير أخرى.

```csharp
foreach (Attachment attachment in message.Attachments)
{
    string filePath = Path.Combine("C:\\Attachments", attachment.Name);
    using (var stream = new FileStream(filePath, FileMode.Create))
    {
        attachment.Save(stream);
    }
}
```

- يستبدل `"C:\\Attachments"` مع مسار المجلد المطلوب.
- ال `attachment.Save()` الطريقة تكتب الملف على القرص.


## الخطوة 6: معالجة المرفقات حسب النوع

إذا كنت بحاجة إلى التعامل مع المرفقات بشكل مختلف استنادًا إلى نوعها (على سبيل المثال، PDF مقابل JPEG)، فإن Aspose.Email يجعل الأمر سهلاً.

```csharp
if (attachment.ContentType.MediaType == "application/pdf")
{
    Console.WriteLine("Processing PDF...");
}
else if (attachment.ContentType.MediaType == "image/jpeg")
{
    Console.WriteLine("Processing JPEG...");
}
```

- `ContentType.MediaType` يحدد نوع الملف (على سبيل المثال، `application/pdf` بالنسبة لملفات PDF، `image/jpeg` (للصور).
- أضف منطقًا مخصصًا لأنواع الملفات المختلفة حسب الحاجة.


## خاتمة

والآن! لم يعد استخراج المرفقات من رسائل البريد الإلكتروني مهمة شاقة. مع Aspose.Email لـ .NET، يمكنك أتمتة هذه العملية ببضعة أسطر برمجية فقط. من إعداد عميل IMAP إلى حفظ المرفقات محليًا، يغطي هذا الدليل كل ما تحتاجه للبدء. 

إذن لماذا الانتظار؟ [تنزيل Aspose.Email](https://releases.aspose.com/email/net/) وابدأ بتبسيط سير عمل البريد الإلكتروني الخاص بك اليوم!


## الأسئلة الشائعة

### هل يمكنني استخدام هذا الكود مع Gmail أو Outlook؟
نعم! استبدل `imap.example.com` مع Gmail (`imap.gmail.com`) أو Outlook (`outlook.office365.com`) عنوان خادم IMAP.

### هل استخدام Aspose.Email مجاني؟
يتطلب Aspose.Email ترخيصًا لاستخدام جميع الميزات. يمكنك طلب ترخيص [نسخة تجريبية مجانية](https://releases.aspose.com/) أو أ [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).

### كيف يمكنني التعامل مع أمان كلمة المرور؟
فكر في استخدام متغيرات البيئة أو تخزين بيانات الاعتماد بشكل آمن بدلاً من كلمات المرور المشفرة.

### هل يمكنني استخراج المرفقات من العناصر المرسلة؟
نعم، استخدم فقط `SelectFolder(ImapFolderInfo.Sent)` بدلا من صندوق الوارد.

### هل يدعم Aspose.Email بروتوكول POP3؟
بالتأكيد! بالإضافة إلى IMAP، يدعم أيضًا POP3 وSMTP.