---
"description": "تعرّف على كيفية تحويل كل صفحة من مستند Word إلى صور PNG فردية بسهولة باستخدام Aspose.Words لـ .NET. يقدم هذا الدليل تعليمات خطوة بخطوة، بما في ذلك أمثلة برمجية."
"linktitle": "استدعاء حفظ الصفحة في مستندات Word"
"second_title": "واجهة برمجة تطبيقات معالجة المستندات Aspose.Words"
"title": "استدعاء حفظ الصفحة في مستندات Word"
"url": "/ar/words/net/guide-to-image-save-options/page-saving-callback-word-document/"
"weight": 10
---

## مقدمة

هل سبق لك أن احتجت إلى تحويل كل صفحة من مستند Word إلى صور منفصلة؟ سواء كنت ترغب في إنشاء صور مصغرة للمعاينة أو تقسيم تقرير طويل إلى صور مرئية سهلة الفهم، فإن Aspose.Words for .NET يجعل هذه المهمة بسيطة وفعالة. في هذا الدليل، سنشرح لك عملية إعداد استدعاء لحفظ الصفحات لحفظ كل صفحة من مستندك كصورة PNG. لنبدأ!

## المتطلبات الأساسية

قبل الغوص، تأكد من أن لديك ما يلي:

1. Aspose.Words for .NET: قم بتنزيله وتثبيته من [هنا](https://releases.aspose.com/words/net/).
2. Visual Studio: أي إصدار سيعمل، ولكننا سنستخدم Visual Studio 2019 لهذا الدليل.
3. المعرفة الأساسية بلغة C#: ستساعدك المعرفة بلغة C# على المتابعة بسلاسة.

## الخطوة 1: استيراد مساحات الأسماء الضرورية

أولاً، علينا استيراد مساحات الأسماء المطلوبة. هذا يسمح لنا بالوصول إلى الفئات والطرق اللازمة دون الحاجة إلى كتابة مساحة الأسماء كاملةً في كل مرة.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## الخطوة 2: تحديد دليل المستندات الخاص بك

بعد ذلك، حدد مسار مجلد المستندات. هذا هو المكان الذي يوجد فيه مستند Word المُدخل، وهو المكان الذي ستُحفظ فيه الصور الناتجة.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: تحميل المستند الخاص بك

الآن، لنحمّل المستند الذي تريد معالجته. تأكد من وجوده في المجلد المحدد، باسم "Rendering.docx".

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 4: تكوين خيارات حفظ الصورة

سنقوم بإعداد خيارات حفظ الصور، مع تحديد أننا نريد حفظ الصفحات كملفات PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

هنا، `PageSet` يحدد نطاق الصفحات التي سيتم حفظها، و `PageSavingCallback` يشير إلى فئة الاستدعاء المخصصة لدينا.

## الخطوة 5: تنفيذ استدعاء حفظ الصفحة

الآن، نحتاج إلى تنفيذ فئة الاستدعاء التي تتعامل مع كيفية حفظ كل صفحة.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

هذه الفئة تنفذ `IPageSavingCallback` الواجهة. في `PageSaving` الطريقة هي أننا نحدد نمط التسمية لكل صفحة محفوظة.

## الخطوة 6: حفظ المستند كصور

وأخيرًا، نحفظ المستند باستخدام الخيارات التي قمنا بتكوينها.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## خاتمة

تهانينا! لقد نجحتَ في إعداد استدعاء حفظ الصفحات لحفظ كل صفحة من مستند Word كصورة PNG منفصلة باستخدام Aspose.Words لـ .NET. هذه التقنية مفيدة للغاية لتطبيقات متنوعة، بدءًا من إنشاء معاينات الصفحات ووصولًا إلى إنشاء صور فردية للصفحات للتقارير.

## الأسئلة الشائعة

### هل يمكنني حفظ الصفحات بتنسيقات أخرى غير PNG؟
نعم! يمكنك حفظ الصفحات بتنسيقات مثل JPEG وBMP وTIFF عن طريق تغيير `SaveFormat` في `ImageSaveOptions`.

### كيف يمكنني حفظ صفحات محددة فقط؟
لحفظ صفحات معينة، قم بتعديل `PageSet` المعلمة في `ImageSaveOptions` لتضمين الصفحات المطلوبة فقط.

### هل من الممكن تخصيص جودة الصورة؟
بالتأكيد! يمكنك التحكم بجودة الصورة الناتجة عن طريق ضبط خصائص مثل `ImageSaveOptions.JpegQuality`.

### كيف يمكنني التعامل مع المستندات الكبيرة بكفاءة؟
بالنسبة للمستندات الكبيرة، فكر في معالجة الصفحات على دفعات لإدارة استخدام الذاكرة بشكل فعال.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Words لـ .NET؟
للحصول على أدلة وأمثلة شاملة، راجع [توثيق Aspose.Words](https://reference.aspose.com/words/net/).