---
"description": "تعرّف على كيفية إضافة خطوط الاتجاه وتخصيصها في الرسوم البيانية باستخدام Aspose.Slides لـ .NET. يغطي هذا الدليل الشامل خطوط الاتجاه الأسيّة، والخطية، واللوغاريتمية، ومتعددة الحدود، والمتوسطات المتحركة، لتحسين تصور بياناتك."
"linktitle": "خطوط الاتجاه في الرسوم البيانية باستخدام Aspose.Slides لـ .NET"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "خطوط الاتجاه في الرسوم البيانية باستخدام Aspose.Slides لـ .NET"
"url": "/ar/slides/net/master-advanced-chart-customization/trend-lines-in-charts/"
"weight": 12
---

## مقدمة  

تُعد إضافة خطوط الاتجاه إلى المخططات البيانية تقنيةً أساسيةً لتحليل اتجاهات البيانات والتنبؤ بالقيم المستقبلية. باستخدام Aspose.Slides لـ .NET، يمكنك بسهولة إضافة خطوط الاتجاه وتخصيصها إلى مخططات العرض التقديمي، مما يُحسّن من عرض بياناتك. يقدم هذا الدليل شرحًا تفصيليًا لإضافة خطوط الاتجاه إلى أنواع مختلفة من المخططات البيانية في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لـ .NET.  

## المتطلبات الأساسية  

قبل أن نتعمق في التنفيذ، تأكد من أن لديك الإعداد التالي:  

1. Aspose.Slides لـ .NET: قم بتنزيل المكتبة وتثبيتها من [صفحة التحميل](https://releases.aspose.com/slides/net/).  
2. بيئة التطوير: استخدم بيئة التطوير المتكاملة مثل Visual Studio للترميز.  
3. المعرفة الأساسية بلغة C#: مطلوب معرفة ببرمجة C# لمتابعة هذا البرنامج التعليمي.  

## استيراد مساحات الأسماء المطلوبة  

للبدء، قم باستيراد مساحات الأسماء الأساسية إلى مشروعك:  

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## الخطوة 1: إعداد العرض التقديمي  

أولاً، أنشئ عرضًا تقديميًا فارغًا. سيُستخدم هذا كحاوية لمخططك.  

```csharp
string dataDir = "Your/Documents/Directory";

// تأكد من وجود الدليل
if (!System.IO.Directory.Exists(dataDir))
    System.IO.Directory.CreateDirectory(dataDir);

// إنشاء عرض تقديمي جديد
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى شريحة  

الآن، أضف شريحة وأدرج مخططًا عموديًا مجمعًا لتوضيح بياناتك.  

```csharp
// إضافة شريحة فارغة
ISlide slide = presentation.Slides[0];

// إضافة مخطط عمودي مجمع
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
```

## الخطوة 3: ملء بيانات الرسم البياني  

إملأ الرسم البياني ببيانات العينة.  

```csharp
// الوصول إلى مصنف بيانات الرسم البياني الافتراضي
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// تحديث الفئات الافتراضية وقيم السلسلة
workbook.Clear(0);
workbook.GetCell(0, 0, 1).Value = "Category 1";
workbook.GetCell(0, 0, 2).Value = "Category 2";

chart.ChartData.Series[0].DataPoints[0].Value.Data = 4.5;
chart.ChartData.Series[0].DataPoints[1].Value.Data = 2.8;
```

## الخطوة 4: إضافة خطوط الاتجاه  

### خط الاتجاه الأسّي  

```csharp
ITrendline expTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
expTrendLine.DisplayEquation = true;
expTrendLine.DisplayRSquaredValue = true;
```

### خط الاتجاه الخطي  

```csharp
ITrendline linTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
linTrendLine.Format.Line.FillFormat.FillType = FillType.Solid;
linTrendLine.Format.Line.FillFormat.SolidFillColor.Color = Color.Blue;
```

### خط الاتجاه اللوغاريتمي  

```csharp
ITrendline logTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Logarithmic);
logTrendLine.AddTextFrameForOverriding("Logarithmic Trend");
```

### خط اتجاه المتوسط المتحرك  

```csharp
ITrendline movAvgTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.MovingAverage);
movAvgTrendLine.Period = 3;
movAvgTrendLine.TrendlineName = "3-Point Moving Average";
```

### خط الاتجاه متعدد الحدود  

```csharp
ITrendline polyTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Polynomial);
polyTrendLine.Order = 2;
polyTrendLine.Forward = 1;
```

### خط اتجاه الطاقة  

```csharp
ITrendline powerTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Power);
powerTrendLine.DisplayEquation = true;
powerTrendLine.Backward = 1;
```

## الخطوة 5: حفظ العرض التقديمي  

وأخيرًا، احفظ العرض التقديمي مع جميع خطوط الاتجاه المضافة إلى الرسم البياني الخاص بك.  

```csharp
presentation.Save(dataDir + "TrendLinesPresentation.pptx", SaveFormat.Pptx);
```

## خاتمة  

باستخدام Aspose.Slides لـ .NET، تُصبح إضافة خطوط الاتجاه إلى مخططاتك البيانية مهمة سهلة. تتيح لك هذه الميزة عرض اتجاهات البيانات بفعالية وإضافة لمسات احترافية إلى عروضك التقديمية. اتبع الخطوات المذكورة أعلاه لدمج أنواع مختلفة من خطوط الاتجاه والارتقاء بتصور بياناتك.  

## الأسئلة الشائعة  

### هل يمكنني تخصيص مظهر خطوط الاتجاه؟  
نعم، يمكنك تخصيص لون وسمك ونمط خطوط الاتجاه باستخدام `Format.Line` ملكية.  

### هل هناك دعم لأنواع أخرى من الرسوم البيانية؟  
نعم، يدعم Aspose.Slides for .NET أنواعًا مختلفة من المخططات، بما في ذلك المخططات الشريطية والدائرية والخطية.  

### كيف أعرض المعادلات وقيم R-squared؟  
يُمكَِن `DisplayEquation` و `DisplayRSquaredValue` خصائص خط الاتجاه لعرض هذه القيم على الرسم البياني.  

### هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات أخرى؟  
نعم، المكتبة متوافقة مع أي لغة تدعم .NET، بما في ذلك VB.NET وF#.  

### أين يمكنني العثور على مزيد من الوثائق؟  
قم بزيارة [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/) لمزيد من المعلومات.