---
"description": "اكتشف كيفية تحسين تصفح مستندات PDF بإضافة إشارات مرجعية فرعية باستخدام Aspose.PDF لـ .NET. يوفر هذا الدليل المفصل الأدوات والتقنيات اللازمة."
"linktitle": "إضافة إشارة مرجعية فرعية في ملف PDF"
"second_title": "مرجع Aspose.PDF لـ .NET API"
"title": "إضافة إشارة مرجعية فرعية في ملف PDF"
"url": "/ar/pdf/net/mastering-bookmarks/adding-child-bookmark/"
"weight": 20
---

## مقدمة

في عالمنا الرقمي اليوم، تُعدّ إدارة المستندات بكفاءة أمرًا بالغ الأهمية، خاصةً عند التعامل مع ملفات PDF. هل سبق لك أن وجدت نفسك تتصفح ملف PDF طويلًا بلا نهاية، باحثًا عن قسم محدد؟ أمرٌ مُحبط، أليس كذلك؟ وهنا يأتي دور الإشارات المرجعية! فهي تعمل كجدول محتويات، مما يُتيح للقراء التنقل عبر المستندات بسهولة. في هذا البرنامج التعليمي، سنستكشف كيفية إضافة إشارات مرجعية فرعية إلى ملف PDF باستخدام Aspose.PDF لـ .NET. بنهاية هذا الدليل، ستُحسّن مستندات PDF الخاصة بك، مما يجعلها أكثر سهولة في الاستخدام وتنظيمًا.

## المتطلبات الأساسية

قبل أن نبدأ في إضافة الإشارات المرجعية، تأكد من توفر ما يلي:

1. Aspose.PDF لـ .NET: قم بتنزيل المكتبة من [موقع Aspose](https://releases.aspose.com/pdf/net/).
2. Visual Studio: بيئة تطوير لكتابة واختبار الكود الخاص بك.
3. المعرفة الأساسية بلغة C#: ستساعدك المعرفة ببرمجة C# على فهم مقتطفات التعليمات البرمجية.

## إنشاء مشروع جديد

1. افتح Visual Studio وأنشئ مشروع C# جديدًا. اختر تطبيق وحدة التحكم لتسهيل الأمر.

## إضافة مرجع Aspose.PDF

1. انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول.
2. حدد "إدارة حزم NuGet".
3. ابحث عن "Aspose.PDF" وقم بتثبيت الإصدار الأحدث.

## استيراد مساحات الأسماء المطلوبة

في الجزء العلوي من `Program.cs` الملف، استيراد المساحات الأساسية اللازمة:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

## الخطوة 1: حدد دليل المستندات الخاص بك

قبل التعامل مع أي ملف PDF، حدد مكان تخزين مستنداتك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

يستبدل `"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لملف PDF الخاص بك.

## الخطوة 2: افتح مستند PDF

الآن، دعنا نفتح مستند PDF الذي تريد العمل عليه:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## الخطوة 3: إنشاء إشارة مرجعية للوالدين

بعد ذلك، قم بإنشاء إشارة مرجعية رئيسية ستكون بمثابة العنوان الرئيسي لإشارات المرجعية الفرعية الخاصة بك:

```csharp
OutlineItemCollection parentBookmark = new OutlineItemCollection(pdfDocument.Outlines)
{
    Title = "Parent Outline",
    Italic = true,
    Bold = true
};
```

## الخطوة 4: إنشاء إشارة مرجعية فرعية

الآن، دعنا نضيف إشارة مرجعية فرعية أسفل الإشارة المرجعية الأصلية:

```csharp
OutlineItemCollection childBookmark = new OutlineItemCollection(pdfDocument.Outlines)
{
    Title = "Child Outline",
    Italic = true,
    Bold = true
};
```

## الخطوة 5: ربط الإشارة المرجعية للطفل بالإشارة المرجعية للوالد

بعد إنشاء كلا العلامتين المرجعيتين، قم بربط العلامة المرجعية الفرعية بالعلامة المرجعية الأصلية:

```csharp
parentBookmark.Add(childBookmark);
```

## الخطوة 6: إضافة الإشارة المرجعية الأصلية إلى المستند

الآن، قم بإضافة الإشارة المرجعية الأصلية (مع الإشارة المرجعية التابعة لها) إلى مجموعة مخططات المستند:

```csharp
pdfDocument.Outlines.Add(parentBookmark);
```

## الخطوة 7: حفظ المستند

وأخيرًا، احفظ التغييرات التي أجريتها على مستند PDF:

```csharp
dataDir = dataDir + "AddChildBookmark_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهانينا! لقد نجحت في إضافة إشارات مرجعية فرعية إلى ملف PDF باستخدام Aspose.PDF لـ .NET. تُحسّن هذه الميزة بشكل كبير سهولة استخدام مستنداتك، مما يُسهّل على القراء تصفحها. سواء كنت تُنشئ تقارير أو كتبًا إلكترونية أو أي مستندات PDF أخرى، فإن الإشارات المرجعية تُحدث فرقًا كبيرًا.

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET عبارة عن مكتبة قوية تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا.

### هل يمكنني إضافة إشارات مرجعية متعددة للأطفال؟
نعم، يمكنك إنشاء عدة إشارات مرجعية فرعية ضمن إشارة مرجعية رئيسية واحدة عن طريق تكرار الخطوات الخاصة بإنشاء الإشارات المرجعية الفرعية وإضافتها.

### هل استخدام Aspose.PDF مجاني؟
يقدم Aspose.PDF نسخة تجريبية مجانية، ولكن للاستفادة الكاملة من الميزات، ستحتاج إلى شراء ترخيص. تحقق من [صفحة الشراء](https://purchase.aspose.com/buy) لمزيد من التفاصيل.

### أين يمكنني العثور على مزيد من الوثائق؟
يمكن العثور على وثائق شاملة لـ Aspose.PDF لـ .NET [هنا](https://reference.aspose.com/pdf/net/).

### ماذا لو واجهت مشاكل؟
إذا واجهت أي مشاكل، يمكنك طلب المساعدة على [منتدى دعم Aspose](https://forum.aspose.com/c/pdf/10).