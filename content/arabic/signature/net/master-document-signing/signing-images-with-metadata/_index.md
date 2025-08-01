---
"description": "تعرّف على كيفية توقيع الصور بكفاءة باستخدام البيانات الوصفية في تطبيقات .NET باستخدام GroupDocs.Signature. يغطي هذا البرنامج التعليمي خطوة بخطوة كل شيء، من التثبيت إلى التنفيذ، مما يُمكّنك من تحسين مستنداتك باستخدام توقيعات البيانات الوصفية بسهولة."
"linktitle": "دليل توقيع الصور باستخدام البيانات الوصفية"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Signature .NET"
"title": "دليل لتوقيع الصور باستخدام البيانات الوصفية باستخدام GroupDocs.Signature"
"url": "/ar/signature/net/master-document-signing/signing-images-with-metadata/"
"weight": 10
---

## مقدمة

GroupDocs.Signature لـ .NET هي مكتبة فعّالة تُمكّن المطورين من توقيع الصور بكفاءة باستخدام البيانات الوصفية. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. GroupDocs.Signature لـ .NET: ثبّت حزمة GroupDocs.Signature في مشروع .NET الخاص بك. يمكنك تنزيلها من [هنا](https://releases.groupdocs.com/signature/net/).
2. ملف الصورة: قم بإعداد ملف الصورة الذي تريد توقيعه باستخدام البيانات الوصفية.

## استيراد مساحات الأسماء الضرورية

في كود C# الخاص بك، قم باستيراد المساحات التالية:

```csharp
using System;
using System.IO;
using GroupDocs.Signature;
using GroupDocs.Signature.Domain;
using GroupDocs.Signature.Options;
```

## الخطوة 1: تحميل ملف صورتك

ابدأ بتحديد المسار إلى ملف صورتك ودليل الإخراج للصورة الموقعة:

```csharp
string filePath = "sample.png";            
string outputFilePath = Path.Combine("Your Document Directory", "SignImageWithMetadata", "SignedWithMetadata.png");
```

## الخطوة 2: إنشاء توقيعات البيانات الوصفية

بعد ذلك، قم بإنشاء توقيعات البيانات الوصفية وأضفها إلى خيارات التوقيع:

```csharp
using (Signature signature = new Signature(filePath))
{
    ushort imgsMetadataId = 41996; // معرف البدء للبيانات الوصفية
    MetadataSignOptions options = new MetadataSignOptions();

    // إضافة أنواع مختلفة من توقيعات البيانات الوصفية
    options
        .Add(new ImageMetadataSignature(imgsMetadataId++, "Mr. Sherlock Holmes")) // قيمة السلسلة
        .Add(new ImageMetadataSignature(imgsMetadataId++, DateTime.Now))          // قيمة التاريخ والوقت
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123456))                // قيمة صحيحة
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123.456D))              // قيمة مزدوجة
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123.456M))              // القيمة العشرية
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123.456F));             // قيمة التعويم

    // توقيع الوثيقة وحفظ النتيجة
    SignResult result = signature.Sign(outputFilePath, options);
    Console.WriteLine($"\nDocument signed successfully with {result.Succeeded.Count} signature(s).\nFile saved at: {outputFilePath}");
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية توقيع صورة ببيانات وصفية باستخدام GroupDocs.Signature لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إضافة توقيعات وصفية إلى تطبيقات .NET، مما يُحسّن وظائف صورك وسلامتها.

## الأسئلة الشائعة

### هل يمكنني توقيع صور متعددة باستخدام البيانات الوصفية باستخدام GroupDocs.Signature لـ .NET؟
نعم، يمكنك توقيع صور متعددة عن طريق التكرار عبر كل ملف صورة وتطبيق توقيعات البيانات الوصفية.

### هل هناك نسخة تجريبية متاحة لـ GroupDocs.Signature لـ .NET؟
نعم يمكنك تنزيل النسخة التجريبية من [هنا](https://releases.groupdocs.com/).

### هل يدعم GroupDocs.Signature لـ .NET تنسيقات ملفات أخرى بالإضافة إلى الصور؟
بالتأكيد! يدعم GroupDocs.Signature تنسيقات متعددة، بما في ذلك PDF وWord وExcel وغيرها.

### هل يمكنني تخصيص مظهر توقيع البيانات الوصفية؟
نعم، يمكنك تخصيص جوانب مثل حجم الخط، واللون، وموضع توقيع البيانات الوصفية.

### أين يمكنني الحصول على الدعم لـ GroupDocs.Signature لـ .NET؟
للحصول على الدعم، قم بزيارة منتدى GroupDocs.Signature [هنا](https://forum.groupdocs.com/c/signature/13).