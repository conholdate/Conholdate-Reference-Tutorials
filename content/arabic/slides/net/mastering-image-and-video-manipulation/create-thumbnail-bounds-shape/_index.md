---
"description": "تعرّف على كيفية استخدام Aspose.Slides لـ .NET لإنشاء صور مصغّرة ذات حدود محددة للأشكال في عروض PowerPoint التقديمية. يقدم هذا الدليل الشامل تعليمات مفصلة خطوة بخطوة."
"linktitle": "إنشاء صورة مصغرة مع حدود للشكل في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء صورة مصغرة مع حدود للشكل في Aspose.Slides"
"url": "/ar/slides/net/mastering-image-and-video-manipulation/create-thumbnail-bounds-shape/"
"weight": 10
---

## مقدمة

إذا كنت مطور .NET وتبحث عن طريقة فعّالة لإنشاء صور مصغّرة مع حدود للأشكال في عروض PowerPoint التقديمية، فإن Aspose.Slides for .NET أداة ممتازة تستحق التجربة. تُبسّط هذه المكتبة القوية التعامل مع ملفات PowerPoint، مما يُمكّنك من استخراج البيانات القيّمة والعمل عليها بسلاسة. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء صورة مصغّرة مع حدود لشكل.

## المتطلبات الأساسية

قبل البدء، تأكد من أن لديك ما يلي:

1. Aspose.Slides لمكتبة .NET: قم بتنزيلها وتثبيتها من [موقع Aspose](https://releases.aspose.com/slides/net/).
2. مسار الملف: استبدال `"Your Documents Directory"` في الكود مع المسار الفعلي إلى مستنداتك.

## استيراد مساحات الأسماء الضرورية

للاستفادة من ميزات Aspose.Slides، ابدأ باستيراد المساحات المطلوبة في بداية مشروعك:

```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```

## الخطوة 1: إنشاء مثيل لفئة العرض التقديمي

أولاً، عليك تهيئة `Presentation` الفئة التي تمثل ملف PowerPoint الخاص بك:

```csharp
string dataDir = "Your Documents Directory\\";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // أصبح الآن كائن العرض التقديمي الخاص بك جاهزًا للتعامل معه.
}
```

باستخدام `using` يضمن البيان الموجود هنا إصدار الموارد بشكل مناسب بعد الانتهاء منها.

## الخطوة 2: إنشاء صورة مصغرة مع حدود الشكل

بعد ذلك، ستقوم بإنشاء صورة مصغرة لشكل في العرض التقديمي الخاص بك مع الحدود المحددة:

```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // تحتوي الخريطة النقطية الآن على الصورة المصغرة ضمن الحدود المحددة.
}
```

في هذه المقتطفة، `ShapeThumbnailBounds.Appearance` يُحدد أنك تريد حدود مظهر الشكل. اضبط معلمات العرض والارتفاع (1، 1) حسب الحاجة بناءً على متطلبات الإخراج.

## الخطوة 3: حفظ الصورة المصغرة على القرص

أخيرًا، احفظ الصورة المصغرة الناتجة بالتنسيق المفضل، مثل PNG:

```csharp
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```

هنا، يمكنك تخصيص اسم الملف وتنسيقه وفقًا لاحتياجات مشروعك.

تهانينا! لقد نجحت في إنشاء صورة مصغّرة بحدود لشكل باستخدام Aspose.Slides لـ .NET. هذه العملية بسيطة وسهلة الدمج في تطبيقات .NET.

## خاتمة

يُسهّل Aspose.Slides for .NET عملية إنشاء وإدارة عروض PowerPoint التقديمية، مُزوّدًا المطورين بأدوات فعّالة لإنشاء الصور المصغّرة وغيرها. باتباع هذا الدليل، ستتعلّم الخطوات الأساسية لاستخدام هذه المكتبة بكفاءة في مشاريعك.

## الأسئلة الشائعة

### هل Aspose.Slides متوافق مع أحدث إطار عمل .NET؟

نعم، يتم تحديث Aspose.Slides بشكل متكرر لدعم أحدث إصدارات إطار عمل .NET.

### هل يمكنني استخدام Aspose.Slides للمشاريع التجارية؟

بالتأكيد! يوفر Aspose.Slides خيارات ترخيص متنوعة تناسب الاستخدام الفردي والتجاري. تحقق [هنا](https://purchase.aspose.com/buy) لمزيد من المعلومات.

### هل هناك نسخة تجريبية مجانية متاحة؟

نعم! يمكنك استكشاف ميزات Aspose.Slides من خلال تجربة مجانية متاحة. [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟

للحصول على المساعدة، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للتواصل مع المجتمع والمطورين ذوي الخبرة.

### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟

نعم يمكن الحصول على تراخيص مؤقتة للمشاريع قصيرة الأجل [هنا](https://purchase.aspose.com/temporary-license/).