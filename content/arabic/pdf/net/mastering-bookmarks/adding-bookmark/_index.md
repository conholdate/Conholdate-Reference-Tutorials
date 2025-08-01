---
"description": "تعرّف على كيفية إضافة إشارات مرجعية إلى مستندات PDF برمجيًا باستخدام Aspose.PDF لـ .NET. يغطي هذا الدليل التفصيلي كل شيء، بدءًا من استيراد الحزم اللازمة ووصولًا إلى حفظ المستند المعدّل."
"linktitle": "إضافة إشارة مرجعية في ملف PDF"
"second_title": "مرجع Aspose.PDF لـ .NET API"
"title": "إضافة إشارة مرجعية في ملف PDF"
"url": "/ar/pdf/net/mastering-bookmarks/adding-bookmark/"
"weight": 10
---

## مقدمة

قد يكون تصفح مستندات PDF الكبيرة مهمة شاقة. عند البحث عن معلومات محددة داخل مستند متعدد الصفحات، قد يُضيع التمرير المتواصل وقتًا ثمينًا. تُقدم الإشارات المرجعية حلاً بسيطًا لهذه المشكلة، حيث تُتيح لك الانتقال بسرعة إلى الأقسام ذات الصلة في ملف PDF. سيُرشدك هذا البرنامج التعليمي خطوة بخطوة حول كيفية إضافة إشارات مرجعية إلى ملفات PDF باستخدام Aspose.PDF for .NET، وهي مكتبة قوية مُصممة للعمل مع ملفات PDF في تطبيقات .NET.

## المتطلبات الأساسية

قبل الغوص في الكود، دعنا نتأكد من أن لديك الأدوات والمعرفة اللازمة للمتابعة:

- Visual Studio: تعد بيئة التطوير المتكاملة (IDE) هذه ضرورية لتطوير .NET.
- Aspose.PDF لـ .NET: نزّل وثبّت مكتبة Aspose.PDF للتعامل مع ملفات PDF في مشروعك. تفضل بزيارة [صفحة التحميل](https://releases.aspose.com/pdf/net/) للبدء.
- المعرفة الأساسية بلغة C#: ستساعدك المعرفة ببرمجة C# على متابعة الأمثلة المذكورة في هذا الدليل بسلاسة.

### إنشاء تطبيق وحدة تحكم جديد

1. افتح Visual Studio وقم بإنشاء مشروع تطبيق وحدة التحكم C# جديد.
2. قم بتسمية مشروعك بشكل مناسب، مثل "PDFBookmarkingDemo".

### أضف مكتبة Aspose.PDF إلى مشروعك

لاستخدام Aspose.PDF لـ .NET في مشروعك:

1. انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول.
2. حدد إدارة حزم NuGet.
3. ابحث عن Aspose.PDF وانقر فوق "تثبيت" لإضافة المكتبة إلى مشروعك.

### استيراد مساحات الأسماء الضرورية

في الجزء العلوي من `Program.cs` الملف، قم باستيراد المساحات التالية:

```csharp
using System;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

توفر هذه المساحات الاسمية إمكانية الوصول إلى الفئات الأساسية للعمل مع مستندات PDF والتعليقات التوضيحية مثل الإشارات المرجعية.

## الخطوة 1: تحديد دليل مستندات PDF

للبدء، حدد المجلد الذي يوجد فيه ملف PDF. سيُستخدم هذا المجلد لتحميل ملف PDF وحفظه. إليك مثال:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

يستبدل `"C:\\YourDirectory\\"` مع المسار الفعلي للمجلد الذي يحتوي على ملف PDF.

## الخطوة 2: افتح مستند PDF

بعد ذلك، افتح مستند PDF الحالي الذي ستضيف إليه الإشارات المرجعية. استخدم `Document` الفئة لتحميل ملف PDF الخاص بك:

```csharp
Document pdfDocument = new Document(dataDir + "YourFile.pdf");
```

يقوم هذا الكود بتحميل ملف PDF من الدليل المحدد.

## الخطوة 3: إنشاء كائن إشارة مرجعية

الآن، سننشئ إشارة مرجعية ونضبط خصائصها. كل إشارة مرجعية تُمثّل رابطًا لقسم أو صفحة مُحددة داخل ملف PDF. يُنشئ الكود التالي إشارة مرجعية بعنوان "الفصل 1":

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Chapter 1";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
```

يمكنك تعديل عنوان ومظهر الإشارة المرجعية. في هذه الحالة، يكون عنوان "الفصل الأول" غامقًا ومائلًا للتأكيد.

## الخطوة 4: تحديد وجهة الإشارة المرجعية

لكل إشارة مرجعية وجهة. هذه الوجهة هي الصفحة المحددة في ملف PDF التي سترتبط بها الإشارة المرجعية. على سبيل المثال، لربط الإشارة المرجعية بالصفحة الأولى:

```csharp
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

يُحدد هذا الكود آلية انتقال الإشارة المرجعية إلى الصفحة الأولى من مستند PDF. عدّل رقم الصفحة بناءً على المكان الذي تريد أن تشير إليه الإشارة المرجعية.

## الخطوة 5: إضافة الإشارة المرجعية إلى المستند

بعد إعداد الإشارة المرجعية، حان وقت إضافتها إلى مجموعة مخططات ملف PDF. سيضمن هذا إدراج الإشارة المرجعية ضمن جدول المحتويات التفاعلي للمستند.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

يضيف هذا السطر من التعليمات البرمجية الإشارة المرجعية التي قمت بإنشائها حديثًا إلى مجموعة الخطوط العريضة لملف PDF.

## الخطوة 6: احفظ ملف PDF باستخدام الإشارة المرجعية

وأخيرًا، بعد إضافة الإشارة المرجعية، قم بحفظ ملف PDF المعدل مع الإشارة المرجعية الجديدة المضمنة:

```csharp
dataDir = dataDir + "YourFile_with_Bookmark.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

يحفظ هذا الكود ملف PDF مع الإشارة المرجعية المضافة باسم "YourFile_with_Bookmark.pdf" في الدليل المحدد.

## خاتمة

إضافة الإشارات المرجعية إلى ملفات PDF طريقة بسيطة وفعّالة لتحسين تصفح مستنداتك وسهولة استخدامها. باستخدام Aspose.PDF لـ .NET، يمكنك بسرعة إضافة إشارات مرجعية تتيح للمستخدمين الانتقال إلى صفحات أو أقسام محددة، مما يُحسّن تجربة المستخدم بشكل عام. باتباع هذا الدليل، ستتعلم كيفية إنشاء الإشارات المرجعية وتخصيصها وإضافتها إلى ملفات PDF ببضعة أسطر من التعليمات البرمجية.

## الأسئلة الشائعة

### هل يمكنني إضافة إشارات مرجعية متعددة إلى ملف PDF؟

نعم، يتيح لك Aspose.PDF لـ .NET إضافة أي عدد من الإشارات المرجعية التي تحتاجها. ما عليك سوى إنشاء عدة `OutlineItemCollection` الكائنات وإضافتها إلى مجموعة مخططات المستند.

### كيف يمكنني تغيير مظهر الإشارة المرجعية؟

يمكنك تعديل مظهر الإشارة المرجعية باستخدام خصائص مثل `Italic`، `Bold`، و `Color` على `OutlineItemCollection` يمكنك أيضًا إضافة أيقونات أو أنماط مخصصة.

### هل Aspose.PDF مجاني للاستخدام؟

يقدم Aspose.PDF نسخة تجريبية مجانية تتيح لك استكشاف ميزاته. مع ذلك، للاستفادة الكاملة من الميزات، ستحتاج إلى شراء ترخيص. تحقق من [صفحة الشراء](https://purchase.aspose.com/buy) لمزيد من التفاصيل.

### أين يمكنني العثور على مزيد من الوثائق؟

للحصول على توثيق مفصل حول Aspose.PDF لـ .NET، قم بزيارة [التوثيق](https://reference.aspose.com/pdf/net/).

### كيف أحصل على الدعم لـ Aspose.PDF؟

إذا كنت بحاجة إلى مساعدة أو دعم، قم بزيارة [منتدى دعم Aspose](https://forum.aspose.com/c/pdf/10).