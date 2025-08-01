---
"description": "เรียนรู้วิธีเพิ่มและปรับแต่งเส้นแนวโน้มในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET คู่มือฉบับสมบูรณ์นี้ครอบคลุมเส้นแนวโน้มแบบเลขชี้กำลัง เส้นตรง เส้นลอการิทึม เส้นพหุนาม และเส้นค่าเฉลี่ยเคลื่อนที่ เพื่อเพิ่มประสิทธิภาพการแสดงภาพข้อมูลของคุณ"
"linktitle": "เส้นแนวโน้มในแผนภูมิด้วย Aspose.Slides สำหรับ .NET"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "เส้นแนวโน้มในแผนภูมิด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/slides/net/master-advanced-chart-customization/trend-lines-in-charts/"
"weight": 12
---

## การแนะนำ  

การเพิ่มเส้นแนวโน้มลงในแผนภูมิเป็นเทคนิคสำคัญสำหรับการวิเคราะห์แนวโน้มข้อมูลและการคาดการณ์มูลค่าในอนาคต ด้วย Aspose.Slides สำหรับ .NET คุณสามารถเพิ่มและปรับแต่งเส้นแนวโน้มลงในแผนภูมิงานนำเสนอของคุณได้อย่างราบรื่น ช่วยเพิ่มประสิทธิภาพการแสดงภาพข้อมูล คู่มือนี้ให้คำแนะนำโดยละเอียดเกี่ยวกับการเพิ่มเส้นแนวโน้มลงในแผนภูมิประเภทต่างๆ ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET  

## ข้อกำหนดเบื้องต้น  

ก่อนที่จะเจาะลึกการใช้งาน ให้แน่ใจว่าคุณมีการตั้งค่าต่อไปนี้:  

1. Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [หน้าดาวน์โหลด](https://releases-aspose.com/slides/net/).  
2. สภาพแวดล้อมการพัฒนา: ใช้ IDE เช่น Visual Studio สำหรับการเขียนโค้ด  
3. ความรู้พื้นฐานเกี่ยวกับ C#: จำเป็นต้องมีความคุ้นเคยกับการเขียนโปรแกรม C# เพื่อทำตามบทช่วยสอนนี้  

## การนำเข้าเนมสเปซที่จำเป็น  

ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโครงการของคุณ:  

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ  

ขั้นแรก ให้เริ่มต้นการนำเสนอแบบว่างเปล่า ซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับแผนภูมิของคุณ  

```csharp
string dataDir = "Your/Documents/Directory";

// ตรวจสอบให้แน่ใจว่ามีไดเร็กทอรีอยู่
if (!System.IO.Directory.Exists(dataDir))
    System.IO.Directory.CreateDirectory(dataDir);

// สร้างการนำเสนอใหม่
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิลงในสไลด์  

ตอนนี้ ให้เพิ่มสไลด์และรวมแผนภูมิคอลัมน์แบบกลุ่มเพื่อแสดงข้อมูลของคุณ  

```csharp
// เพิ่มสไลด์เปล่า
ISlide slide = presentation.Slides[0];

// เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
```

## ขั้นตอนที่ 3: การเติมข้อมูลแผนภูมิ  

เติมข้อมูลตัวอย่างลงในแผนภูมิ  

```csharp
// เข้าถึงสมุดงานข้อมูลแผนภูมิเริ่มต้น
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// อัปเดตหมวดหมู่และค่าชุดเริ่มต้น
workbook.Clear(0);
workbook.GetCell(0, 0, 1).Value = "Category 1";
workbook.GetCell(0, 0, 2).Value = "Category 2";

chart.ChartData.Series[0].DataPoints[0].Value.Data = 4.5;
chart.ChartData.Series[0].DataPoints[1].Value.Data = 2.8;
```

## ขั้นตอนที่ 4: การเพิ่มเส้นแนวโน้ม  

### เส้นแนวโน้มแบบเอ็กซ์โพเนนเชียล  

```csharp
ITrendline expTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
expTrendLine.DisplayEquation = true;
expTrendLine.DisplayRSquaredValue = true;
```

### เส้นแนวโน้มเชิงเส้น  

```csharp
ITrendline linTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
linTrendLine.Format.Line.FillFormat.FillType = FillType.Solid;
linTrendLine.Format.Line.FillFormat.SolidFillColor.Color = Color.Blue;
```

### เส้นแนวโน้มลอการิทึม  

```csharp
ITrendline logTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Logarithmic);
logTrendLine.AddTextFrameForOverriding("Logarithmic Trend");
```

### เส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่  

```csharp
ITrendline movAvgTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.MovingAverage);
movAvgTrendLine.Period = 3;
movAvgTrendLine.TrendlineName = "3-Point Moving Average";
```

### เส้นแนวโน้มพหุนาม  

```csharp
ITrendline polyTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Polynomial);
polyTrendLine.Order = 2;
polyTrendLine.Forward = 1;
```

### เส้นแนวโน้มพลัง  

```csharp
ITrendline powerTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Power);
powerTrendLine.DisplayEquation = true;
powerTrendLine.Backward = 1;
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ  

สุดท้าย ให้บันทึกการนำเสนอพร้อมเส้นแนวโน้มทั้งหมดที่เพิ่มลงในแผนภูมิของคุณ  

```csharp
presentation.Save(dataDir + "TrendLinesPresentation.pptx", SaveFormat.Pptx);
```

## บทสรุป  

การใช้ Aspose.Slides สำหรับ .NET จะทำให้การเพิ่มเส้นแนวโน้มลงในแผนภูมิของคุณกลายเป็นเรื่องง่ายดาย ฟีเจอร์นี้ช่วยให้คุณนำเสนอแนวโน้มข้อมูลได้อย่างมีประสิทธิภาพและเพิ่มความเป็นมืออาชีพให้กับงานนำเสนอของคุณ ทำตามขั้นตอนข้างต้นเพื่อรวมเส้นแนวโน้มประเภทต่างๆ เข้าด้วยกันและยกระดับการแสดงข้อมูลของคุณ  

## คำถามที่พบบ่อย  

### ฉันสามารถปรับแต่งลักษณะของเส้นแนวโน้มได้หรือไม่  
ใช่ คุณสามารถปรับแต่งสี ความหนา และรูปแบบของเส้นแนวโน้มได้โดยใช้ `Format.Line` คุณสมบัติ.  

### มีการรองรับประเภทแผนภูมิอื่น ๆ หรือไม่  
ใช่ Aspose.Slides สำหรับ .NET รองรับแผนภูมิประเภทต่างๆ รวมถึงแผนภูมิแท่ง แผนภูมิวงกลม และแผนภูมิเส้น  

### ฉันจะแสดงสมการและค่า R-squared ได้อย่างไร  
เปิดใช้งาน `DisplayEquation` และ `DisplayRSquaredValue` คุณสมบัติสำหรับเส้นแนวโน้มเพื่อแสดงค่าเหล่านี้บนแผนภูมิ  

### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ร่วมกับภาษาอื่นได้หรือไม่  
ใช่ ไลบรารีนี้เข้ากันได้กับภาษาที่รองรับ .NET ทุกภาษา รวมถึง VB.NET และ F#  

### ฉันสามารถหาเอกสารเพิ่มเติมได้จากที่ไหน  
เยี่ยมชม [เอกสาร Aspose.Slides สำหรับ .NET](https://reference.aspose.com/slides/net/) สำหรับข้อมูลเพิ่มเติม