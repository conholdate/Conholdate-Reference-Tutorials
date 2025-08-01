---
"description": "تعرّف على كيفية حفظ مستندات Microsoft OneNote بكفاءة كملفات PDF باستخدام Aspose.Note لـ .NET. يشرح لك هذا الدليل المتطلبات الأساسية اللازمة، ويقدم أسئلة شائعة مفيدة."
"linktitle": "حفظ مستندات OneNote بتنسيق PDF"
"second_title": "واجهة برمجة تطبيقات Aspose.Note .NET"
"title": "حفظ مستندات OneNote بتنسيق PDF باستخدام Aspose.Note لـ .NET"
"url": "/ar/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## مقدمة

في هذا البرنامج التعليمي، سنستكشف كيفية حفظ المستندات بتنسيق PDF باستخدام Aspose.Note لـ .NET. Aspose.Note مكتبة فعّالة تُمكّن المطورين من العمل مع ملفات Microsoft OneNote برمجيًا. سنغطي المتطلبات الأساسية، ونستورد مساحات الأسماء، ونقدم أدلة خطوة بخطوة لحفظ المستندات بتنسيق PDF بتخطيطات صفحات مختلفة.

## المتطلبات الأساسية
1. Visual Studio: تأكد من تثبيته.
2. Aspose.Note لـ .NET: قم بتنزيل المكتبة وتثبيتها.
3. معرفة لغة C#: مطلوب فهم أساسي للغة.

## استيراد مساحات الأسماء الضرورية
قبل المتابعة، قم باستيراد المساحات التالية في الكود الخاص بك:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## الخطوة 1: الحفظ في ملف PDF باستخدام إعدادات صفحة الرسالة
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // تحديث هذا المسار
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
يقوم بتحميل مستند OneNote وحفظه بتنسيق PDF باستخدام إعدادات الصفحة بحجم الحرف.

## الخطوة 2: الحفظ في ملف PDF باستخدام إعدادات الصفحة A4 (لا يوجد حد أقصى للارتفاع)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // تحديث هذا المسار
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
مماثل للخطوة 1 ولكن يستخدم إعدادات الصفحة A4 دون قيود الارتفاع.

## خاتمة
يوضح هذا البرنامج التعليمي بنجاح كيفية تحويل ملفات OneNote إلى صيغة PDF باستخدام Aspose.Note. باستخدام إعدادات صفحات مختلفة، يكتسب المطورون مرونة في إدارة المستندات.

## الأسئلة الشائعة
### هل يمكن لـ Aspose.Note التعامل مع ملفات OneNote المعقدة؟
نعم، فهو يتعامل بفعالية مع الميزات المختلفة لملفات OneNote المعقدة.

### هل Aspose.Note مناسب للمشاريع التجارية؟
نعم، يمكنك استخدامه للتطبيقات التجارية بعد شراء الترخيص.

### هل يقدم Aspose.Note نسخة تجريبية مجانية؟
نعم، تتوفر نسخة تجريبية مجانية للاستكشاف.

### أين يمكنني العثور على وثائق لـ Aspose.Note؟
تتوفر وثائق مفصلة على موقع Aspose المرجعي.

### هل تحتاج إلى مزيد من المساعدة؟
للاستفسارات والحصول على الدعم، راجع منتدى Aspose.Note.