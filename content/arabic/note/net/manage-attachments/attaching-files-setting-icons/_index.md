---
"description": "تعلّم خطوة بخطوة كيفية إرفاق الملفات وتعيين أيقونات مخصصة في مستندات Microsoft OneNote باستخدام Aspose.Note لـ .NET. حسّن تطبيق .NET الخاص بك بميزات إدارة مستندات وتخصيص سلسة."
"linktitle": "إرفاق ملف وتعيين الرمز في Aspose.Note"
"second_title": "واجهة برمجة تطبيقات Aspose.Note .NET"
"title": "إرفاق الملفات وتعيين الأيقونات في Aspose.Note لـ .NET"
"url": "/ar/note/net/manage-attachments/attaching-files-setting-icons/"
"weight": 10
---

## مقدمة

Aspose.Note for .NET هي مكتبة متقدمة مصممة للمطورين لإنشاء ملفات Microsoft OneNote ومعالجتها وتحويلها برمجيًا. من أبرز ميزات هذه المكتبة قدرتها على إرفاق الملفات بمستندات OneNote وتخصيص أيقوناتها. في هذا الدليل، سنستكشف كيفية الاستفادة من Aspose.Note for .NET لإرفاق الملفات وتعيين أيقونات مخصصة بسلاسة، مما يُثري وظائف مستندات OneNote.

## المتطلبات الأساسية

قبل تنفيذ الحل، تأكد من توفر ما يلي:

- بيئة التطوير: Visual Studio أو بيئة تطوير متكاملة مماثلة مخصصة لتطوير .NET.
- تثبيت المكتبة: قم بتثبيت [Aspose.Note لـ .NET](https://releases.aspose.com/words/net/) مكتبة.
- معرفة البرمجة: فهم أساسيات لغة C#.

## استيراد مساحات الأسماء المطلوبة

أضف هذه المساحات الأسماء إلى مشروعك للحصول على الوظائف الأساسية:

```csharp
using System.IO;
using Aspose.Note;
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
```

فيما يلي تفاصيل التنفيذ خطوة بخطوة.

## الخطوة 1: إنشاء مستند OneNote جديد

قم بتهيئة مستند OneNote جديد باستخدام `Document` فصل.

```csharp
Document doc = new Document();
```

## الخطوة 2: إضافة صفحة جديدة

أضف صفحة إلى المستند لتنظيم ملاحظاتك ومرفقاتك.

```csharp
Aspose.Note.Page page = new Aspose.Note.Page(doc);
```

## الخطوة 3: إعداد مخطط تفصيلي

إنشاء `Outline` الكائن الذي يعمل بمثابة الحاوية للعناصر الموجودة في صفحة OneNote الخاصة بك.

```csharp
Outline outline = new Outline(doc);
```

## الخطوة 4: تهيئة عنصر المخطط التفصيلي

أن `OutlineElement` سوف يحمل المرفق والأيقونة المرتبطة به.

```csharp
OutlineElement outlineElem = new OutlineElement(doc);
```

## الخطوة 5: إرفاق ملف وتحديد الرمز الخاص به

حدد الملف الذي تريد إرفاقه وقم بتوفير أيقونة له.

```csharp
string dataDir = "Your Document Directory";

using (var stream = File.OpenRead(dataDir + "icon.jpg"))
{
    AttachedFile attachedFile = new AttachedFile(doc, dataDir + "attachment.txt", stream, ImageFormat.Jpeg);
    outlineElem.AppendChildLast(attachedFile);
}
```

## الخطوة 6: تجميع هيكل المستند

أضف `OutlineElement` الى `Outline`، و `Outline` الى `Page`.

```csharp
outline.AppendChildLast(outlineElem);
page.AppendChildLast(outline);
```

## الخطوة 7: إضافة الصفحة إلى المستند

وأخيرًا، قم بتضمين الصفحة في مستند OneNote الخاص بك.

```csharp
doc.AppendChildLast(page);
```

## الخطوة 8: حفظ المستند

قم بتصدير مستندك المحدث مع ملف المرفق والأيقونة.

```csharp
dataDir = dataDir + "AttachFileAndSetIcon_out.one";
doc.Save(dataDir);
```

## خاتمة

باتباع الخطوات الموضحة في هذا الدليل، يمكنك بسهولة إرفاق الملفات وتعيين أيقونات مخصصة في مستندات OneNote باستخدام Aspose.Note لـ .NET. تُحسّن هذه الميزة تنظيم المستندات وتجربة المستخدم بشكل كبير، مما يجعل تطبيقاتك أكثر قوة وغنىً بالميزات.

## الأسئلة الشائعة

### هل يمكن إرفاق ملفات متعددة بملاحظة واحدة؟
نعم، يمكنك إرفاق ملفات متعددة عن طريق تكرار عملية الإرفاق لكل ملف.

### ما هي تنسيقات الصور المدعومة للأيقونات؟
يدعم Aspose.Note تنسيقات JPEG، وPNG، وBMP، وGIF لأيقونات المرفقات.

### هل من الممكن إرفاق الملفات بشكل ديناميكي من عناوين URL الخارجية؟
يمكنك تنزيل الملفات باستخدام مكتبات .NET مثل `HttpClient` ثم قم بإرفاقها باستخدام Aspose.Note.

### هل هناك أي قيود على حجم الملف المرفق؟
لا يوجد حد حجم صريح مفروض بواسطة Aspose.Note، ولكن تأكد من أن موارد النظام لديك قادرة على التعامل مع الملفات الكبيرة.

### هل يمكن تغيير حجم الأيقونات قبل تعيينها؟
نعم، يمكنك معالجة صورة الرمز باستخدام .NET `System.Drawing` المكتبة قبل إرفاقها.

لمزيد من المساعدة، استكشف [التوثيق](https://reference.aspose.com/words/net/) أو تواصل معنا [دعم Aspose](https://forum.aspose.com/c/words/8).