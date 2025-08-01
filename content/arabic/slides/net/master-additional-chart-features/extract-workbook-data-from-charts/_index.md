---
"description": "أطلق العنان لإمكانيات عروض PowerPoint التقديمية بتعلم كيفية استرداد بيانات المصنفات من المخططات باستخدام Aspose.Slides لـ .NET. يرشدك هذا البرنامج التعليمي خطوة بخطوة خلال العملية، مما يُسهّل استخراج بيانات المخططات واستخدامها بفعالية."
"linktitle": "استخراج بيانات المصنف من المخططات باستخدام Aspose.Slides لـ .NET"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "استخراج بيانات المصنف من المخططات باستخدام Aspose.Slides لـ .NET"
"url": "/ar/slides/net/master-additional-chart-features/extract-workbook-data-from-charts/"
"weight": 12
---

## مقدمة

قد يكون العمل مع عروض PowerPoint التقديمية أمرًا صعبًا، خاصةً عند استخراج بيانات قيّمة من مخططات مُضمّنة. لحسن الحظ، يُوفّر Aspose.Slides for .NET حلاً فعّالاً يُبسّط هذه العملية. في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية استرداد مصنف من مخطط ضمن عرض تقديمي في PowerPoint.

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، تأكد من أن لديك ما يلي جاهزًا:

### Aspose.Slides لـ .NET

يجب تثبيت Aspose.Slides for .NET في بيئة التطوير لديك. إذا لم تقم بذلك بعد، يمكنك تنزيله من الموقع الإلكتروني:

[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/)

### عرض تقديمي على PowerPoint

احتفظ بملف عرض PowerPoint الخاص بك في متناول يدك، وخاصةً الملف الذي يحتوي على مخطط بالبيانات المرتبطة التي ترغب في استردادها.

## الخطوة 1: استيراد مساحات الأسماء الضرورية

للعمل بشكل فعال مع Aspose.Slides، ستحتاج أولاً إلى استيراد المساحات المطلوبة:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## الخطوة 2: تحديد دليل المستندات

حدد الدليل الذي يوجد به ملف العرض التقديمي الخاص بك:

```csharp
string dataDir = "Your Document Directory"; // ضبط هذا المسار حسب الحاجة
```

## الخطوة 3: تحميل العرض التقديمي

يمكنك تحميل عرض PowerPoint التقديمي مع تفعيل استرداد المصنف من ذاكرة التخزين المؤقت للمخطط. إليك كيفية القيام بذلك:

```csharp
string pptxFile = Path.Combine(dataDir, "YourPresentation.pptx");
string outPptxFile = Path.Combine(RunExamples.OutPath, "RecoveredWorkbook.pptx");

LoadOptions lo = new LoadOptions();
lo.SpreadsheetOptions.RecoverWorkbookFromChartCache = true;

using (Presentation pres = new Presentation(pptxFile, lo))
{
    // الوصول إلى بيانات الرسم البياني والعمل عليها
    // سيتم وضع الكود الخاص بك هنا
    pres.Save(outPptxFile, SaveFormat.Pptx);
}
```

في هذه الخطوة، `LoadOptions` يسمح لك الكائن بتمكين استرداد المصنف باستخدام `RecoverWorkbookFromChartCache` ملكية.

## الخطوة 4: استرداد الرسم البياني والوصول إلى المصنف الخاص به

الآن حان الوقت للبحث في الرسم البياني واسترجاع البيانات المرتبطة به:

```csharp
IChart chart = pres.Slides[0].Shapes[0] as IChart; // ضبط المؤشر حسب الحاجة
IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;

// الآن يمكنك العمل مع بيانات المصنف حسب متطلباتك
```

من خلال الوصول إلى الشكل الأول للشريحة الأولى (والذي من المتوقع أن يكون مخططًا)، يمكنك الحصول على مصنف بيانات المخطط ويمكنك معالجة البيانات أو استخراجها حسب الحاجة.

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية استرداد مصنف من مخطط في عرض تقديمي على PowerPoint بفعالية باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة استخراج بيانات المخطط واستخدامها لتلبية احتياجاتك التحليلية.

## الأسئلة الشائعة

### ما هو Aspose.Slides لـ .NET؟

Aspose.Slides for .NET هي مكتبة قوية تتيح للمطورين إنشاء عروض تقديمية لبرنامج Microsoft PowerPoint ومعالجتها وتحويلها برمجيًا.

### هل يمكنني تجربة Aspose.Slides لـ .NET قبل الشراء؟

نعم! تقدم Aspose نسخة تجريبية مجانية من Aspose.Slides لـ .NET. يمكنك تقييم إمكانياتها قبل الشراء. [احصل على النسخة التجريبية المجانية هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟

يمكنك الوصول إلى وثائق شاملة لـ Aspose.Slides لـ .NET [هنا](https://reference.aspose.com/slides/net/)، والذي يتضمن أمثلة ومراجع API.

### كيف يمكنني شراء ترخيص لـ Aspose.Slides لـ .NET؟

لشراء الترخيص، قم بزيارة موقع Aspose واستخدم الرابط التالي: [شراء Aspose.Slides لـ .NET](https://purchase.aspose.com/buy).