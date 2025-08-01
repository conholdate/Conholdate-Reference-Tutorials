---
"description": "اكتشف كيفية استخراج ملفات الفيديو المضمنة بسهولة من عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. يغطي هذا الدليل الشامل خطوة بخطوة كل شيء، بدءًا من إعداد بيئة العمل وحتى حفظ مقاطع الفيديو المستخرجة."
"linktitle": "استخراج مقاطع الفيديو من شرائح PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "استخراج مقاطع الفيديو من شرائح PowerPoint باستخدام Aspose.Slides"
"url": "/ar/slides/net/extract-audio-and-video/extract-videos-from-powerpoint-slides/"
"weight": 14
---

## مقدمة

Aspose.Slides for .NET هي مكتبة فعّالة تُمكّن المطورين من التفاعل برمجيًا مع عروض PowerPoint التقديمية. في هذا الدليل، سنشرح لك عملية استخراج مقاطع الفيديو المُضمّنة في شرائح PowerPoint باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Aspose.Slides لـ .NET: الحصول على المكتبة وتثبيتها من [موقع Aspose](https://purchase.aspose.com/buy).
- عرض تقديمي على PowerPoint: قم بإعداد ملف PowerPoint (على سبيل المثال، `Video.pptx`) مع الفيديو الذي ترغب في استخراجه.

## المساحات الاسمية الضرورية

للعمل مع Aspose.Slides لـ .NET، عليك استيراد مساحات الأسماء المناسبة. أدرج ما يلي في الكود الخاص بك:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

## الخطوة 1: تحديد دليل المستندات

أولاً، قم بتحديد المسار إلى عرض PowerPoint الخاص بك:

```csharp
string dataDir = "Your Document Directory";
```

يستبدل `"Your Document Directory"` مع المسار الفعلي إلى الدليل الذي يحتوي على ملف PowerPoint الخاص بك.

## الخطوة 2: تحميل العرض التقديمي

قم بتحميل عرض PowerPoint في `Presentation` هدف:

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

يؤدي هذا إلى تهيئة `Presentation` الكائن باستخدام ملف PowerPoint المحدد.

## الخطوة 3: التكرار عبر الشرائح والأشكال

بعد ذلك، قم بالمرور على كل شريحة في العرض التقديمي وتحقق من إطارات الفيديو:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in slide.Shapes)
    {
        if (shape is VideoFrame videoFrame)
        {
            // انتقل إلى استخراج الفيديو
        }
    }
}
```

## الخطوة 4: استخراج بيانات الفيديو

بمجرد العثور على إطار فيديو، استخرج خصائصه وبياناته الثنائية:

```csharp
IVideoFrame vf = (IVideoFrame)shape;  // تخزين الشكل كإطار فيديو
string contentType = vf.EmbeddedVideo.ContentType;
Byte[] buffer = vf.EmbeddedVideo.BinaryData;

// احصل على امتداد الملف
string fileExtension = contentType.Substring(contentType.LastIndexOf('/') + 1);
```

## الخطوة 5: حفظ الفيديو

وأخيرًا، اكتب بيانات الفيديو المستخرجة إلى ملف:

```csharp
using (FileStream stream = new FileStream(dataDir + "ExtractedVideo." + fileExtension, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

يقوم هذا الكود بإنشاء ملف جديد في الدليل المحدد ويكتب بيانات الفيديو فيه.

## خاتمة

مع Aspose.Slides لـ .NET، يُعد استخراج مقاطع الفيديو من شرائح PowerPoint عملية سهلة وبسيطة. باتباع هذا الدليل، يمكنك بسهولة إدارة محتوى الوسائط المتعددة داخل تطبيقات .NET، مما يُثري تجربة المستخدم ووظائفها.

## الأسئلة الشائعة

### ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة مصممة للعمل مع عروض PowerPoint، مما يسمح للمستخدمين بإنشاء ملفات العروض التقديمية وتحريرها ومعالجتها برمجيًا.

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
يمكنك الوصول إلى الوثائق الكاملة [هنا](https://reference.aspose.com/slides/net/).

### هل يتوفر Aspose.Slides لـ .NET للتجربة المجانية؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هذا الرابط](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
يمكن تقديم طلبات الحصول على تراخيص مؤقتة [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
الدعم متاح من خلال [منتدى Aspose.Slides](https://forum.aspose.com/).