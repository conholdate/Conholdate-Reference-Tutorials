---
"description": "เรียนรู้วิธีปรับปรุงแผนภูมิ PowerPoint ของคุณด้วยตัวเลือกมาร์กเกอร์แบบกำหนดเองโดยใช้ Aspose.Slides สำหรับ .NET คู่มือทีละขั้นตอนนี้ครอบคลุมข้อกำหนดเบื้องต้น การสร้างแผนภูมิ การจัดรูปแบบจุดข้อมูล และอื่นๆ อีกมากมาย"
"linktitle": "ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Aspose.Slides .NET"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Aspose.Slides .NET"
"url": "/th/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## การแนะนำ

การนำภาพช่วยสอนมาใช้ในงานนำเสนอเป็นสิ่งสำคัญอย่างยิ่งต่อการสื่อสารที่มีประสิทธิภาพ Aspose.Slides สำหรับ .NET มอบเครื่องมือที่มีประสิทธิภาพสำหรับการสร้างและปรับแต่งแผนภูมิ ช่วยให้นักพัฒนาสามารถปรับปรุงการนำเสนอข้อมูลได้ หนึ่งในฟีเจอร์ที่โดดเด่นคือความสามารถในการใช้ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูล ช่วยให้ปรับแต่งแผนภูมิได้อย่างแม่นยำและสวยงามอย่างมืออาชีพ บทความนี้จะแนะนำคุณทุกขั้นตอนที่จำเป็นเพื่อให้บรรลุผลสำเร็จ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการต่อ โปรดตรวจสอบสิ่งต่อไปนี้:

- Aspose.Slides สำหรับ .NET ติดตั้งแล้ว: ดาวน์โหลดจาก [ที่นี่](https://releases-aspose.com/slides/net/).
- การตั้งค่าพื้นฐาน: ไฟล์การนำเสนอ เช่น "Test.pptx" ในไดเร็กทอรีการทำงานของคุณ
- สภาพแวดล้อมการพัฒนา: Visual Studio หรือเทียบเท่า กำหนดค่าสำหรับ .NET

## การนำเข้าเนมสเปซที่จำเป็น

เพิ่มเนมสเปซที่จำเป็นให้กับโครงการของคุณเพื่อการพัฒนาที่ราบรื่น:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## ขั้นตอนที่ 1: สร้างแผนภูมิในงานนำเสนอของคุณ

เริ่มต้นด้วยการสร้างแผนภูมิเริ่มต้นบนสไลด์แรกของการนำเสนอของคุณ:

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

นี่เพิ่ม `LineWithMarkers` แผนภูมิไปยังสไลด์ของคุณพร้อมขนาดที่ระบุ

## ขั้นตอนที่ 2: ดึงดัชนีแผ่นงานข้อมูลแผนภูมิ

ดัชนีแผ่นงานข้อมูลแผนภูมิเริ่มต้นมีความจำเป็นสำหรับการปรับแต่งเพิ่มเติม:

```csharp
int defaultWorksheetIndex = 0;
```

## ขั้นตอนที่ 3: เข้าถึงสมุดงานข้อมูลแผนภูมิ

ในการจัดการข้อมูลแผนภูมิ ให้ดึงข้อมูลสมุดงานที่เกี่ยวข้อง:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## ขั้นตอนที่ 4: กำหนดค่าชุดแผนภูมิและเพิ่มจุดข้อมูล

ล้างซีรีส์เริ่มต้นและเพิ่มจุดข้อมูลใหม่สำหรับซีรีส์ของคุณ:

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// เพิ่มจุดข้อมูลลงในชุดข้อมูล
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## ขั้นตอนที่ 5: ใช้การเติมรูปภาพกับเครื่องหมายจุดข้อมูล

รูปภาพที่กำหนดเองสามารถทำให้เครื่องหมายข้อมูลดูน่าสนใจได้:

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// ตั้งค่ารูปภาพที่กำหนดเองสำหรับเครื่องหมาย
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## ขั้นตอนที่ 6: ปรับแต่งขนาดเครื่องหมาย

ปรับขนาดของเครื่องหมายเพื่อเพิ่มการมองเห็น:

```csharp
series.Marker.Size = 20;
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอที่อัปเดต

บันทึกการนำเสนอที่กำหนดเองไปยังตำแหน่งที่คุณต้องการ:

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## บทสรุป

Aspose.Slides สำหรับ .NET มอบเครื่องมือสำหรับนักพัฒนาในการสร้างแผนภูมิอย่างมืออาชีพ พร้อมตัวเลือกการปรับแต่งที่หลากหลาย ด้วยการใช้ตัวเลือกตัวทำเครื่องหมายแผนภูมิ คุณสามารถปรับปรุงความสวยงามและความชัดเจนของงานนำเสนอได้อย่างมาก คู่มือทีละขั้นตอนนี้ช่วยให้มั่นใจได้ว่าการปรับแต่งที่ซับซ้อนก็สามารถใช้งานได้ง่าย

## คำถามที่พบบ่อย

### ฉันสามารถใช้รูปแบบภาพใด ๆ เพื่อปรับแต่งเครื่องหมายได้หรือไม่
ใช่ Aspose.Slides รองรับรูปแบบภาพต่างๆ รวมถึง JPEG, PNG และ BMP สำหรับการปรับแต่งเครื่องหมาย

### ฉันจะเปลี่ยนประเภทแผนภูมิหลังจากสร้างได้อย่างไร
หากต้องการเปลี่ยนประเภทแผนภูมิ ให้เข้าถึง `chart.Type` ทรัพย์สินและมอบหมายให้แตกต่างกัน `ChartType`-

### Aspose.Slides สำหรับ .NET เข้ากันได้กับ PowerPoint เวอร์ชันเก่ากว่าหรือไม่
ใช่ รองรับความเข้ากันได้ย้อนหลังกับรูปแบบ PowerPoint รุ่นเก่า ช่วยให้มีความคล่องตัว

### ฉันสามารถอัปเดตข้อมูลแผนภูมิแบบไดนามิกได้หรือไม่
แน่นอน ใช้ `IChartDataWorkbook` เพื่ออัปเดตข้อมูลแผนภูมิตามโปรแกรม

### ฉันสามารถหาแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน
สำรวจ [เอกสาร Aspose.Slides](https://reference.aspose.com/slides/net/) หรือเข้าร่วม [ฟอรัมชุมชน](https://forum.aspose.com/) เพื่อรับการสนับสนุน