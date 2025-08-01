---
"description": "تعرّف على كيفية إضافة توقيع رقمي بسلاسة إلى مستندات Word باستخدام Aspose.Words لـ .NET. يغطي هذا البرنامج التعليمي الشامل كل شيء، بدءًا من إعداد بيئتك وإضافة سطر توقيع، وصولًا إلى حفظ مستنداتك الموقعة والتحقق منها."
"linktitle": "إنشاء وتوقيع سطر توقيع جديد"
"second_title": "واجهة برمجة تطبيقات معالجة المستندات Aspose.Words"
"title": "إنشاء وتوقيع سطر توقيع جديد"
"url": "/ar/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## مقدمة

هل ترغب بإضافة توقيع رقمي إلى مستند وورد؟ مع Aspose.Words لـ .NET، الأمر أسهل مما تظن! سيرشدك هذا البرنامج التعليمي خلال خطوات إعداد بيئتك، وإضافة سطر توقيع، وتوقيع مستندك رقميًا. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل الغوص في الكود، تأكد من أن لديك ما يلي:

1. Aspose.Words لـ .NET - [تحميله هنا](https://releases.aspose.com/words/net/).
2. بيئة تطوير .NET - Visual Studio مثالية لهذه المهمة.
3. المستند للتوقيع - يمكنك إنشاء مستند Word جديد أو استخدام مستند موجود.
4. ملف الشهادة - أ `.pfx` الملف ضروري للتوقيعات الرقمية.
5. صورة سطر التوقيع (اختياري) - يمكنك تضمين ملف صورة للتوقيع.

## استيراد مساحات الأسماء المطلوبة

لاستخدام وظائف Aspose.Words، تحتاج إلى استيراد المساحات التالية:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## الخطوة 1: إعداد دليل المستندات

ابدأ بتحديد مسار مجلد المستندات. هنا يمكنك حفظ مستنداتك واسترجاعها.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // حدد مسار دليل المستند الخاص بك
```

## الخطوة 2: إنشاء مستند جديد

الآن، لنُنشئ مستند Word جديدًا. سيُستخدم هذا المستند كلوحة رسم لسطر توقيعك.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدخال سطر التوقيع

الآن، استخدم `DocumentBuilder` الفئة لإدراج سطر التوقيع في المستند الخاص بك:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## الخطوة 4: حفظ المستند

بعد إدراج سطر التوقيع، احفظ المستند. هذه خطوة أساسية قبل التوقيع.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## الخطوة 5: تكوين خيارات التوقيع

حدّد خيارات عملية التوقيع. يشمل ذلك تحديد مُعرّف سطر التوقيع والصورة الاختيارية التي سيتم عرضها مع التوقيع.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // المسار إلى صورتك
};
```

## الخطوة 6: تحميل الشهادة

قم بتحميل ملف الشهادة المطلوب لتوقيع المستند:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // ضبط اسم الملف وكلمة المرور
```

## الخطوة 7: توقيع الوثيقة

وأخيرًا، قم بتوقيع المستند باستخدام `DigitalSignatureUtil` احفظ المستند الموقّع باسم جديد للرجوع إليه في المستقبل.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## خاتمة

تهانينا! لقد نجحت في إنشاء مستند Word وإضافة سطر توقيع وتوقيعه رقميًا باستخدام Aspose.Words for .NET. تُبسّط هذه الأداة الفعّالة أتمتة المستندات، وتضمن توقيع عقودك ومستنداتك الرسمية وتوثيقها بشكل آمن.

## الأسئلة الشائعة

### هل يمكنني استخدام تنسيقات صور أخرى لسطر التوقيع؟

نعم، يمكنك استخدام تنسيقات الصور المختلفة، بما في ذلك PNG وJPG وBMP.

### هل من الضروري استخدام `.pfx` ملف للحصول على الشهادة؟

نعم، أ `.pfx` الملف هو تنسيق قياسي لتخزين الشهادات والمفاتيح الخاصة للتوقيعات الرقمية.

### هل يمكنني إضافة أسطر توقيع متعددة في مستند واحد؟

بالتأكيد! يمكنك إدراج عدة أسطر توقيع بتكرار خطوة الإدراج حسب الحاجة.

### ماذا لو لم يكن لدي شهادة رقمية؟

سيتعين عليك الحصول على شهادة رقمية من هيئة إصدار شهادات موثوقة أو إنشاء شهادة باستخدام أدوات مثل OpenSSL.

### كيف يمكنني التحقق من التوقيع الرقمي في المستند؟

يمكنك التحقق من التوقيع الرقمي عن طريق فتح المستند الموقع في Word والتحقق من تفاصيل التوقيع للتأكد من صحته وسلامته.