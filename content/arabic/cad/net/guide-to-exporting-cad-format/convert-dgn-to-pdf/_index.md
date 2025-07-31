---
"description": "تعلّم كيفية تحويل ملفات DGN إلى PDF بسهولة باستخدام مكتبة Aspose.CAD القوية لـ .NET. هذا الدليل المفصل مُصمّم للمطورين من جميع المستويات."
"linktitle": "تحويل DGN إلى PDF في Aspose.CAD لـ .NET"
"second_title": "Aspose.CAD .NET - تنسيق ملفات CAD وBIM"
"title": "تحويل DGN إلى PDF في Aspose.CAD لـ .NET"
"url": "/ar/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## مقدمة

قد يكون التعامل مع ملفات CAD أمرًا صعبًا، ولكن مع Aspose.CAD لـ .NET، يمكن للمطورين التعامل مع مختلف تنسيقات CAD وتحويلها بسهولة. من الاحتياجات الشائعة تحويل ملفات DGN إلى ملفات PDF، وهو ما سنتناوله خطوة بخطوة في هذا البرنامج التعليمي.

## المتطلبات الأساسية

للمتابعة، تأكد من أن لديك ما يلي:

- الكفاءة الأساسية في لغة البرمجة C# وإطار عمل .NET.
- تم تثبيت مكتبة Aspose.CAD لـ .NET. يمكنك تنزيلها. [هنا](https://releases.aspose.com/cad/net/).
- نموذج لملف DGN (على سبيل المثال، Nikon_D90_Camera.dgn). 

## الخطوة 1: استيراد مساحات الأسماء المطلوبة

ابدأ باستيراد المساحات الأسماء ذات الصلة في مشروع C# الخاص بك:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## الخطوة 2: تحميل ملف DGN

حدد الدليل لملف DGN الخاص بك وقم بتحميله باستخدام الكود التالي:

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // سيتم إجراء المعالجة الإضافية هنا...
}
```

## الخطوة 3: تكوين خيارات التنقيح

بعد ذلك، قم بإعداد خيارات التحويل إلى بيانات نقطية لتحديد كيفية عرض DGN في ملف PDF:

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // اضبط العرض حسب الحاجة
    PageHeight = 300, // ضبط الارتفاع حسب الحاجة
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## الخطوة 4: إنشاء خيارات PDF

قم بتحديد خيارات PDF، ودمج إعدادات التحويل إلى بيانات نقطية التي تم تكوينها مسبقًا:

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## الخطوة 5: احفظ DGN بصيغة PDF

أخيرًا، احفظ ملف DGN بتنسيق PDF باستخدام الخيارات التي قمت بتكوينها:

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## خاتمة

تهانينا! لقد نجحت في تحويل ملف DGN إلى PDF باستخدام Aspose.CAD لـ .NET. أرشدك هذا البرنامج التعليمي البسيط إلى كيفية تحميل ملف DGN، وضبط خيارات التصغير، وحفظ الناتج كملف PDF.

## الأسئلة الشائعة

### هل أحتاج إلى معرفة مسبقة ببرنامج CAD لاستخدام Aspose.CAD؟  
بالتأكيد! صُمم Aspose.CAD لتبسيط مهام CAD المعقدة، مما يجعله متاحًا لجميع المطورين، بغض النظر عن خبرتهم في CAD.

### أين يمكنني العثور على المزيد من الموارد والوثائق الخاصة بـ Aspose.CAD؟  
يمكنك استكشاف الأدلة الشاملة والأمثلة في [وثائق Aspose.CAD](https://reference.aspose.com/cad/net/).

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.CAD؟  
نعم، يمكن الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.CAD؟  
يمكنك طلب تراخيص مؤقتة [هنا](https://purchase.conholdate.com/temporary-license/).

### هل تحتاج إلى مساعدة أو لديك أسئلة؟  
انضم إلى المحادثة في [منتدى Aspose.CAD](https://forum.aspose.com/c/cad/19) للحصول على الدعم المجتمعي والاستفسارات.