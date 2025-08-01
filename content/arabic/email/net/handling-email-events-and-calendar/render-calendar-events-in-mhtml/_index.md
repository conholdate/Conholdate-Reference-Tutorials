---
"description": "حوّل أحداث التقويم إلى صيغة MHTML باستخدام Aspose.Email لـ .NET. تعلّم خطوة بخطوة كيفية تخصيص ملفات MSG وحفظها باستخدام C#."
"linktitle": "عرض أحداث التقويم في MHTML باستخدام Aspose.Email"
"second_title": "واجهة برمجة تطبيقات معالجة البريد الإلكتروني Aspose.Email .NET"
"title": "عرض أحداث التقويم في MHTML باستخدام Aspose.Email"
"url": "/ar/email/net/handling-email-events-and-calendar/render-calendar-events-in-mhtml/"
"weight": 15
---

## مقدمة

Aspose.Email لـ .NET مكتبة فعّالة لإدارة مهام البريد الإلكتروني في تطبيقات .NET. من أمثلة استخدامها الرائعة عرض أحداث التقويم برمجيًا باستخدام لغة C#. سواءً كنت تُنشئ ميزة تكامل التقويم أو تُنشئ مُشاهدات بريد إلكتروني مُخصصة، سيُرشدك هذا البرنامج التعليمي إلى كيفية عرض أحداث التقويم بتنسيق MHTML بدقة وتخصيص.

## المتطلبات الأساسية

قبل أن نبدأ، دعونا نتأكد من أن كل شيء جاهز لمتابعة هذا البرنامج التعليمي:

1. Aspose.Email لمكتبة .NET: قم بتنزيل أحدث إصدار من المكتبة من [صفحة تنزيل Aspose.Email لـ .NET](https://releases.aspose.com/email/net/).
2. بيئة التطوير: Visual Studio (أو بيئة التطوير المتكاملة C# المفضلة لديك) مثبتة على نظامك.
3. الترخيص: احصل على ترخيص ساري المفعول لـ Aspose.Email. لأغراض التقييم، يمكنك استخدام [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).
4. ملف MSG نموذجي: ملف MSG لأحداث التقويم. يمكنك استخدام أي `.msg` ملف يحتوي على أحداث التقويم، مثل "اجتماع مع حدوثات متكررة.msg".

## استيراد الحزم

للبدء، قم بتضمين المساحات الأساسية اللازمة في مشروعك. 

```csharp
using System;
using Aspose.Email;
using Aspose.Email.Mht;
```

الآن، دعونا ننتقل إلى الدليل خطوة بخطوة!

## الخطوة 1: تحميل ملف MSG لحدث التقويم

أولاً، نقوم بتحميل ملف MSG الذي يحتوي على حدث التقويم. هذه الخطوة أساسية لأنها تُعدّ المدخل لعرض الحدث بصيغة MHTML.


```csharp
string dataDir = "Your Data Directory";
string fileName = "Meeting with Recurring Occurrences.msg";

// تحميل ملف MSG
MailMessage msg = MailMessage.Load(dataDir + fileName);
```

- `dataDir`:يحدد الدليل الذي سيتم تخزين ملف MSG الخاص بك فيه.
- `fileName`: اسم ملف حدث التقويم.
- `MailMessage.Load`:يقرأ الملف ويحمله إلى `MailMessage` هدف.

## الخطوة 2: تكوين خيارات حفظ MHTML

بعد ذلك، نُهيئ خيارات عرض حدث التقويم بتنسيق MHTML. يتضمن ذلك تفعيل تنسيقات ورؤوس وخصائص أخرى مُحددة للتخصيص.

```csharp
MhtSaveOptions options = new MhtSaveOptions
{
    MhtFormatOptions = MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent
};
```

- `MhtSaveOptions`:يمثل الإعدادات لحفظ ملفات MHTML.
- `MhtFormatOptions`:يقوم بتكوين خيارات مثل تضمين الرؤوس وعرض أحداث التقويم.

## الخطوة 3: تخصيص قوالب العرض

هنا، نُحدد كيفية ظهور خصائص مُحددة، مثل وقت بدء الحدث، في المُخرَج. تُتيح هذه الخطوة مُخرَجًا قابلًا للتخصيص والقراءة بدرجة عالية.


```csharp
if (options.FormatTemplates.ContainsKey(MhtTemplateName.Start))
    options.FormatTemplates[MhtTemplateName.Start] = @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>";
else
    options.FormatTemplates.Add(MhtTemplateName.Start, @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

- `MhtTemplateName.Start`:يشير إلى خاصية "البدء" لحدث التقويم.
- `options.FormatTemplates`:تخصيص قالب العرض لخصائص محددة.

## الخطوة 4: حفظ حدث التقويم بصيغة MHTML

أخيرًا، احفظ حدث التقويم في ملف MHTML بالخيارات التي تم تكوينها.


```csharp
msg.Save(dataDir + "Meeting with Recurring Occurrences.mhtml", options);
```

- `msg.Save`:يحفظ الرسالة بالتنسيق والموقع المحددين.
- `Meeting with Recurring Occurrences.mhtml`: اسم ملف الإخراج.

## خاتمة

يُعد عرض أحداث التقويم باستخدام Aspose.Email لـ .NET فعالاً وقابلاً للتخصيص بدرجة كبيرة. باتباع الخطوات المذكورة أعلاه، يمكنك تحويل أحداث التقويم بسلاسة إلى ملف MHTML بتنسيق مُخصص.

## الأسئلة الشائعة

### ما هو MHTML؟
MHTML هو تنسيق ملف أرشيف ويب يحتوي على HTML والموارد ذات الصلة مثل الصور، مما يجعله مناسبًا لعرض ومشاركة أحداث التقويم.

### هل يمكنني تقديم الأحداث المتكررة؟
نعم! يدعم Aspose.Email عرض الأحداث المتكررة، مما يضمن التقاط جميع التفاصيل بدقة.

### هل هناك حاجة إلى ترخيص؟
نعم، يلزم الحصول على ترخيص ساري المفعول. يمكنك طلب [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) للتقييم.

### هل يمكنني إضافة خصائص مخصصة إلى المخرجات؟
بالتأكيد! يمكنك تخصيص قوالب لخصائص إضافية باستخدام `FormatTemplates` مجموعة.

### كيف يمكنني استكشاف المشكلات وإصلاحها؟
قم بزيارة [منتدى دعم البريد الإلكتروني Aspose.](https://forum.aspose.com/c/email/12/) للحصول على مساعدة الخبراء.