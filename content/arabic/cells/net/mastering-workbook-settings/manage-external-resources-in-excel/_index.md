---
"description": "اكتشف كيفية التحكم بسلاسة في الموارد الخارجية في مصنفات Excel باستخدام Aspose.Cells لـ .NET. يرشدك هذا الدليل الشامل خلال كل خطوة، بدءًا من تنفيذ موفر تدفق مخصص ووصولًا إلى عرض أوراق العمل."
"linktitle": "إدارة الموارد الخارجية في Excel باستخدام Aspose.Cells لـ .NET"
"second_title": "واجهة برمجة تطبيقات معالجة Excel لـ Aspose.Cells .NET"
"title": "إدارة الموارد الخارجية في Excel باستخدام Aspose.Cells لـ .NET"
"url": "/ar/cells/net/mastering-workbook-settings/manage-external-resources-in-excel/"
"weight": 10
---

## مقدمة

عند العمل مع البيانات في Excel، تُحسّن إدارة الموارد الخارجية بسلاسة وظائف تطبيقك بشكل ملحوظ. إذا كنت ترغب في التحكم في الصور والعناصر الخارجية الأخرى في مصنفات Excel باستخدام Aspose.Cells لـ .NET، فأنت في المكان المناسب! سيشرح لك هذا الدليل العملية خطوة بخطوة، مما يُمكّنك من تطبيق حل مُخصص للتعامل مع هذه الموارد بسهولة.

## المتطلبات الأساسية

قبل أن نتعمق في جوانب الترميز، تأكد من إعداد ما يلي:

1. Visual Studio: بيئة تطوير متكاملة لكتابة واختبار تطبيقات .NET. يُنصح باستخدام Visual Studio لدعمه الشامل وواجهته سهلة الاستخدام.
2. Aspose.Cells لـ .NET: قم بتنزيل المكتبة من [صفحة إصدار Aspose Cells](https://releases.aspose.com/cells/net/).
3. المعرفة الأساسية بلغة C#: ستساعدك المعرفة بمفاهيم C# و.NET على فهم التنفيذ بشكل أفضل.
4. إعداد مشروعك: تأكد من أن مشروعك يشير إلى مكتبة Aspose.Cells، والتي يمكنك إضافتها عبر NuGet Package Manager في Visual Studio.
5. ملفات العينة: قم بإعداد ملف Excel نموذجي يحتوي على موارد خارجية (على سبيل المثال، صور مرتبطة) لأغراض العرض التوضيحي.

بمجرد توفر كل هذه المتطلبات الأساسية لديك، فلنبدأ في إدارة الموارد الخارجية باستخدام Aspose.Cells.

## استيراد الحزم
لبدء البرمجة، ستحتاج إلى استيراد الحزم اللازمة في ملف C#. إليك ما تحتاجه:
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using Aspose.Cells.Rendering;
using System.Drawing.Imaging;
```

## الخطوة 1: تحديد الدلائل

أولاً، حدد الدليل المصدر والدليل الناتج حيث يتم تخزين ملفاتك والمكان الذي تريد حفظ ملفات الإخراج فيه.

```csharp
// تحديد دليل المصدر
static string sourceDir = @"C:\Path\To\Your\Documents\"; // تخصيص المسار
// تحديد دليل الإخراج
static string outputDir = @"C:\Path\To\Your\Output\";
```

تأكد من استبدال المسارات بالدلائل الفعلية على جهازك.

### الخطوة 2: تنفيذ واجهة IStreamProvider

بعد ذلك، قم بإنشاء فئة مخصصة لتنفيذ `IStreamProvider` ستتولى هذه الفئة إدارة كيفية الوصول إلى الموارد الخارجية مثل الصور.

```csharp
class CustomStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        // تنظيف الموارد إذا لزم الأمر
        options.Stream?.Close();
    }

    public void InitStream(StreamProviderOptions options)
    {
        // فتح مجرى الملف للمورد الخارجي
        options.Stream = new FileStream(Path.Combine(sourceDir, "image.png"), FileMode.Open, FileAccess.Read);
    }
}
```

في `InitStream` الطريقة هي أننا نفتح الملف الذي يعمل كمورد خارجي لك ونقوم بتعيينه إلى `Stream` ملكية.

### الخطوة 3: تحميل ملف Excel

الآن، دعنا نحمل مصنف Excel الذي يتضمن المورد الخارجي.

```csharp
public static void Execute()
{
    // تحميل ملف Excel
    Workbook workbook = new Workbook(Path.Combine(sourceDir, "sample.xlsx"));
    
    // تعيين موفر البث المخصص
    workbook.Settings.StreamProvider = new CustomStreamProvider();
```

يقوم هذا المقطع بتحميل ملف Excel الخاص بك ويقوم بتعيين موفر البث المخصص للتعامل مع الموارد الخارجية.

### الخطوة 4: الوصول إلى ورقة العمل

بعد تحميل المصنف، يمكنك الوصول إلى ورقة العمل المطلوبة بسهولة.

```csharp
    // الوصول إلى ورقة العمل الأولى
    Worksheet worksheet = workbook.Worksheets[0];
```

يمكنك الوصول إلى أي ورقة عمل عن طريق تحديد الفهرس الخاص بها.

### الخطوة 5: تكوين خيارات الصورة والطباعة

قم بتحديد الشكل الذي تريد أن تبدو عليه الصورة الناتجة عن طريق تكوين خيارات الصورة أو الطباعة.

```csharp
    // تحديد خيارات الصورة أو الطباعة
    ImageOrPrintOptions options = new ImageOrPrintOptions
    {
        OnePagePerSheet = true,
        ImageType = Drawing.ImageType.Png
    };
```

يضمن اختيار PNG الحصول على إخراج واضح ونقي.

### الخطوة 6: تحويل ورقة العمل إلى صورة

الآن يأتي الجزء المثير - تحويل ورقة العمل إلى ملف صورة!

```csharp
    // إنشاء عرض تقديمي للورقة وتحويل ورقة العمل إلى صورة
    SheetRender sheetRender = new SheetRender(worksheet, options);
    sheetRender.ToImage(0, Path.Combine(outputDir, "output.png"));
    
    Console.WriteLine("Excel sheet rendered successfully to an image!");
}
```

يقوم هذا الكود بتحويل ورقة العمل بأكملها إلى صورة PNG، والتي سيتم حفظها في دليل الإخراج المحدد.

## خاتمة

تهانينا! لقد تعلمت الآن كيفية التحكم بالموارد الخارجية في ملفات Excel باستخدام Aspose.Cells لـ .NET. لا تُحسّن هذه الوظيفة قدرات تطبيقك فحسب، بل تُبسّط أيضًا كيفية إدارة مجموعات البيانات والعروض التقديمية. باتباع الخطوات الموضحة أعلاه، يمكنك تكييف هذا الحل ليناسب متطلبات مشروعك الفريدة.

## الأسئلة الشائعة

### ما هو Aspose.Cells؟
Aspose.Cells عبارة عن مكتبة قوية مصممة لمطوري .NET لإنشاء ملفات Excel ومعالجتها وإدارتها دون الحاجة إلى Microsoft Excel.

### كيف يمكنني تنزيل Aspose.Cells لـ .NET؟
يمكنك تنزيله من [موقع Aspose](https://releases.aspose.com/cells/net/).

### هل هناك نسخة تجريبية مجانية متاحة؟
نعم! تقدم Aspose نسخة تجريبية مجانية من Aspose.Cells، متوفرة على موقعها. [صفحة الإصدار](https://releases.aspose.com/cells/net/).

### ما هي أنواع الملفات التي يدعمها Aspose.Cells؟
يدعم Aspose.Cells تنسيقات Excel المختلفة، بما في ذلك XLS، وXLSX، وCSV، والمزيد.

### أين يمكنني العثور على الدعم لـ Aspose.Cells؟
قم بزيارة [منتدى أسبوزي](https://forum.aspose.com/c/cells/9) للحصول على المساعدة والدعم المجتمعي.