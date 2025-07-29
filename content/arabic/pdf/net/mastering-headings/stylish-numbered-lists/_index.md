---
"description": "اكتشف كيفية إنشاء قوائم مرقمة بشكل جميل في مستندات PDF باستخدام Aspose.PDF لـ .NET. يرشدك هذا الدليل خلال عملية تطبيق أنماط الترقيم المختلفة، مثل الأرقام الرومانية."
"linktitle": "قوائم مرقمة أنيقة باستخدام Aspose.PDF لـ .NET"
"second_title": "مرجع Aspose.PDF لـ .NET API"
"title": "قوائم مرقمة أنيقة باستخدام Aspose.PDF لـ .NET"
"url": "/ar/net/programming-with-headings/stylish-numbered-lists/"
"weight": 10
---

## مقدمة

هل احتجت يومًا إلى إنشاء قوائم مرقمة ومنظمة جيدًا في مستندات PDF؟ سواءً كانت أوراقًا قانونية أو تقارير أو عروضًا تقديمية، فإن أساليب الترقيم الفعالة ضرورية لتنظيم محتواك. مع Aspose.PDF لـ .NET، يمكنك بسهولة تطبيق أساليب ترقيم متنوعة على عناوين ملفات PDF، مما ينتج عنه مستندات أنيقة واحترافية.

## المتطلبات الأساسية

قبل أن ننتقل إلى الترميز، تأكد من أن لديك ما يلي جاهزًا:

1. Aspose.PDF لـ .NET: قم بتنزيل أحدث إصدار من [هنا](https://releases.aspose.com/pdf/net/).
2. بيئة التطوير: ستحتاج إلى Visual Studio أو أي بيئة تطوير متكاملة متوافقة مع .NET.
3. .NET Framework: تأكد من تثبيت .NET Framework 4.0 أو أعلى.
4. الترخيص: يمكنك استخدام ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/) أو استكشاف [نسخة تجريبية مجانية](https://releases.aspose.com/) خيارات.

## استيراد الحزم المطلوبة

ابدأ باستيراد المساحات الأسماء الضرورية في مشروعك:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 1: إعداد المستند

لنبدأ بإنشاء مستند PDF جديد وتكوين تخطيطه، بما في ذلك حجم الصفحة والهوامش.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// تعيين أبعاد الصفحة والهوامش
pdfDoc.PageInfo.Width = 612.0; // 8.5 بوصة
pdfDoc.PageInfo.Height = 792.0; // 11 بوصة
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo(72, 72, 72, 72); // هوامش 1 بوصة
```

يتيح لك هذا الإعداد توفير حجم حرف قياسي للمستند الخاص بك مع هوامش تبلغ بوصة واحدة على جميع الجوانب.

## الخطوة 2: إضافة صفحة إلى ملف PDF

بعد ذلك، سنضيف صفحة فارغة إلى مستند PDF، حيث سنطبق أنماط الترقيم لاحقًا.

```csharp
// إضافة صفحة جديدة إلى مستند PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo = pdfDoc.PageInfo; // استخدم نفس الإعدادات الموجودة في المستند
```

## الخطوة 3: إنشاء صندوق عائم

يتيح لك FloatingBox وضع المحتوى بشكل مستقل عن تدفق الصفحة، مما يمنحك تحكمًا أكبر في تخطيطك.

```csharp
// إنشاء FloatingBox للمحتوى المنظم
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox
{
    Margin = pdfPage.PageInfo.Margin
};
pdfPage.Paragraphs.Add(floatBox);
```

## الخطوة 4: إضافة العناوين بالأرقام الرومانية

الآن، دعونا نضيف عنواننا الأول مع ترقيم الأرقام الرومانية بأحرف صغيرة.

```csharp
// إنشاء العنوان الأول بالأرقام الرومانية
Aspose.Pdf.Heading heading1 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 1,
    Text = "List 1",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading1);
```

## الخطوة 5: إضافة عنوان ثانٍ برقم بداية مخصص

بعد ذلك، سنضيف عنوانًا ثانيًا، بدءًا من الرقم الروماني 13.

```csharp
// إنشاء عنوان ثانٍ يبدأ بالرقم الروماني 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 13,
    Text = "List 2",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading2);
```

## الخطوة 6: إضافة عنوان مع ترقيم أبجدي

من أجل التنوع، دعونا نضيف عنوانًا ثالثًا باستخدام الترقيم الأبجدي بالأحرف الصغيرة.

```csharp
// إنشاء عنوان بترقيم أبجدي
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2)
{
    IsInList = true,
    StartNumber = 1,
    Text = "The value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed",
    Style = NumberingStyle.LettersLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading3);
```

## الخطوة 7: حفظ ملف PDF

وأخيرًا، دعنا نحفظ ملف PDF في الدليل المطلوب.

```csharp
// حفظ مستند PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine($"\nNumber style applied successfully in headings.\nFile saved at {dataDir}");
```

## خاتمة

تهانينا! لقد نجحت في تطبيق أنماط ترقيم متنوعة - أرقام رومانية وأبجدية - على عناوين ملفات PDF باستخدام Aspose.PDF لـ .NET. تتيح لك مرونة Aspose.PDF التحكم في تخطيط الصفحة، وأنماط الترقيم، وموضع المحتوى، مما يُمكّنك من إنشاء مستندات PDF منظمة واحترافية.

## الأسئلة الشائعة

### هل يمكنني تطبيق أنماط أرقام مختلفة على نفس مستند PDF؟  
نعم، يمكنك مزج أنماط الترقيم المختلفة، مثل الأرقام الرومانية، والأرقام العربية، والترقيم الأبجدي داخل نفس المستند.

### كيف يمكنني تخصيص الرقم الأولي للعناوين؟  
يمكنك تعيين رقم البداية لأي عنوان باستخدام `StartNumber` ملكية.

### هل هناك طريقة لإعادة تعيين تسلسل الترقيم؟  
نعم، يمكنك إعادة تعيين الترقيم عن طريق ضبط `StartNumber` الخاصية لكل عنوان.

### هل يمكنني تطبيق تنسيق غامق أو مائل على العناوين بالإضافة إلى الترقيم؟  
بالتأكيد! يمكنك تخصيص أنماط العناوين بتعديل خصائص مثل الخط والحجم والخط العريض والمائل باستخدام `TextState` هدف.

### كيف أحصل على ترخيص مؤقت لـ Aspose.PDF؟  
يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/) لاختبار Aspose.PDF دون قيود.