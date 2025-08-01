---
"description": "تعرّف على كيفية تحسين مخططات PowerPoint الخاصة بك باستخدام خيارات علامات مخصصة باستخدام Aspose.Slides لـ .NET. يغطي هذا الدليل التفصيلي المتطلبات الأساسية، وإنشاء المخططات، وتنسيق نقاط البيانات، والمزيد."
"linktitle": "خيارات علامة الرسم البياني على نقطة البيانات في Aspose.Slides .NET"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "خيارات علامة الرسم البياني على نقطة البيانات في Aspose.Slides .NET"
"url": "/ar/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## مقدمة

يُعدّ دمج الوسائل البصرية في العروض التقديمية أمرًا أساسيًا للتواصل الفعال. يوفر Aspose.Slides for .NET أدوات فعّالة لإنشاء المخططات وتخصيصها، مما يُمكّن المطورين من تحسين عروض البيانات التقديمية. ومن أبرز ميزاته إمكانية استخدام خيارات تحديد المخططات على نقاط البيانات، مما يتيح تخصيصًا دقيقًا للحصول على مخططات ذات مظهر احترافي. ستوضح لك هذه المقالة كل خطوة لتحقيق ذلك.

## المتطلبات الأساسية

قبل المتابعة، تأكد مما يلي:

- تم تثبيت Aspose.Slides لـ .NET: قم بتنزيله من [هنا](https://releases.aspose.com/slides/net/).
- الإعداد الأساسي: ملف عرض تقديمي، مثل "Test.pptx"، في دليل العمل الخاص بك.
- بيئة التطوير: Visual Studio أو ما يعادله، مهيأة لـ .NET.

## استيراد مساحات الأسماء المطلوبة

أضف مساحات الأسماء الضرورية إلى مشروعك لتحقيق التطوير السلس:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## الخطوة 1: إنشاء مخطط في العرض التقديمي الخاص بك

ابدأ بإنشاء مخطط افتراضي على الشريحة الأولى من العرض التقديمي الخاص بك:

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

وهذا يضيف `LineWithMarkers` قم بإضافة مخطط إلى الشريحة الخاصة بك بالأبعاد المحددة.

## الخطوة 2: استرداد فهرس ورقة عمل بيانات الرسم البياني

يعد فهرس ورقة عمل بيانات الرسم البياني الافتراضي ضروريًا لمزيد من التخصيص:

```csharp
int defaultWorksheetIndex = 0;
```

## الخطوة 3: الوصول إلى مصنف بيانات الرسم البياني

للتعامل مع بيانات الرسم البياني، قم باسترداد المصنف المرتبط:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## الخطوة 4: تكوين سلسلة المخططات وإضافة نقاط البيانات

مسح السلسلة الافتراضية وإضافة نقاط بيانات جديدة لسلسلتك:

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// إضافة نقاط البيانات إلى السلسلة
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## الخطوة 5: تطبيق تعبئة الصور على علامات نقاط البيانات

يمكن للصور المخصصة أن تجعل علامات البيانات جذابة بصريًا:

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// تعيين صور مخصصة للعلامات
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## الخطوة 6: تخصيص حجم العلامة

تعديل حجم العلامات لتحسين الرؤية:

```csharp
series.Marker.Size = 20;
```

## الخطوة 7: حفظ العرض التقديمي المحدث

احفظ العرض التقديمي المخصص في الموقع المطلوب:

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## خاتمة

يُزوّد Aspose.Slides for .NET المطورين بأدوات لإنشاء مخططات بيانية احترافية بخيارات تخصيص غنية. باستخدام خيارات علامات المخططات، يمكنك تحسين مظهر عروضك التقديمية ووضوحها بشكل ملحوظ. يضمن هذا الدليل التفصيلي سهولة تنفيذ حتى التخصيصات المعقدة.

## الأسئلة الشائعة

### هل يمكنني استخدام أي تنسيق صورة لتخصيص العلامة؟
نعم، يدعم Aspose.Slides تنسيقات الصور المختلفة، بما في ذلك JPEG، وPNG، وBMP، لتخصيص العلامة.

### كيف يمكنني تغيير نوع الرسم البياني بعد إنشائه؟
لتغيير نوع الرسم البياني، قم بالوصول إلى `chart.Type` الممتلكات وتعيين مختلفة `ChartType`.

### هل Aspose.Slides for .NET متوافق مع إصدارات PowerPoint القديمة؟
نعم، فهو يدعم التوافق مع تنسيقات PowerPoint القديمة، مما يضمن التنوع.

### هل يمكنني تحديث بيانات الرسم البياني بشكل ديناميكي؟
بالتأكيد. استخدم `IChartDataWorkbook` لتحديث بيانات الرسم البياني برمجيًا.

### أين يمكنني العثور على المزيد من الموارد؟
استكشف [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/) أو انضم إلى [المنتديات المجتمعية](https://forum.aspose.com/) للحصول على الدعم.