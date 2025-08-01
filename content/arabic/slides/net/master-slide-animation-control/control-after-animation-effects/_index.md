---
"description": "أطلق العنان لإمكانات عروضك التقديمية بإتقان تأثيرات الرسوم المتحركة اللاحقة باستخدام Aspose.Slides لـ .NET. يوفر لك هذا الدليل المفصل الأساسيات اللازمة."
"linktitle": "إتقان تأثيرات After-Animation باستخدام Aspose.Slides لـ .NET"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان تأثيرات After-Animation باستخدام Aspose.Slides لـ .NET"
"url": "/ar/slides/net/master-slide-animation-control/control-after-animation-effects/"
"weight": 11
---

## مقدمة

تُحسّن الرسوم المتحركة الديناميكية عروضك التقديمية بشكل ملحوظ، مما يجعلها أكثر جاذبية وجاذبية بصرية. مع Aspose.Slides لـ .NET، يمكنك بسهولة التحكم في تأثيرات الرسوم المتحركة اللاحقة، مما يتيح لك إنشاء تجارب تفاعلية لجمهورك. سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال عملية معالجة هذه التأثيرات في شرائحك.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية ببرمجة C# و.NET.
- تم تثبيت مكتبة Aspose.Slides لـ .NET. نزّلها. [هنا](https://releases.aspose.com/slides/net/).
- بيئة تطوير متكاملة (IDE) مثل Visual Studio.

## استيراد مساحات الأسماء

للوصول إلى وظائف Aspose.Slides الضرورية، قم بتضمين المساحات التالية في الكود الخاص بك:

```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```

## الخطوة 1: إعداد دليل المستندات

ابدأ بالتأكد من وجود دليل مستنداتك. إن لم يكن موجودًا، فأنشئه:

```csharp
string dataDir = "Your Document Directory";
if (!Directory.Exists(dataDir))
    Directory.CreateDirectory(dataDir);
```

## الخطوة 2: تحديد مسار ملف الإخراج

حدد مسار ملف الإخراج للعرض التقديمي المعدل الخاص بك:

```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```

## الخطوة 3: تحميل العرض التقديمي

قم بتحميل العرض التقديمي الحالي الخاص بك باستخدام `Presentation` فصل:

```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```

## الخطوة 4: تعديل تأثيرات الرسوم المتحركة على الشريحة 1

استنسخ الشريحة الأولى واضبط تأثير الرسوم المتحركة اللاحقة على "إخفاء عند النقر التالي بالماوس":

```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```

## الخطوة 5: تعديل تأثيرات الرسوم المتحركة على الشريحة 2

استنسخ الشريحة الأولى مرة أخرى، وقم بتغيير تأثير الرسوم المتحركة اللاحقة إلى "لون" بصبغة خضراء:

```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```

## الخطوة 6: تعديل تأثيرات الرسوم المتحركة على الشريحة 3

بالنسبة للشريحة الثالثة، اضبط تأثير ما بعد الرسوم المتحركة على "إخفاء بعد الرسوم المتحركة":

```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```

## الخطوة 7: حفظ العرض التقديمي المعدّل

وأخيرًا، احفظ العرض التقديمي المعدّل:

```csharp
pres.Save(outPath, SaveFormat.Pptx);
```

## خاتمة

تهانينا! لقد نجحت في تعلم كيفية التحكم بتأثيرات ما بعد الرسوم المتحركة على الشرائح باستخدام Aspose.Slides لـ .NET. لا تتردد في تجربة تأثيرات مختلفة لإنشاء عروض تقديمية ديناميكية وجذابة تجذب جمهورك.

## الأسئلة الشائعة

### هل يمكنني تطبيق تأثيرات مختلفة بعد الرسوم المتحركة على عناصر فردية ضمن شريحة؟

نعم، يمكنك تخصيص تأثيرات ما بعد الرسوم المتحركة للعناصر الفردية عن طريق تكرارها وضبط خصائصها وفقًا لذلك.

### هل Aspose.Slides متوافق مع أحدث إصدارات .NET؟

بالتأكيد! يتم تحديث Aspose.Slides بانتظام لضمان توافقه مع أحدث إصدارات .NET Framework.

### كيف يمكنني إضافة رسوم متحركة مخصصة إلى الشرائح باستخدام Aspose.Slides؟

للحصول على معلومات مفصلة حول إضافة الرسوم المتحركة المخصصة، راجع [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/).

### ما هي تنسيقات الملفات التي يدعمها Aspose.Slides لحفظ العروض التقديمية؟

يدعم Aspose.Slides تنسيقات متنوعة، بما في ذلك PPTX وPPT وPDF وغيرها. راجع الوثائق للاطلاع على القائمة الكاملة.

### أين يمكنني الحصول على الدعم أو طرح الأسئلة المتعلقة بـ Aspose.Slides؟

للحصول على الدعم والتفاعل المجتمعي، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).