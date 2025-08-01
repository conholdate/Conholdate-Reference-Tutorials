---
"description": "تعرّف على كيفية تحسين نماذج PDF بإضافة مربعات تفاعلية مع Aspose.PDF لـ .NET. يغطي هذا الدليل التفصيلي كل شيء، بدءًا من إعداد مستندك ووصولًا إلى حفظه باستخدام خيارات منسدلة سهلة الاستخدام."
"linktitle": "إضافة مربعات المجموعة التفاعلية"
"second_title": "مرجع Aspose.PDF لـ .NET API"
"title": "إضافة مربعات التحرير والسرد التفاعلية"
"url": "/ar/pdf/net/mastering-pdf-forms/add-interactive-combo-boxes/"
"weight": 30
---

## مقدمة

هل رغبتَ يومًا في تحسين ملفات PDF الخاصة بك باستخدام نماذج تفاعلية؟ إحدى أكثر الطرق فعاليةً لتحقيق ذلك هي إضافة مربع خيارات منسّق، والذي يسمح للمستخدمين بالاختيار من قائمة خيارات مُعدّة مسبقًا. هذه الميزة مفيدةٌ بشكل خاص للاستطلاعات والطلبات والاستبيانات. في هذا الدليل، سنستكشف كيفية إضافة مربع خيارات منسّق بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET. في النهاية، ستكون جاهزًا لتخصيص نماذج PDF الخاصة بك بثقة.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من أن لديك ما يلي:

- مكتبة Aspose.PDF لـ .NET: قم بتنزيلها وتثبيتها من [صفحة التحميل](https://releases.aspose.com/pdf/net/).
- بيئة تطوير .NET: يوصى باستخدام Visual Studio.
- المعرفة الأساسية بتطبيقات C# و.NET.
- ترخيص Aspose.PDF: يمكنك استخدام [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) أو وضع المحاكمة.

مع وضع هذه المتطلبات الأساسية في مكانها، فلننتقل إلى الترميز!

## استيراد مساحات الأسماء الضرورية

للعمل مع Aspose.PDF، عليك استيراد مساحات الأسماء المطلوبة. سيسمح لك هذا بالوصول إلى الفئات والأساليب اللازمة لمعالجة ملفات PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

توفر هذه المساحات الاسمية إمكانية الوصول إلى فئات مثل `Document`، `ComboBoxField`، وغيرها من المرافق الأساسية.

## الخطوة 1: إعداد مستند PDF الخاص بك

أولاً، تحتاج إلى مستند PDF للعمل عليه. لننشئ ملف PDF جديدًا ونضيف إليه صفحة فارغة.

```csharp
// حدد المسار لحفظ المستند
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند جديد
Document doc = new Document();
// إضافة صفحة جديدة إلى المستند
doc.Pages.Add();
```

هنا، نقوم بإنشاء `Document` أضف صفحة فارغة. هذه الصفحة بمثابة لوحة لمربعنا المنسدل.

## الخطوة 2: إنشاء حقل المربع المنسدل

الآن، لنُنشئ مربع التحرير والسرد. سيكون هذا المربع هو القائمة المنسدلة التي يتفاعل معها المستخدمون في ملف PDF.

```csharp
// إنشاء كائن حقل ComboBox
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

في هذا الكود، نُحدد موضع وحجم مربع التحرير والسرد باستخدام الإحداثيات. يُحدد المستطيل المنطقة التي سيظهر فيها مربع التحرير والسرد في الصفحة.

## الخطوة 3: إضافة خيارات إلى المربع المنسدل

الآن حان وقت ملء مربع التحرير والسرد بالخيارات. لنُضِف بعض خيارات الألوان.

```csharp
// إضافة خيارات إلى ComboBox
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

ستكون هذه الخيارات الأربعة - الأحمر والأصفر والأخضر والأزرق - متاحة للمستخدمين للاختيار من القائمة المنسدلة.

## الخطوة 4: إضافة المربع المنسدل إلى المستند

بعد إنشاء المربع المنسدل وإضافة الخيارات، نحتاج الآن إلى تضمينه في حقول نموذج المستند.

```csharp
// أضف كائن ComboBox إلى مجموعة حقول النموذج الخاصة بالمستند
doc.Form.Add(combo);
```

يقوم هذا السطر بتضمين المربع المنسدل في ملف PDF، مما يجعله تفاعليًا وجاهزًا لإدخال المستخدم.

## الخطوة 5: حفظ المستند

وأخيرًا، احفظ مستندك لرؤية المربع المنسدل أثناء العمل.

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
// حفظ مستند PDF
doc.Save(dataDir);
Console.WriteLine("\nComboBox field added successfully.\nFile saved at " + dataDir);
```

نحفظ المستند باسم `ComboBox_out.pdf`. تحقق من دليل الإخراج الخاص بك، وستجد ملف PDF مع المربع المنسدل التفاعلي الخاص بك!

## خاتمة

تهانينا! لقد نجحت في إضافة مربع تحرير وسرد إلى ملف PDF باستخدام Aspose.PDF لـ .NET بخمس خطوات بسيطة. تتيح لك هذه الوظيفة الفعّالة إمكانيات عديدة لتخصيص نماذج PDF وتحسينها. بعد أن أتقنت استخدام المربعات التحريرية والسرد، فكّر في استكشاف حقول نماذج أخرى، مثل مربعات الاختيار وحقول النصوص أو إنشاء أزرار اختيار تفاعلية، لإثراء ملفات PDF بشكل أكبر.

## الأسئلة الشائعة

### هل يمكنني إضافة المزيد من الخيارات إلى المربع المنسدل بعد إنشائه؟
نعم يمكنك تعديل `ComboBoxField` كائن لإضافة المزيد من الخيارات قبل حفظ المستند.

### هل من الممكن تغيير حجم المربع المنسدل؟
بالتأكيد! يمكنك تعديل الأبعاد في `ComboBoxField` منشئ لتغيير حجمه حسب الحاجة.

### هل يدعم Aspose.PDF لـ .NET حقول النماذج الأخرى؟
نعم، يدعم Aspose.PDF حقول النماذج المختلفة، بما في ذلك مربعات النص، وأزرار الراديو التفاعلية، ومربعات الاختيار.

### هل يمكنني استخدام هذا الكود مع مستند PDF موجود؟
نعم، يمكنك تحميل ملف PDF موجود وإضافة المربع المنسدل إليه بدلاً من إنشاء ملف جديد.

### هل أحتاج إلى ترخيص لاستخدام Aspose.PDF لـ .NET؟
مع أن Aspose.PDF لـ .NET يقدم نسخة تجريبية مجانية، إلا أن ترخيصًا ساريًا مطلوب للاستفادة الكاملة من الميزات. يمكنك الحصول على [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) للاختبار.