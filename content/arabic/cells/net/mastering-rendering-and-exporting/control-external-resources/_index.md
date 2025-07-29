---
"description": "أطلق العنان لإمكانات تحويل ملفات Excel إلى PDF مع Aspose.Cells لـ .NET. في هذا الدليل الشامل، تعلّم كيفية إدارة الموارد الخارجية، مثل الصور، لضمان توافق ملفات PDF مع متطلبات التنسيق المطلوبة."
"linktitle": "التحكم في الموارد الخارجية باستخدام Aspose.Cells لـ .NET"
"second_title": "واجهة برمجة تطبيقات معالجة Excel لـ Aspose.Cells .NET"
"title": "التحكم في الموارد الخارجية باستخدام Aspose.Cells لـ .NET"
"url": "/ar/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## مقدمة

في عالمنا الرقمي اليوم، يُعد تحويل جداول بيانات Excel إلى مستندات PDF أمرًا شائعًا وضروريًا. سواء كنت تُعدّ تقارير أو بيانات مالية أو مواد عروض تقديمية، فإن ضمان توافق ملفات PDF مع التنسيق المطلوب أمر بالغ الأهمية. يوفر Aspose.Cells for .NET مكتبة فعّالة تُمكّنك من التحكم في عملية التحويل هذه بدقة، خاصةً عند التعامل مع موارد خارجية مثل الصور. في هذا الدليل، سنستكشف كيفية إدارة الموارد الخارجية بفعالية أثناء عملية تحويل Excel إلى PDF باستخدام Aspose.Cells. هيا بنا!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي جاهزًا:

1. Visual Studio أو أي بيئة تطوير متكاملة متوافقة مع .NET: ستكون هذه بيئة التطوير الخاصة بك.
2. Aspose.Cells لـ .NET: إذا لم تقم بتثبيته بعد، قم بزيارة [تنزيلات Aspose](https://releases.aspose.com/cells/net/) الصفحة للحصول على الإصدار الأحدث.
3. المعرفة الأساسية بلغة C#: الإلمام بلغة C# مفيد. إذا كنت بحاجة إلى توضيح لأي مفاهيم، فلا تتردد في البحث عنها.
4. ملف Excel نموذجي: قم بإعداد ملف Excel، مثل "samplePdfSaveOptions_StreamProvider.xlsx"، والذي يحتوي على الموارد الخارجية التي ترغب في تحويلها.
5. ملف الصورة للاختبار: استخدم ملف صورة مثل "newPdfSaveOptions_StreamProvider.png" كمورد خارجي أثناء التحويل.

## استيراد الحزم الضرورية

للبدء، ستحتاج إلى استيراد مساحات الأسماء المطلوبة من مكتبة Aspose.Cells. أضف التعليمات التالية في أعلى ملف C#:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

توفر هذه المساحات الأسماء الفئات والطرق الأساسية لمهامك.

## الخطوة 1: إنشاء فئة موفر التدفق

أولاً، قم بإنشاء فئة موفر التدفق التي تنفذ `IStreamProvider` ستتيح لك هذه الفئة التحكم في كيفية تحميل الموارد الخارجية.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // تحميل الصورة في مجرى الذاكرة
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: يتم استدعاء هذه الطريقة عند إغلاق الدفق، وتسجيل رسالة تصحيح حاليًا.
- InitStream: تقوم هذه الطريقة بقراءة ملف الصورة الخارجي كمصفوفة بايت، وتحويله إلى مجرى ذاكرة، وتعيينه إلى `options.Stream` ملكية.

## الخطوة 2: إعداد أدلة المصدر والإخراج

بعد ذلك، قم بتحديد الدلائل لملف Excel الخاص بك وملف PDF الناتج.

```csharp
// دليل المصدر
string sourceDir = "Your Document Directory";
// دليل الإخراج
string outputDir = "Your Document Directory";
```

يستبدل `"Your Document Directory"` مع المسار الفعلي على نظامك حيث توجد ملفاتك.

## الخطوة 3: تحميل ملف Excel الخاص بك

الآن قم بتحميل ملف Excel الذي تريد إنشاء ملف PDF منه.

```csharp
// قم بتحميل ملف Excel المصدر الذي يحتوي على صور خارجية
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

ال `Workbook` تمثل الفئة من Aspose.Cells ملف Excel الخاص بك، والذي قد يتضمن موارد خارجية مختلفة مثل الصور.

## الخطوة 4: تعيين خيارات حفظ PDF

قبل حفظ المصنف بتنسيق PDF، حدد خيارات الحفظ المطلوبة.

```csharp
// تحديد خيارات حفظ PDF - موفر البث
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // احفظ كل ورقة في صفحة جديدة
};
```

يؤدي هذا إلى إنشاء مثيل لـ `PdfSaveOptions`، مما يسمح لك بتخصيص تنسيق PDF. `OnePagePerSheet` يضمن الخيار ظهور كل ورقة Excel على صفحة منفصلة في ملف PDF النهائي.

## الخطوة 5: تعيين موفر البث الخاص بك

قم بتوصيل جهازك `Workbook` مثال مع `MyStreamProvider` الصف الذي قمت بإنشائه سابقًا.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

يضمن هذا الخط أنه في كل مرة يتم فيها مواجهة موارد خارجية أثناء التحويل، فسوف يقوم موفر الخدمة المخصص الخاص بك بإدارتها وفقًا لذلك.

## الخطوة 6: حفظ المصنف بتنسيق PDF

الآن، قم بحفظ مصنف Excel الخاص بك بتنسيق PDF.

```csharp
// حفظ المصنف بصيغة PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

عن طريق الاتصال `Save` من خلال تطبيق الطريقة على كائن المصنف وتمرير دليل الإخراج مع خيارات PDF، يمكنك تحويل ملف Excel إلى ملف PDF منسق بشكل جيد.

## الخطوة 7: تأكيد التنفيذ الناجح

وأخيرًا، من الجيد التأكد من اكتمال العملية بنجاح.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

ستُعلمك هذه الرسالة بحالة عمليتك، وتزودك بتعليقات مفيدة.

## خاتمة

لقد أتقنتَ الآن عملية التحكم في الموارد الخارجية أثناء تحويل ملفات Excel إلى PDF باستخدام Aspose.Cells! باتباع هذه الخطوات، يمكنك ضمان تضمين الصور والعناصر الخارجية الأخرى بدقة في مستنداتك، مما ينتج عنه منتج نهائي مُحسّن في كل مرة.

## الأسئلة الشائعة

### ما هو Aspose.Cells؟
Aspose.Cells هي مكتبة قوية لمطوري .NET تتيح إنشاء ملفات Excel ومعالجتها وتحويلها وعرضها بتنسيقات مختلفة.

### كيف يمكنني تنزيل Aspose.Cells؟
يمكنك تنزيل الإصدار الأحدث من [رابط التحميل](https://releases.aspose.com/cells/net/).

### هل يمكنني تجربة Aspose.Cells مجانًا؟
نعم! يمكنك الوصول إلى نسخة تجريبية مجانية بزيارة [صفحة التجربة المجانية](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم لـ Aspose.Cells؟
للاستفسارات المتعلقة بالدعم، قم بزيارة [منتدى دعم Aspose](https://forum.aspose.com/c/cells/9).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Cells؟
يمكنك التقدم بطلب للحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).