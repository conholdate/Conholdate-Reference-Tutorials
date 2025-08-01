---
"description": "تعرّف على كيفية الاستفادة من فئة Aspose.Tasks لـ .NET لتصفية مهام المشروع بناءً على شروط متعددة، وذلك من خلال الجمع بين معايير مثل مهام التلخيص والسمات غير الصفرية."
"linktitle": "تصفية المهام والعمليات في Aspose.Tasks"
"second_title": "واجهة برمجة تطبيقات Aspose.Tasks .NET"
"title": "تصفية المهام والعمليات في Aspose.Tasks"
"url": "/ar/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## مقدمة

في هذا البرنامج التعليمي، سوف نستكشف كيفية إجراء تصفية متقدمة لمهام المشروع في Aspose.Tasks لـ .NET من خلال الاستفادة من `Util.And` تتيح هذه الميزة القوية للمطورين تصفية المهام استنادًا إلى معايير متعددة بكفاءة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. المعرفة الأساسية ببرمجة C#.
2. تم تثبيت Aspose.Tasks لـ .NET. إذا لم تقم بذلك بعد، يمكنك تنزيله من [هذا الرابط](https://releases.aspose.com/tasks/net/).
3. بيئة تطوير متكاملة (IDE) مثل Visual Studio لكتابة وتشغيل التعليمات البرمجية.

## استيراد مساحات الأسماء

للبدء، عليك استيراد مساحات الأسماء المطلوبة إلى مشروع C# الخاص بك. سيسمح لك هذا بالوصول إلى وظائف Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## الخطوة 1: تهيئة المشروع وجمع المهام

أولاً، قم بتشغيل مشروع Aspose.Tasks واجمع جميع المهام فيه. لأغراض التوضيح، سنفترض وجود ملف مشروع باسم `Project2.mpp`.

```csharp
// المسار إلى دليل المستندات
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// جمع كل مهام الطفل
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## الخطوة 2: تحديد شروط التصفية

في هذه الخطوة، سنحدد شروط تصفية المهام. في مثالنا، سننشئ شرطين: أحدهما لتصفية المهام المختصرة، والآخر لضمان عدم وجود أي مهام فارغة.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## الخطوة 3: دمج الشروط مع عملية AND

الخطوة التالية هي الجمع بين هذه الشروط باستخدام `Util.And` يسمح لنا هذا بإنشاء شرط مركب يفرض كلا المعيارين.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## الخطوة 4: تطبيق مهام الشرط والتصفية المجمعة

الآن، دعنا نطبق الشرط المدمج على المهام المجمعة لتصفية المهام المحددة التي تلبي كلا الشرطين.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## الخطوة 5: إخراج المهام المفلترة

أخيرًا، سنراجع مهامنا المُفلترة ونُخرِج التفاصيل ذات الصلة. سيساعدنا هذا على فهم المهام التي تُلبي معاييرنا.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## خاتمة

في هذا البرنامج التعليمي، أوضحنا كيفية إجراء عمليات التصفية المتقدمة في Aspose.Tasks لـ .NET باستخدام `Util.And` من خلال الجمع بين عدة شروط، يمكننا تصفية المهام بفعالية، وبالتالي تعزيز فائدة تطبيقات إدارة المشاريع لدينا.

## الأسئلة الشائعة

### ما هو Aspose.Tasks لـ .NET؟

Aspose.Tasks for .NET عبارة عن واجهة برمجة تطبيقات شاملة مصممة للمطورين للتعامل مع ملفات Microsoft Project برمجيًا داخل تطبيقات .NET.

### هل يمكنني الجمع بين أكثر من شرطين باستخدام Util.And؟

نعم! `Util.And` تتيح لك الفئة دمج شروط متعددة، مما يتيح منطق تصفية معقدًا مصممًا خصيصًا لتلبية احتياجاتك.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟

نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هذا الرابط](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks؟

الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/tasks/net/).

### كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟

يتوفر الدعم من خلال منتدى مجتمع Aspose.Tasks، والذي يمكن الوصول إليه [هنا](https://forum.aspose.com/c/tasks/15).