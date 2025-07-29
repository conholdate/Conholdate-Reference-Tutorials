---
"description": "أطلق العنان لقوة أتمتة Excel مع هذا الدليل الشامل لنقل نماذج مستخدم VBA ووحدات الماكرو بين المصنفات باستخدام Aspose.Cells لـ .NET. مثالي للمبتدئين والمطورين ذوي الخبرة."
"linktitle": "نقل نماذج VBA ووحدات الماكرو بين مصنفات Excel"
"second_title": "واجهة برمجة تطبيقات معالجة Excel لـ Aspose.Cells .NET"
"title": "نقل نماذج VBA ووحدات الماكرو بين مصنفات Excel"
"url": "/ar/cells/net/mastering-workbook-vba-project/transfer-vba-user-form-and-macro/"
"weight": 11
---

## مقدمة

أهلاً بكم في دليلكم الشامل لتحسين تجربة استخدام Excel باستخدام وحدات ماكرو VBA ونماذج المستخدم! في هذا البرنامج التعليمي، سنستكشف كيفية نقل مُصمم نماذج المستخدم VBA Macro UserForm من مصنف إلى آخر باستخدام مكتبة Aspose.Cells for .NET القوية. سواءً كنتَ مطورًا خبيرًا أو مبتدئًا، سيزودك هذا الدليل التفصيلي بالمعرفة اللازمة للتعامل مع ملفات Excel برمجيًا. هل أنت مستعد للبدء؟ هيا بنا!

## المتطلبات الأساسية
قبل أن ننتقل إلى البرمجة، دعنا نتأكد من أن لديك كل ما تحتاجه:

1. بيئة تطوير C#: بيئة عمل لتطوير C#، مع التوصية بشدة باستخدام Visual Studio.
2. مكتبة Aspose.Cells لـ .NET: تأكد من دمج مكتبة Aspose.Cells في مشروعك. يمكنك بسهولة [قم بتحميله هنا](https://releases.aspose.com/cells/net/).
3. المعرفة الأساسية بـ VBA ووحدات الماكرو في Excel: إن المعرفة بـ VBA وكيفية عمل وحدات الماكرو في Excel سوف تعزز فهمك لهذا البرنامج التعليمي.
4. ملف Excel يحتوي على نموذج مستخدم: قم بإنشاء مصنف Excel أو الحصول عليه يحتوي على نموذج مستخدم (يفضل مع تمكين وحدات الماكرو، مثل `.xlsm` الملفات).

## استيراد الحزم المطلوبة
للاستفادة من الوظائف التي يوفرها Aspose.Cells، قم بتضمين المساحات التالية في أعلى ملف C# الخاص بك:

```csharp
using System;
using Aspose.Cells;
using Aspose.Cells.Vba;
```

ستتيح لك هذه المساحات الاسمية الوصول إلى الأدوات القوية المضمنة داخل مكتبة Aspose.Cells.

## الخطوة 1: تحديد دليل المصدر والإخراج
أولاً، قم بتحديد مواقع ملفاتك:

```csharp
// تحديد أدلة المصدر والإخراج
string sourceDir = @"Your\Source\Directory\";
string outputDir = @"Your\Output\Directory\";
```

استبدل مسارات العنصر النائب بالدلائل الفعلية التي يتم تخزين ملفاتك فيها.

## الخطوة 2: إنشاء مصنف هدف فارغ
بعد ذلك، قم بإنشاء مصنف جديد حيث ستنسخ نموذج المستخدم والماكرو:

```csharp
// إنشاء مصنف هدف فارغ
Workbook target = new Workbook();
```

يؤدي هذا إلى تهيئة مصنف فارغ، ليكون بمثابة لوحة الرسم الخاصة بك لنقل البيانات القادم.

## الخطوة 3: تحميل مصنف القالب الخاص بك
قم بتحميل المصنف الذي يحتوي على نموذج المستخدم والماكرو الخاص بك:

```csharp
// قم بتحميل ملف Excel الذي يحتوي على نموذج مستخدم VBA-Macro Designer
Workbook templateFile = new Workbook(sourceDir + "sampleDesignerForm.xlsm");
```

يُعدِّل `"sampleDesignerForm.xlsm"` إلى اسم ملفك الفعلي.

## الخطوة 4: نسخ أوراق العمل إلى المصنف المستهدف
الآن، دعنا ننسخ أوراق العمل من القالب إلى المصنف المستهدف:

```csharp
// نسخ جميع أوراق عمل القالب إلى المصنف المستهدف
foreach (Worksheet ws in templateFile.Worksheets)
{
    if (ws.Type == SheetType.Worksheet)
    {
        Worksheet s = target.Worksheets.Add(ws.Name);
        s.Copy(ws);
        // أضف رسالة في الخلية A2 من ورقة العمل المستهدفة
        s.Cells["A2"].PutValue("VBA Macro and User Form copied from template to target.");
    }
}
```

يتكرر هذا الكود في كل ورقة عمل في القالب وينسخها إلى المصنف المستهدف، مما يضمن نقل جميع بياناتك بسلاسة.

## الخطوة 5: نسخ وحدات الماكرو VBA من القالب
بعد ذلك، سنقوم بنسخ وحدات الماكرو VBA، بما في ذلك وحدات UserForm Designer، إلى المصنف الجديد:

```csharp
// نسخ نموذج مستخدم VBA-Macro Designer من القالب إلى الهدف
foreach (VbaModule vbaItem in templateFile.VbaProject.Modules)
{
    if (vbaItem.Name == "ThisWorkbook")
    {
        // نسخ كود وحدة ThisWorkbook
        target.VbaProject.Modules["ThisWorkbook"].Codes = vbaItem.Codes;
    }
    else
    {
        // نسخ كود وبيانات الوحدات النمطية الأخرى
        int vbaMod = target.VbaProject.Modules.Add(vbaItem.Type, vbaItem.Name);
        target.VbaProject.Modules[vbaMod].Codes = vbaItem.Codes;

        if (vbaItem.Type == VbaModuleType.Designer)
        {
            // احصل على مساحة تخزين مصمم نموذج المستخدم
            byte[] designerStorage = templateFile.VbaProject.Modules.GetDesignerStorage(vbaItem.Name);
            // إضافة وحدة تخزين المصمم إلى مشروع Vba المستهدف
            target.VbaProject.Modules.AddDesignerStorage(vbaItem.Name, designerStorage);
        }
    }
}
```

يضمن هذا الكود أنه ليس فقط يتم نسخ الكود ولكن أيضًا تصميم نموذج المستخدم، مما يحافظ على وظائف وحدات الماكرو الخاصة بك.

## الخطوة 6: حفظ المصنف المستهدف
بعد الانتهاء من عملية النسخ، احفظ المصنف الجديد الخاص بك:

```csharp
// حفظ المصنف المستهدف
target.Save(outputDir + "outputDesignerForm.xlsm", SaveFormat.Xlsm);
```

عدّل اسم ملف الإخراج حسب الحاجة. تُنشئ هذه الخطوة مصنفًا مُخصّصًا مليئًا بوحدات الماكرو ونماذج المستخدم.

## الخطوة 7: تأكيد النجاح
وأخيرًا، اطبع رسالة النجاح على وحدة التحكم:

```csharp
Console.WriteLine("CopyVBAMacroUserFormDesignerStorageToWorkbook executed successfully.\r\n");
```

هذا السطر البسيط يطمئنك إلى أن عمليتك سارت بسلاسة - وهو تأكيد أساسي على عملك الجاد!

## خاتمة
تهانينا! لقد نجحت في تعلم كيفية نسخ مُصمم نماذج مستخدم ماكرو VBA من مصنف إلى آخر باستخدام Aspose.Cells لـ .NET. قد يبدو الأمر صعبًا في البداية، لكن الممارسة ستُتقن التعامل مع المصنفات. تذكر أن البرمجة تعتمد على التجربة، لذا لا تتردد في استكشاف الوظائف المختلفة في ملفات Excel. إذا كانت لديك أي أسئلة أو كنت بحاجة إلى مساعدة، فإن منتديات Aspose ووثائقها مصادر ممتازة للدعم.

## الأسئلة الشائعة

### ما هي إصدارات Excel التي يدعمها Aspose.Cells؟
يدعم Aspose.Cells تنسيقات Excel المختلفة، بما في ذلك XLSX، وXLSM، وCSV، والمزيد.

### هل يمكنني استخدام Aspose.Cells مجانًا؟
نعم! يمكنك البدء بفترة تجريبية مجانية لتقييم المكتبة: [نسخة تجريبية مجانية](https://releases.aspose.com/).

### هل أحتاج إلى Visual Studio لتشغيل هذا الكود؟
على الرغم من أن Visual Studio يوصى به لميزاته سهلة الاستخدام، فإن أي بيئة تطوير متكاملة لـ C# تدعم تطوير .NET ستكون كافية.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
يمكنك استكشاف [توثيق Aspose.Cells](https://reference.aspose.com/cells/net/) لمزيد من الأمثلة والشروحات المتعمقة.

### كيف يمكنني حل المشكلات أثناء استخدام Aspose.Cells؟
ينبغي عليك زيارة [منتدى دعم Aspose](https://forum.aspose.com/c/cells/9) للحصول على المساعدة من المجتمع وموظفي دعم Aspose.