---
"description": "تعلّم خطوة بخطوة كيفية استخدام Aspose.Cells لـ .NET لتحويل نطاقات خلايا محددة في ورقة عمل Excel إلى ملفات صور بكفاءة. يغطي هذا الدليل الشامل المتطلبات الأساسية، وتعليمات الإعداد، ومثالًا برمجيًا."
"linktitle": "تصدير نطاقات خلايا Excel كصور باستخدام Aspose.Cells لـ .NET"
"second_title": "واجهة برمجة تطبيقات معالجة Excel لـ Aspose.Cells .NET"
"title": "تصدير نطاقات خلايا Excel كصور باستخدام Aspose.Cells لـ .NET"
"url": "/ar/cells/net/mastering-rendering-and-exporting/export-excel-cell-ranges-as-images/"
"weight": 14
---

## مقدمة

عند العمل مع ملفات Excel، تُعدّ مشاركة نطاقات محددة من البيانات كصور مفيدة للغاية، سواءً للتقارير أو العروض التقديمية أو للمشاركة السريعة. في هذا الدليل، سنستكشف كيفية تصدير نطاقات الخلايا إلى صور باستخدام Aspose.Cells لـ .NET. باتباع التعليمات خطوة بخطوة، ستتمكن من إدارة هذه العملية بسلاسة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي جاهزًا:

1. Visual Studio: سوف تحتاج إلى تثبيت Visual Studio على جهاز الكمبيوتر الخاص بك.
2. Aspose.Cells لـ .NET: قم بتنزيل المكتبة من [موقع Aspose](https://releases.aspose.com/cells/net/)يمكنك اختيار تجربة مجانية لاستكشاف الميزات.
3. المعرفة الأساسية بلغة C#: ستساعدك المعرفة بلغة C# و.NET على متابعة هذا البرنامج التعليمي بسهولة أكبر.
4. ملف Excel النموذجي: في هذا العرض التوضيحي، سنستخدم ملفًا باسم `sampleExportRangeOfCellsInWorksheetToImage.xlsx`، والتي يمكنك إنشاؤها للاختبار.

## الخطوة 1: استيراد الحزم الضرورية

للعمل مع ملفات Excel والصور في .NET، تحتاج إلى استيراد المساحات التالية:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

توفر هذه المساحات الأسماء الأدوات اللازمة للتعامل مع مصنفات العمل، وعرض الصور، وإدارة خيارات الرسم.

## الخطوة 2: إعداد مسارات الدليل

بعد ذلك، قم بإنشاء مسارات الدليل المصدر والإخراج حيث يوجد ملف Excel الخاص بك والمكان الذي تريد حفظ الصورة الناتجة فيه.

```csharp
// تحديد أدلة المصدر والإخراج
string sourceDir = "Your Document Directory";
string outputDir = "Your Document Directory";
```

يستبدل `"Your Document Directory\\"` مع مسار الملف الفعلي الخاص بك.

## الخطوة 3: إنشاء مصنف من ملف المصدر

إنشاء `Workbook` مثال مع ملف Excel الخاص بك:

```csharp
// تحميل المصنف
Workbook workbook = new Workbook(sourceDir + "sampleExportRangeOfCellsInWorksheetToImage.xlsx");
```

يفتح هذا السطر ملف Excel الخاص بك لمزيد من التعديل.

## الخطوة 4: الوصول إلى ورقة العمل المطلوبة

بعد فتح المصنف، ستحتاج إلى الوصول إلى ورقة العمل المحددة التي تحتوي على البيانات التي تريد تصديرها.

```csharp
// الوصول إلى ورقة العمل الأولى
Worksheet worksheet = workbook.Worksheets[0];
```

بإمكانك تغيير الفهرس إذا كانت بياناتك موجودة على ورقة مختلفة.

## الخطوة 5: تحديد منطقة الطباعة

قم بتحديد نطاق الخلايا التي تريد تحويلها إلى صورة عن طريق تعيين منطقة الطباعة:

```csharp
// تعيين منطقة الطباعة
worksheet.PageSetup.PrintArea = "D8:G16";
```

ضبط مراجع الخلايا (`D8:G16`) وفقًا لاحتياجاتك المحددة.

## الخطوة 6: تكوين هوامش الصفحة

لتجنب وجود مسافات بيضاء إضافية في الصورة المصدرة، اضبط الهوامش على الصفر:

```csharp
// تعيين الهوامش إلى الصفر
worksheet.PageSetup.LeftMargin = 0;
worksheet.PageSetup.RightMargin = 0;
worksheet.PageSetup.TopMargin = 0;
worksheet.PageSetup.BottomMargin = 0;
```

## الخطوة 7: تعيين خيارات الصورة

الآن، قم بتحديد كيفية عرض الصورة، بما في ذلك الدقة والتنسيق:

```csharp
// إنشاء خيارات الصورة
ImageOrPrintOptions options = new ImageOrPrintOptions
{
    OnePagePerSheet = true,
    ImageType = ImageType.Jpeg,
    HorizontalResolution = 200,
    VerticalResolution = 200
};
```

هنا، ستكون الصورة بصيغة JPEG بدقة 200 نقطة في البوصة. عدّل هذه الإعدادات حسب الحاجة.

## الخطوة 8: تحويل ورقة العمل إلى صورة

حان الوقت لتحويل النطاق المحدد إلى صورة:

```csharp
// تحويل ورقة العمل إلى صورة
SheetRender sr = new SheetRender(worksheet, options);
sr.ToImage(0, outputDir + "outputExportRangeOfCellsInWorksheetToImage.jpg");
```

سيؤدي هذا إلى حفظ الصورة في دليل الإخراج المحدد.

## الخطوة 9: تأكيد التنفيذ

لتقديم تعليقات بعد التصدير، اطبع رسالة نجاح على وحدة التحكم:

```csharp
Console.WriteLine("ExportRangeOfCellsInWorksheetToImage executed successfully.");
```

## خاتمة

لقد نجحتَ في تعلّم كيفية تصدير نطاق من الخلايا من ورقة عمل Excel إلى صورة باستخدام Aspose.Cells لـ .NET! تُعد هذه الميزة مفيدةً للغاية لمشاركة البيانات بكفاءة أو إنشاء عروض مرئية لمعلوماتك.

## الأسئلة الشائعة

### هل يمكنني تغيير صيغة الصورة؟

نعم! يمكنك بسهولة تغيير `ImageType` تحويل الخاصية إلى تنسيقات أخرى مثل PNG أو BMP.

### ماذا لو أردت تصدير نطاقات متعددة؟

سوف تحتاج إلى تكرار عملية العرض لكل نطاق ترغب في تصديره.

### هل هناك حد لحجم النطاق الذي يمكنني تصديره؟

صُمم Aspose.Cells للتعامل مع نطاقات كبيرة، ولكن قد يختلف الأداء. يُنصح بإجراء الاختبار ضمن حدود معقولة.

### هل يمكنني أتمتة هذه العملية؟

بالتأكيد! يمكنك دمج هذه الوظيفة في تطبيقات أو نصوص برمجية أكبر للأتمتة.

### أين يمكنني الحصول على الدعم الإضافي؟

لمزيد من المساعدة، قم بزيارة [منتدى دعم Aspose](https://forum.aspose.com/c/cells/9).