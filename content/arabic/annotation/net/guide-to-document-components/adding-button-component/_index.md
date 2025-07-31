---
"description": "اكتشف كيفية تحسين مستندات PDF الخاصة بك بإضافة مكونات أزرار تفاعلية باستخدام GroupDocs.Annotation لـ .NET. هذا البرنامج التعليمي خطوة بخطوة."
"linktitle": "إضافة مكونات الزر"
"second_title": "GroupDocs.Annotation .NET API"
"title": "إضافة مكونات الأزرار باستخدام GroupDocs.Annotation لـ .NET"
"url": "/ar/annotation/net/guide-to-document-components/adding-button-component/"
"weight": 10
---

## مقدمة

في هذا البرنامج التعليمي، سنشرح لك العملية البسيطة لإضافة مكون زر إلى مستند PDF باستخدام مكتبة GroupDocs.Annotation لـ .NET. بنهاية هذا الدليل، ستكون قادرًا على تحسين مستندات PDF الخاصة بك بميزات تفاعلية.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. GroupDocs.Annotation لـ .NET: قم بتنزيل مكتبة GroupDocs.Annotation لـ .NET وتثبيتها من [هنا](https://releases.groupdocs.com/annotation/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير مناسبة مع تثبيت إطار عمل .NET.

## الخطوة 1: استيراد مساحات الأسماء الضرورية

ابدأ باستيراد المساحات المطلوبة إلى مشروعك:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Annotation.Models;
using GroupDocs.Annotation.Models.AnnotationModels;
using GroupDocs.Annotation.Models.FormatSpecificComponents.Pdf;
using GroupDocs.Annotation.Options;
```

## الخطوة 2: تهيئة مسار الإخراج

قم بتحديد مسار الإخراج حيث سيتم حفظ ملف PDF المعدل:

```csharp
string outputPath = Path.Combine("Your Document Directory", "result" + Path.GetExtension("input.pdf"));
```

## الخطوة 3: إضافة مكون زر

الآن، دعنا نقوم بإنشاء مكون الزر وإضافته إلى ملف PDF الخاص بك:

```csharp
using (Annotator annotator = new Annotator("input.pdf"))
{
    ButtonComponent button = new ButtonComponent
    {
        Box = new Rectangle(100, 100, 100, 100), // موضع وحجم الزر
        PenColor = 65535,                       // لون حدود الزر
        Style = BorderStyle.Dashed,             // نمط الحدود
        BorderWidth = 0,                        // عرض الحدود
        BorderColor = 0,                        // لون الحدود
        AlternateName = "Name",                 // الاسم البديل للزر
        PartialName = "Partial Name",           // الاسم الجزئي للزر
        NormalCaption = "Caption",               // النص المعروض على الزر
        ButtonColor = 16761035,                 // لون خلفية الزر
        Replies = new List<Reply>
        {
            new Reply { Comment = "First comment", RepliedOn = DateTime.Now },
            new Reply { Comment = "Second comment", RepliedOn = DateTime.Now }
        }
    };

    annotator.Add(button); // أضف الزر إلى الموضح
    annotator.Save("result.pdf"); // حفظ ملف PDF المعدل
}
```

## الخطوة 4: عرض مسار الإخراج

وأخيرًا، أبلغ المستخدم بمكان حفظ ملف الإخراج:

```csharp
Console.WriteLine($"\nDocument saved successfully.\nCheck output in {outputPath}.");
```

تهانينا! لقد نجحت في إضافة زر إلى مستند PDF باستخدام GroupDocs.Annotation لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية دمج مكونات الأزرار في مستندات PDF باستخدام GroupDocs.Annotation لـ .NET. باتباع هذه الخطوات، يمكنك تحسين تفاعلية مستندات PDF بشكل ملحوظ.

## الأسئلة الشائعة

### هل يمكنني تخصيص مظهر الزر؟

بالتأكيد! يمكنك تعديل خصائص متنوعة، كالحجم واللون والنمط، لتناسب احتياجاتك.

### هل GroupDocs.Annotation لـ .NET متوافق مع كافة إصدارات PDF؟

نعم، يدعم GroupDocs.Annotation لـ .NET مجموعة واسعة من إصدارات PDF، مما يضمن التوافق مع معظم المستندات.

### هل يمكنني إضافة مكونات زر متعددة إلى مستند PDF واحد؟

نعم، يمكنك إضافة عدد غير محدود من مكونات الأزرار إلى مستند PDF.

### هل يدعم GroupDocs.Annotation لـ .NET تنسيقات الملفات الأخرى؟

نعم، فهو يدعم تنسيقات المستندات المختلفة، بما في ذلك DOCX وPPTX وXLSX، بالإضافة إلى PDF.

### هل هناك نسخة تجريبية متاحة لأغراض الاختبار؟

نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من GroupDocs.Annotation لـ .NET من [هنا](https://releases.groupdocs.com/).