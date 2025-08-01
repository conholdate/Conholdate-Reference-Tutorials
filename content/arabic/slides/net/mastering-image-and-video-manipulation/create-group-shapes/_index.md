---
"description": "تعرّف على كيفية إنشاء أشكال المجموعات وإدارتها باستخدام Aspose.Slides لـ .NET. يقدم هذا الدليل الشامل تعليمات واضحة خطوة بخطوة."
"linktitle": "إنشاء أشكال المجموعة في PowerPoint باستخدام Aspose.Slides لـ .NET"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء أشكال المجموعة في PowerPoint باستخدام Aspose.Slides لـ .NET"
"url": "/ar/slides/net/mastering-image-and-video-manipulation/create-group-shapes/"
"weight": 11
---

## مقدمة

إن تحسين المظهر العام لعروض PowerPoint التقديمية وتنظيمها يُؤثر بشكل كبير على تفاعل جمهورك. ومن الطرق الفعّالة لتحقيق ذلك استخدام أشكال المجموعات. في هذا البرنامج التعليمي، سنستكشف كيفية استخدام Aspose.Slides for .NET لإنشاء أشكال المجموعات وتعديلها في عروضك التقديمية.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:

- Aspose.Slides لـ .NET: قم بتنزيل أحدث إصدار من مكتبة Aspose.Slides وتثبيته من [موقع Aspose](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير متكاملة متوافقة مع .NET، مثل Visual Studio، للعمل على مشروعك.
- المعرفة الأساسية بلغة C#: تعرف على المفاهيم الأساسية للغة C#.


## استيراد مساحات الأسماء الضرورية

في مشروع C# الخاص بك، ابدأ بتضمين مساحات الأسماء التالية:

```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```

## الخطوة 1: إنشاء مثيل لفئة العرض التقديمي

إنشاء مثيل لـ `Presentation` الصف الذي ستعمل فيه على شرائحك. حدد المجلد الذي تُخزّن فيه مستنداتك:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // ستتم هنا خطوات إنشاء الأشكال والتلاعب بها
}
```

## الخطوة 2: الوصول إلى الشريحة الأولى

استرداد الشريحة الأولى من العرض التقديمي الذي قمت بإنشائه حديثًا:

```csharp
ISlide slide = pres.Slides[0];
```

## الخطوة 3: الوصول إلى مجموعة الأشكال

احصل على مجموعة الأشكال الموجودة على الشريحة:

```csharp
IShapeCollection slideShapes = slide.Shapes;
```

## الخطوة 4: إضافة شكل المجموعة

الآن حان الوقت لإضافة شكل المجموعة إلى الشريحة:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## الخطوة 5: إضافة الأشكال داخل المجموعة

يمكنك ملء شكل المجموعة بأشكال فردية، مثل المستطيلات:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100); // الشكل 1
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100); // الشكل 2
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100); // الشكل 3
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100); // الشكل 4
```

## الخطوة 6: تحديد الإطار لشكل المجموعة

يؤدي تعيين إطار لشكل المجموعة إلى منحها حدودًا محددة:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## الخطوة 7: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدّل في الدليل المحدد:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

## خاتمة

تهانينا! لقد نجحت في إنشاء أشكال المجموعات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. بتنظيم الأشكال بهذه الطريقة، يمكنك تحسين المظهر المرئي ووضوح المحتوى بشكل كبير، مما يجعل عروضك التقديمية أكثر تأثيرًا.

## الأسئلة الشائعة

### هل Aspose.Slides متوافق مع أحدث إصدار من .NET؟

نعم، يتم تحديث Aspose.Slides بانتظام للتوافق مع أحدث إصدارات .NET. تحقق من [التوثيق](https://reference.aspose.com/slides/net/) للحصول على أحدث تفاصيل التوافق.

### هل يمكنني تجربة Aspose.Slides قبل الشراء؟

بالتأكيد! يمكنك تنزيل نسخة تجريبية مجانية. [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم للاستعلامات المتعلقة بـ Aspose.Slides؟

قم بزيارة Aspose.Slides [المنتدى](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟

يمكنك طلب ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني شراء ترخيص كامل لـ Aspose.Slides؟

يمكنك شراء ترخيص من [صفحة الشراء](https://purchase.aspose.com/buy).