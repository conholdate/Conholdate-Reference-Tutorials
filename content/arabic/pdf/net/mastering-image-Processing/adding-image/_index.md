---
"description": "تعرّف على كيفية إضافة الصور برمجيًا إلى ملفات PDF باستخدام Aspose.PDF لـ .NET. يغطي هذا البرنامج التعليمي الشامل كل خطوة، بدءًا من إعداد بيئتك ووصولًا إلى عرض الصور على صفحات محددة."
"linktitle": "إضافة صورة في ملف PDF"
"second_title": "مرجع Aspose.PDF لـ .NET API"
"title": "إضافة صورة في ملف PDF"
"url": "/ar/pdf/net/mastering-image-Processing/adding-image/"
"weight": 10
---

## مقدمة

هل سبق لك أن احتجت إلى إدراج صورة في ملف PDF برمجيًا؟ سواء كنت تُطوّر نظامًا لإنشاء المستندات أو تُضيف عناصر هوية تجارية، يُسهّل Aspose.PDF لـ .NET هذه المهمة. في هذا البرنامج التعليمي، سنشرح لك خطوات إضافة صورة إلى ملف PDF.

## المتطلبات الأساسية

قبل أن نبدأ في الترميز، تأكد من أن لديك ما يلي:

- Aspose.PDF لمكتبة .NET: قم بتنزيل أحدث إصدار وتثبيته من [تنزيلات Aspose](https://releases.aspose.com/pdf/net/).
- بيئة تطوير .NET: يمكنك استخدام Visual Studio أو أي بيئة تطوير متكاملة من اختيارك.
- المعرفة الأساسية بلغة C#: المعرفة ببرمجة C# ومبادئ البرمجة الكائنية التوجه مفيدة.
- ملفات العينة: ملف PDF وصورة (على سبيل المثال، شعار) للإدراج.

## الخطوة 1: إعداد بيئة التطوير الخاصة بك

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE). استورد مساحات الأسماء اللازمة للعمل مع Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

ستتيح لك هذه المساحات الأسماء التعامل مع مستندات PDF والتعامل مع تدفقات الملفات بشكل فعال.

## الخطوة 2: افتح مستند PDF

حدد موقع ملف PDF الخاص بك وافتحه باستخدام `Document` فصل:

```csharp
// حدد المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح مستند PDF
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

تأكد من الاستبدال `YOUR DOCUMENT DIRECTORY` مع المسار الفعلي الذي يتم تخزين ملف PDF الخاص بك فيه.

## الخطوة 3: تحديد إحداثيات الصورة

قم بتعيين إحداثيات المكان الذي سيتم وضع الصورة فيه في ملف PDF:

```csharp
// تحديد إحداثيات الصورة
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

تحدد هذه الإحداثيات موضع وحجم الصورة على الصفحة.

## الخطوة 4: حدد الصفحة لإدراج الصورة

اختر الصفحة التي تريد إضافة الصورة إليها في ملف PDF. تذكر أن Aspose.PDF يستخدم فهرسة أحادية للصفحات:

```csharp
// احصل على الصفحة الأولى من ملف PDF
Page page = pdfDocument.Pages[1];
```

## الخطوة 5: تحميل الصورة في مجرى

قم بتحميل الصورة التي تريد إدراجها في مجرى البيانات:

```csharp
// تحميل الصورة في تيار
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open))
{
    // إضافة صورة إلى موارد الصفحة
    page.Resources.Images.Add(imageStream);
}
```

تأكد من أن مسار ملف الصورة صحيح.

## الخطوة 6: حفظ حالة الرسومات الحالية

قبل وضع الصورة، احفظ حالة الرسومات الحالية:

```csharp
// حفظ حالة الرسومات الحالية
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## الخطوة 7: تحديد موضع الصورة باستخدام المستطيل والمصفوفة

إنشاء `Rectangle` لوضع الصورة و `Matrix` للقياس:

```csharp
// إنشاء كائنات المستطيل والمصفوفة
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## الخطوة 8: تطبيق تحويل المصفوفة

استخدم `ConcatenateMatrix` المشغل لوضع الصورة بشكل صحيح:

```csharp
// تطبيق تحويل المصفوفة
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## الخطوة 9: عرض الصورة على صفحة PDF

تقديم الصورة باستخدام `Do` المشغل:

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// ارسم الصورة على الصفحة
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## الخطوة 10: استعادة حالة الرسومات

بعد عرض الصورة، قم باستعادة حالة الرسومات:

```csharp
// استعادة حالة الرسومات
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## الخطوة 11: حفظ مستند PDF المحدث

وأخيرًا، احفظ ملف PDF المعدّل:

```csharp
dataDir = dataDir + "AddImage_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
```

## خاتمة

إدراج صورة في ملف PDF باستخدام Aspose.PDF لـ .NET عملية سهلة وبسيطة، مقسمة إلى خطوات واضحة. تتيح لك هذه الطريقة تخصيص ملفات PDF الخاصة بك بسهولة باستخدام الشعارات والعلامات المائية والصور الأخرى.

## الأسئلة الشائعة

### هل يمكنني إضافة صور متعددة إلى صفحة واحدة؟
نعم، يمكنك تكرار الخطوات لكل صورة تريد إدراجها.

### كيف يمكنني التحكم بحجم الصورة المدرجة؟
يتم تحديد الحجم من خلال إحداثيات المستطيل الذي تحدده.

### هل يمكنني إدراج أنواع أخرى من الملفات مثل PNG أو GIF؟
نعم، يدعم Aspose.PDF تنسيقات الصور المختلفة، بما في ذلك PNG، وGIF، وBMP، وJPEG.

### هل من الممكن إضافة الصور بشكل ديناميكي؟
بالتأكيد! يمكنك تحميل الصور ديناميكيًا عن طريق تحديد مسار الملف أو استخدام التدفقات.

### هل يمكنني إضافة الصور بكميات كبيرة إلى صفحات متعددة؟
نعم، يمكنك التنقل بين الصفحات في مستند وإضافة الصور باستخدام نفس النهج.