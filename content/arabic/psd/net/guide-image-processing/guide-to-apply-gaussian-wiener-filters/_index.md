---
"description": "اكتشف كيفية تقليل الضوضاء بفعالية وتحسين جودة الصورة في تطبيقات .NET باستخدام مرشحات Gaussian وWiener مع Aspose.PSD. يرشدك هذا الدليل الشامل خلال عملية الإعداد والتصفية."
"linktitle": "دليل لتطبيق المرشحات Gaussian وWiener"
"second_title": "واجهة برمجة تطبيقات Aspose.PSD .NET"
"title": "دليل لتطبيق مرشحات Gaussian وWiener في Aspose.PSD لـ .NET"
"url": "/ar/psd/net/guide-image-processing/guide-to-apply-gaussian-wiener-filters/"
"weight": 10
---

## مقدمة

في مجال معالجة الصور، وخاصةً في بيئات .NET، يتألق Aspose.PSD كمجموعة أدوات متعددة الاستخدامات. من بين ميزاته العديدة، تُعدّ إمكانية تطبيق مرشحات Gaussian وWiener فعّالة للغاية، مما يُمكّن المطورين من تحسين جودة الصور وتقليل الضوضاء وتحسين المخرجات المرئية بفعالية. ستُرشدك هذه المقالة إلى الخطوات اللازمة لتطبيق هذه المرشحات في تطبيقاتك.

## المتطلبات الأساسية

قبل البدء، تأكد من أن لديك ما يلي:

1. Aspose.PSD لـ .NET: قم بتنزيل المكتبة وتثبيتها من [توثيق Aspose.PSD لـ .NET](https://reference.aspose.com/psd/net/).
   
2. صورة نموذجية: جهّز صورة نموذجية واحدة على الأقل بصيغة PSD للاختبار. يمكنك العثور على مجموعة متنوعة من الصور النموذجية في وثائق Aspose.PSD.

3. إعداد IDE: يوصى باستخدام بيئة التطوير المتكاملة (IDE) المتوافقة مع .NET، مثل Visual Studio، لتنفيذ التعليمات البرمجية بسلاسة.

## الخطوة 1: استيراد مساحات الأسماء الضرورية

ابدأ باستيراد المساحات المطلوبة في مشروع C# الخاص بك للوصول إلى وظائف Aspose.PSD:

```csharp
using Aspose.PSD.ImageFilters.FilterOptions;
using Aspose.PSD.ImageOptions;
```

## الخطوة 2: تحميل الصورة المشوشة

ابدأ بتحميل صورتك المشوشة إلى التطبيق. عدّل مسار الملف حسب الحاجة:

```csharp
// حدد المسار إلى دليل المستندات الخاص بك.
string dataDir = "Your Document Directory";
string sourceFile = dataDir + @"sample.psd";

// تحميل الصورة المشوشة 
using (Image image = Image.Load(sourceFile))
{
    // المضي قدما في المعالجة الإضافية
}
```

## الخطوة 3: التحويل إلى RasterImage

لضمان التوافق مع عمليات التصفية، قم بتحويل صورتك المحملة إلى `RasterImage`:

```csharp
// تأكد من أن الصورة من نوع RasterImage للتصفية
RasterImage rasterImage = image as RasterImage;
if (rasterImage == null)
{
    Console.WriteLine("The image is not a RasterImage.");
    return;
}
```

## الخطوة 4: تكوين خيارات التصفية

بعد ذلك، قم بإنشاء وتكوين خيارات المرشح Gaussian وWiener من خلال تحديد قيم نصف القطر والسلاسة:

```csharp
// إنشاء مثيل لـ GaussWienerFilterOptions باستخدام المعلمات المحددة
GaussWienerFilterOptions options = new GaussWienerFilterOptions(12, 3)
{
    Grayscale = true // تم ضبطه على true لمعالجة التدرج الرمادي
};
```

## الخطوة 5: تطبيق المرشحات

قم بتطبيق خيارات الفلترة المُكوّنة على `RasterImage`:

```csharp
// قم بتطبيق مرشحات Gaussian و Wiener على الصورة
rasterImage.Filter(image.Bounds, options);
```

## الخطوة 6: احفظ الصورة الناتجة

أخيرًا، احفظ الصورة المُعالجة بالصيغة التي تريدها. في هذا المثال، سنحفظها بصيغة GIF:

```csharp
string destName = dataDir + @"gauss_wiener_out.gif";
image.Save(destName, new GifOptions());
Console.WriteLine($"Filtered image saved to: {destName}");
```

## خاتمة

تهانينا! لقد نجحت في تطبيق مرشحات Gaussian وWiener لتحسين جودة صورتك باستخدام Aspose.PSD لـ .NET. تُعد هذه المرشحات أدوات قيّمة في مختلف المجالات، من استعادة وضوح الصور إلى تحسين الرسومات في مشاريع التصميم.

## الأسئلة الشائعة

### هل يمكنني تطبيق هذه المرشحات على الصور بتنسيقات أخرى غير PSD؟

نعم، يدعم Aspose.PSD تنسيقات متعددة، بما في ذلك BMP، وJPEG، وPNG، والمزيد، مما يسمح بمعالجة الصور بشكل متنوع.

### ماذا تعني حجم نصف القطر وقيمة السلاسة؟

يحدد حجم نصف القطر مدى عمل الفلتر، بينما تعمل قيمة التنعيم على ضبط مستوى التنعيم المطبق على صورتك، مما يؤثر على حدتها وتفاصيلها بشكل عام.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.PSD؟

يمكنك الحصول على ترخيص مؤقت عن طريق زيارة [صفحة ترخيص Aspose.PSD المؤقت](https://purchase.conholdate.com/temporary-license/).

### أين يمكنني العثور على الدعم والموارد الإضافية؟

للاستفسارات والمساعدة، [منتدى Aspose.PSD](https://forum.aspose.com/c/psd/34) يعد مصدرًا رائعًا للتواصل مع المجتمع وفريق الدعم.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.PSD؟

نعم، يمكنك استكشاف ميزات Aspose.PSD عن طريق تنزيل [نسخة تجريبية مجانية](https://releases.aspose.com/).