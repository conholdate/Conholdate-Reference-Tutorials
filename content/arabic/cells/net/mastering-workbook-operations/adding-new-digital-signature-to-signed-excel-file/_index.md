---
"description": "تعرّف على كيفية إضافة توقيع رقمي جديد إلى ملف Excel مُوقّع موجود باستخدام Aspose.Cells لـ .NET. يغطي هذا الدليل الشامل جميع المتطلبات الأساسية، مع تعليمات برمجية مفصلة، وأمثلة برمجية."
"linktitle": "إضافة توقيع رقمي جديد إلى ملف Excel الموقّع"
"second_title": "واجهة برمجة تطبيقات معالجة Excel لـ Aspose.Cells .NET"
"title": "إضافة توقيع رقمي جديد إلى ملف Excel الموقّع"
"url": "/ar/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## مقدمة

في ظلّ العالم الرقمي اليوم، أصبح ضمان صحة وسلامة المستندات أكثر أهمية من أي وقت مضى. تُوفّر التوقيعات الرقمية وسيلةً موثوقةً للتحقق من عدم تعديل المستند ومن أنّه صادرٌ من مصدرٍ شرعي. إذا كنت تعمل على ملفات Excel في .NET وتحتاج إلى إضافة توقيع رقمي جديد إلى ملفٍّ مُوقّعٍ مُسبقًا، فهذا الدليل مُصمّمٌ لك! سنشرح لك بالتفصيل عملية إضافة توقيع رقمي إلى ملف Excel مُوقّع مُسبقًا باستخدام Aspose.Cells لـ .NET.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من أن لديك ما يلي:

1. Aspose.Cells لـ .NET: قم بتنزيل Aspose.Cells وتثبيته من [صفحة الإصدار](https://releases.aspose.com/cells/net/).
2. .NET Framework: تأكد من أن جهازك يحتوي على .NET Framework وأنك على دراية بمفاهيم برمجة .NET الأساسية.
3. الشهادة الرقمية: احصل على شهادة رقمية صالحة بصيغة .pfx. للاختبار، يمكنك إنشاء شهادة ذاتية التوقيع.
4. بيئة التطوير: استخدم IDE مثل Visual Studio لكتابة وتنفيذ كود C# الخاص بك.
5. ملف Excel نموذجي: يحتوي على ملف Excel موجود تم توقيعه رقميًا بالفعل، والذي سيكون الهدف لإضافة توقيع جديد.

بعد وضع هذه المتطلبات الأساسية في مكانها، فلننتقل إلى الكود!

## استيراد الحزم الضرورية

في أعلى ملف C# الخاص بك، قم بتضمين مساحات الأسماء التالية للوصول إلى الفئات والطرق المطلوبة:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## الخطوة 1: تحديد الدلائل الخاصة بك

حدد الدلائل الخاصة بملفات المصدر والمكان الذي تريد حفظ ملف الإخراج فيه:

```csharp
// دليل المصدر
string sourceDir = "Your Document Directory"; // استبدل بالدليل الفعلي الخاص بك
// دليل الإخراج
string outputDir = "Your Document Directory"; // استبدل بالدليل الفعلي الخاص بك
```

## الخطوة 2: تحميل المصنف الموقّع الموجود

قم بتحميل مصنف Excel الذي تم توقيعه بالفعل:

```csharp
// قم بتحميل المصنف الذي تم توقيعه رقميًا بالفعل
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## الخطوة 3: إنشاء مجموعة توقيعات رقمية

إنشاء مجموعة لإدارة توقيعاتك الرقمية:

```csharp
// إنشاء مجموعة التوقيعات الرقمية
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## الخطوة 4: تحميل الشهادة الخاصة بك

قم بتحميل الشهادة الرقمية الخاصة بك، والتي سيتم استخدامها لإنشاء التوقيع الجديد:

```csharp
// ملف الشهادة وكلمة المرور الخاصة به
string certFileName = sourceDir + "AsposeDemo.pfx"; // ملف الشهادة الخاص بك
string password = "aspose"; // كلمة مرور الشهادة الخاصة بك

// إنشاء شهادة جديدة
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## الخطوة 5: إنشاء توقيع رقمي جديد

الآن، قم بإنشاء توقيع رقمي جديد وأضفه إلى مجموعتك:

```csharp
// إنشاء توقيع رقمي جديد وإضافته إلى المجموعة
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## الخطوة 6: إضافة مجموعة التوقيعات إلى المصنف

أضف مجموعة التوقيعات الرقمية إلى المصنف:

```csharp
// إضافة مجموعة التوقيعات الرقمية إلى المصنف
workbook.AddDigitalSignature(dsCollection);
```

## الخطوة 7: حفظ المصنف

احفظ المصنف بالتوقيع الرقمي الجديد المضمن:

```csharp
// حفظ المصنف
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## الخطوة 8: تأكيد النجاح

تقديم ملاحظات حول التنفيذ الناجح:

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## خاتمة

تهانينا! لقد نجحت في إضافة توقيع رقمي جديد إلى ملف Excel مُوقّع مسبقًا باستخدام Aspose.Cells لـ .NET. تُعزز هذه العملية أمان مستنداتك وتضمن صحتها وسلامتها.

## الأسئلة الشائعة

### ما هو التوقيع الرقمي؟

التوقيع الرقمي هو مخطط رياضي يتحقق من صحة وسلامة الرسائل أو المستندات الرقمية، ويضمن عدم تغييرها ويؤكد هوية الموقع.

### هل أحتاج إلى شهادة خاصة لإنشاء توقيع رقمي؟

نعم، يلزم الحصول على شهادة رقمية صادرة عن هيئة إصدار شهادات موثوقة (CA) لإنشاء توقيع رقمي صالح.

### هل يمكنني استخدام شهادة موقعة ذاتيًا للاختبار؟

بالتأكيد! يمكنك استخدام شهادة موقعة ذاتيًا لأغراض التطوير والاختبار، ولكن في الإنتاج، يُنصح باستخدام شهادة من جهة اعتماد موثوقة.

### ماذا يحدث إذا حاولت إضافة توقيع إلى مستند غير موقع؟

إذا حاولت إضافة توقيع رقمي إلى مستند غير موقّع بالفعل، فستعمل العملية دون مشاكل، ولكن التوقيع الأصلي لن يكون موجودًا.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Cells؟

للحصول على أدلة تفصيلية ومراجع API، راجع [توثيق Aspose.Cells](https://reference.aspose.com/cells/net/).