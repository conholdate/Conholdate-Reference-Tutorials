---
"description": "أطلق العنان لإمكانيات عروضك التقديمية بتعلم كيفية تضمين مقاطع الفيديو باستخدام Aspose.Slides لـ .NET. يرشدك هذا البرنامج التعليمي الشامل خطوة بخطوة خلال عملية دمج عناصر الوسائط المتعددة."
"linktitle": "إضافة إطار فيديو مضمن في عروض .NET التقديمية"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إضافة إطار فيديو مضمن في عروض .NET التقديمية"
"url": "/ar/slides/net/mastering-image-and-video-manipulation/add-embedded-videos-frame/"
"weight": 19
---

## مقدمة

في ظلّ وتيرة العروض التقديمية السريعة اليوم، يُمكن لدمج عناصر الوسائط المتعددة أن يُعزز التفاعل والاحتفاظ بالجمهور بشكل ملحوظ. يُقدّم Aspose.Slides for .NET حلاًّ فعّالاً لتضمين إطارات الفيديو في شرائحك. سيُرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، لضمان تجربة سلسة من البداية إلى النهاية.

## المتطلبات الأساسية

قبل البدء، تأكد من أن لديك ما يلي:

- Aspose.Slides لمكتبة .NET: قم بتنزيل المكتبة وتثبيتها من [صفحة الإصدار](https://releases.aspose.com/slides/net/).
- المحتوى الإعلامي: ملف فيديو (على سبيل المثال، "Wildlife.mp4") الذي تريد تضمينه في العرض التقديمي الخاص بك.

## استيراد مساحات الأسماء الضرورية

ابدأ باستيراد المساحات المطلوبة في مشروع .NET الخاص بك:

```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```

## الخطوة 1: إعداد الدلائل الخاصة بك

تأكد من أن مشروعك يتضمن الدلائل اللازمة للمستندات وملفات الوسائط:

```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");

// إنشاء الدليل إذا لم يكن موجودًا
if (!Directory.Exists(dataDir))
    Directory.CreateDirectory(dataDir);
```

## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي

إنشاء مثيل لـ `Presentation` الفئة التي تمثل ملف PPTX الخاص بك:

```csharp
using (Presentation pres = new Presentation())
{
    // احصل على الشريحة الأولى
    ISlide sld = pres.Slides[0];
```

## الخطوة 3: تضمين الفيديو

قم بتضمين الفيديو في العرض التقديمي الخاص بك باستخدام الكود التالي:

```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(Path.Combine(videoDir, "Wildlife.mp4"), FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```

## الخطوة 4: إضافة إطار فيديو

بعد ذلك، أضف إطار فيديو إلى الشريحة:

```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```

## الخطوة 5: تكوين خصائص الفيديو

ضبط خصائص الفيديو، بما في ذلك وضع التشغيل ومستوى الصوت:

```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto; // تشغيل الفيديو تلقائيًا
vf.Volume = AudioVolumeMode.Loud; // ضبط مستوى الصوت
```

## الخطوة 6: احفظ العرض التقديمي الخاص بك

وأخيرًا، احفظ ملف PPTX المعدّل على القرص:

```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```

يمكنك تكرار هذه الخطوات لكل مقطع فيديو ترغب في تضمينه في العرض التقديمي الخاص بك.

## خاتمة

تهانينا! لقد نجحت في تضمين إطار فيديو في عرضك التقديمي باستخدام Aspose.Slides لـ .NET. هذه الميزة الديناميكية ترتقي بعروضك التقديمية إلى مستوى جديد، وتأسر جمهورك بوسائل الإعلام المتعددة المدمجة بسلاسة.

## الأسئلة الشائعة

### هل يمكنني تضمين مقاطع فيديو في أي شريحة من العرض التقديمي؟

نعم، يمكنك تحديد أي شريحة عن طريق ضبط الفهرس في `pres.Slides[index]`.

### ما هي صيغ الفيديو المدعومة؟

يدعم Aspose.Slides تنسيقات الفيديو المختلفة، بما في ذلك MP4، وAVI، وWMV.

### هل يمكنني تخصيص حجم وموضع إطار الفيديو؟

بالتأكيد! يمكنك تعديل المعلمات في `AddVideoFrame(x, y, width, height, video)` لتناسب احتياجاتك.

### هل هناك حد لعدد مقاطع الفيديو التي يمكنني تضمينها؟

يعتمد الحد الأقصى لمقاطع الفيديو المضمنة عادةً على سعة برنامج العرض التقديمي لديك.

### أين يمكنني الحصول على مزيد من المساعدة أو مشاركة تجربتي؟

لا تتردد في زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.