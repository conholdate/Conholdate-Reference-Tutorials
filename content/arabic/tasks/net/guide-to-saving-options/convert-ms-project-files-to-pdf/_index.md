---
"description": "تعرّف على كيفية تحويل ملفات Microsoft Project (.mpp) إلى PDF باستخدام Aspose.Tasks لـ .NET. اتبع هذا الدليل التفصيلي لتخصيص إخراج PDF، واختيار صفحات محددة، وأتمتة تحويلات الدفعات."
"linktitle": "خيارات حفظ PDF لـ Aspose.Tasks"
"second_title": "واجهة برمجة تطبيقات Aspose.Tasks .NET"
"title": "تحويل ملفات MS Project إلى PDF باستخدام Aspose.Tasks لـ .NET"
"url": "/ar/tasks/net/guide-to-saving-options/convert-ms-project-files-to-pdf/"
"weight": 13
---

## مقدمة

تلعب إدارة ملفات المشاريع الفعّالة دورًا محوريًا في تبسيط سير العمل ونجاح المشاريع. باستخدام Aspose.Tasks لـ .NET، يمكن للمطورين تحويل ملفات Microsoft Project إلى صيغة PDF بدقة ومرونة. في هذا الدليل، سنشرح خطوة بخطوة عملية حفظ ملفات Microsoft Project (.mpp) كملفات PDF، مع خيارات قابلة للتخصيص.

## المتطلبات الأساسية لاستخدام Aspose.Tasks لـ .NET

قبل المتابعة، تأكد من استيفاء المتطلبات الأساسية التالية:

1. Aspose.Tasks لتثبيت .NET  
   قم بتنزيل المكتبة وتثبيتها من [موقع إلكتروني](https://releases.aspose.com/tasks/net/).

2. بيئة التطوير  
   معرفة عملية بلغة البرمجة C# وبيئة تطوير .NET مهيأة.

3. إدخال ملف Microsoft Project  
   لديك صالحة `.mpp` الملف متاح للتحويل.

## استيراد مساحات الأسماء الأساسية

قبل الترميز، قم بتضمين المساحات الأساسية اللازمة للوصول إلى وظائف Aspose.Tasks. 

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System.Collections.Generic;
```

## الخطوة 1: تحميل ملف Microsoft Project

للبدء، قم بتحميل `.mpp` الملف في `Project` الكائن. استبدل `"Your_Project_File_Path.mpp"` مع المسار إلى ملف الإدخال الخاص بك.

```csharp
var project = new Project("Your_Project_File_Path.mpp");
```

## الخطوة 2: تكوين خيارات حفظ PDF

حدّد خيارات تخصيص ملف PDF الناتج. يوفر Aspose.Tasks لـ .NET مرونةً في التحكم في عرض الصفحات وتخطيطها وجوانب أخرى.

```csharp
var options = new PdfSaveOptions
{
    RenderToSinglePage = false, // ما إذا كان سيتم عرض كل المحتوى على صفحة واحدة
    Pages = new List<int>()     // الصفحات المراد تضمينها في ملف PDF
};
```

## الخطوة 3: تحديد عدد الصفحات

استخدم `PageCount` لتحديد عدد الصفحات التي يغطيها المشروع. يساعد هذا في تحديد ما إذا كنت ترغب في تضمين صفحات محددة أو تصديرها جميعها.

```csharp
Console.WriteLine("Total Pages: " + options.PageCount);
```

## الخطوة 4: تحديد صفحات محددة للتصدير (اختياري)

حدد الصفحات الدقيقة التي سيتم تضمينها في ملف PDF عن طريق ملء `Pages` الملكية. على سبيل المثال، لتصدير الصفحتين 1 و4:

```csharp
options.Pages.Add(1);
options.Pages.Add(4);
```

## الخطوة 5: احفظ ملف المشروع بتنسيق PDF

وأخيرا، احفظ `.mpp` الملف كملف PDF عن طريق استدعاء `Save` الطريقة. حدد مسار ملف الإخراج وأدخل الخيارات المُهيأة.

```csharp
project.Save("Output_PDF_File_Path.pdf", options);
```

## خاتمة

يضمن تحويل ملفات Microsoft Project إلى PDF باستخدام Aspose.Tasks لـ .NET تجربة سلسة وقابلة للتخصيص. من تحديد صفحات محددة إلى أتمتة عمليات التصدير على دفعات، تُمكّن هذه الأداة المطورين من التعامل مع ملفات المشاريع بفعالية.

## الأسئلة الشائعة

### هل يمكنني تخصيص مظهر ملف PDF المُصدَّر؟
نعم، يسمح لك Aspose.Tasks بتخصيص الخطوط والألوان وتخطيطات الصفحات لتلبية احتياجاتك المحددة.

### هل من الممكن التحويل `.mpp` الملفات من الإصدارات الأقدم من Microsoft Project؟
يدعم Aspose.Tasks `.mpp` الملفات من Microsoft Project 2003 فصاعدًا.

### كيف يمكنني عرض كافة بيانات المشروع على صفحة PDF واحدة؟
ضبط `RenderToSinglePage` ممتلكات `PdfSaveOptions` الاعتراض على `true`.

```csharp
options.RenderToSinglePage = true;
```

### هل يمكنني تصدير بيانات المشروع إلى تنسيقات ملفات أخرى؟
نعم، يدعم Aspose.Tasks التصدير إلى تنسيقات مختلفة بما في ذلك Excel وHTML وتنسيقات الصور مثل PNG وJPEG.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks لـ .NET؟
نعم يمكنك تنزيل [نسخة تجريبية مجانية هنا](https://releases.aspose.com/).