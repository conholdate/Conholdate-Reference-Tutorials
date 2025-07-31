---
"description": "تعلّم كيفية تحويل مخططات CAD بكفاءة إلى صيغ صور نقطية متنوعة باستخدام Aspose.CAD لـ .NET. يرشدك هذا الدليل الشامل خلال العملية بترميز واضح."
"linktitle": "تحويل تصدير CAD إلى صورة نقطية"
"second_title": "Aspose.CAD .NET - تنسيق ملفات CAD وBIM"
"title": "تحويل تصدير CAD إلى صورة نقطية باستخدام Aspose.CAD لـ .NET"
"url": "/ar/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## مقدمة

هل ترغب في تحويل مخططات CAD إلى صور نقطية بسهولة باستخدام Aspose.CAD لـ .NET؟ صُمم هذا الدليل التفصيلي لمساعدتك في إتمام العملية، مع شروحات برمجية موجزة لتجربة سلسة. سواء كنت مطورًا خبيرًا أو مبتدئًا، يوفر هذا البرنامج التعليمي معلومات قيّمة تناسب جميع مستويات المهارة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- مكتبة Aspose.CAD لـ .NET: قم بتنزيل المكتبة وتثبيتها من [موقع Aspose.CAD](https://releases.aspose.com/cad/net/).
- ملف رسم CAD: احتفظ بملف رسم CAD الخاص بك (على سبيل المثال، `conic_pyramid.dxf`) جاهزة للتحويل.

## استيراد مساحات الأسماء المطلوبة

في مشروع .NET الخاص بك، ستحتاج إلى استيراد مساحات الأسماء اللازمة لاستخدام دوال Aspose.CAD. أضف ما يلي إلى أعلى الكود:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## الخطوة 1: تحميل رسم CAD الخاص بك

أولاً، حدد الدليل وقم بتحميل ملف CAD الخاص بك إلى مثيل صورة:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// تحميل رسم CAD
using (var image = Image.Load(sourceFilePath))
{
    // انتقل إلى الخطوات التالية
}
```

## الخطوة 2: إنشاء خيارات التربيع

بعد ذلك، قم بإعداد خيارات التحويل إلى صورة نقطية، وتحديد الأبعاد المطلوبة للصورة الناتجة:

```csharp
// تهيئة خيارات CadRasterization
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## الخطوة 3: تحديد الطبقات للتحويل

إذا كنت تريد تحويل طبقات معينة، قم بإضافتها إلى خيارات التحويل النقطي الخاصة بك:

```csharp
// حدد الطبقة التي تريد تحويلها
rasterizationOptions.Layers = new [] { "LayerA" };
```

## الخطوة 4: إعداد خيارات تصدير JPEG

الآن، قم بإنشاء خيارات لتنسيق الصورة التي ترغب في تصديرها (JPEG في هذه الحالة):

```csharp
// إنشاء JpegOptions للتصدير
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## الخطوة 5: التصدير إلى تنسيق JPEG

وأخيرًا، احفظ الصورة المحولة:

```csharp
// تحديد مسار ملف الإخراج وحفظ الصورة
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## ميزة إضافية: تحويل جميع الطبقات

لتحويل كافة الطبقات في رسم CAD الخاص بك، يمكنك تنفيذ طريقة مثل هذه:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // قم بالتكرار خلال الطبقات وحفظ كل منها كملف JPEG منفصل
    // كود التنفيذ الخاص بك هنا
}
```

## خاتمة

تهانينا! لقد تعلمت كيفية تحويل مخططات CAD بفعالية إلى صيغ صور نقطية باستخدام Aspose.CAD لـ .NET. يقدم هذا الدليل نهجًا مباشرًا ومناسبًا للمطورين الذين يسعون إلى تحويلات CAD فعّالة.

## الأسئلة الشائعة

### هل يمكنني التصدير إلى تنسيقات صور مختلفة؟

بالتأكيد! ببساطة قم بالتبديل `JpegOptions` مع خيارات التنسيق الأخرى، مثل `PngOptions` أو `BmpOptions`، اعتمادًا على احتياجاتك.

### هل تتوفر نسخة تجريبية؟

نعم، يمكنك تنزيل نسخة تجريبية لاستكشاف الوظيفة من خلال اتباع ما يلي [وصلة](https://releases.aspose.com/cad/net/).

### أين يمكنني العثور على الدعم لـ Aspose.CAD؟

للحصول على دعم المجتمع، راجع Aspose.CAD [المنتدى](https://forum.aspose.com/c/cad/19)أو فكر في شراء ترخيص للحصول على مساعدة أكثر تخصصًا.

### هل التراخيص المؤقتة ممكنة؟

نعم، التراخيص المؤقتة متاحة؛ يمكنك طلب واحدة [هنا](https://purchase.conholdate.com/temporary-license/).

### أين يمكنني الوصول إلى الوثائق التفصيلية؟

قم بزيارة الوثائق الشاملة [هنا](https://reference.aspose.com/cad/net/) لمزيد من المعلومات.