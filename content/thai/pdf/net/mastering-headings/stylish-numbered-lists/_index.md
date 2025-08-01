---
"description": "ค้นพบวิธีสร้างรายการที่มีหมายเลขกำกับอย่างสวยงามในเอกสาร PDF ของคุณด้วย Aspose.PDF สำหรับ .NET คู่มือนี้จะแนะนำขั้นตอนการใช้รูปแบบการกำหนดหมายเลขต่างๆ เช่น ตัวเลขโรมัน"
"linktitle": "รายการหมายเลขที่มีสไตล์โดยใช้ Aspose.PDF สำหรับ .NET"
"second_title": "เอกสารอ้างอิง Aspose.PDF สำหรับ .NET API"
"title": "รายการหมายเลขที่มีสไตล์โดยใช้ Aspose.PDF สำหรับ .NET"
"url": "/th/net/programming-with-headings/stylish-numbered-lists/"
"weight": 10
---

## การแนะนำ

คุณเคยจำเป็นต้องสร้างรายการที่มีโครงสร้างชัดเจนและมีหมายเลขกำกับในเอกสาร PDF ของคุณหรือไม่? ไม่ว่าจะเป็นเอกสารทางกฎหมาย รายงาน หรืองานนำเสนอ รูปแบบการกำหนดหมายเลขที่มีประสิทธิภาพเป็นสิ่งสำคัญอย่างยิ่งในการจัดระเบียบเนื้อหาของคุณ ด้วย Aspose.PDF สำหรับ .NET คุณสามารถนำรูปแบบการกำหนดหมายเลขที่หลากหลายมาใช้กับหัวเรื่อง PDF ของคุณได้อย่างง่ายดาย ส่งผลให้เอกสารของคุณดูสวยงามและเป็นมืออาชีพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มเขียนโค้ด ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อม:

1. Aspose.PDF สำหรับ .NET: ดาวน์โหลดเวอร์ชันล่าสุดจาก [ที่นี่](https://releases-aspose.com/pdf/net/).
2. สภาพแวดล้อมการพัฒนา: คุณจะต้องมี Visual Studio หรือ IDE ที่เข้ากันได้กับ .NET
3. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework 4.0 ขึ้นไป
4. ใบอนุญาต: คุณสามารถใช้ใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/) หรือสำรวจ [ทดลองใช้ฟรี](https://releases.aspose.com/) ตัวเลือก

## การนำเข้าแพ็คเกจที่จำเป็น

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโครงการของคุณ:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 1: การตั้งค่าเอกสาร

เริ่มต้นด้วยการสร้างเอกสาร PDF ใหม่และกำหนดเค้าโครง รวมถึงขนาดหน้าและระยะขอบ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// ตั้งค่าขนาดหน้าและระยะขอบ
pdfDoc.PageInfo.Width = 612.0; // 8.5 นิ้ว
pdfDoc.PageInfo.Height = 792.0; // 11 นิ้ว
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo(72, 72, 72, 72); // ระยะขอบ 1 นิ้ว
```

การตั้งค่านี้ทำให้เอกสารของคุณมีขนาด Letter มาตรฐานโดยมีระยะขอบด้านละ 1 นิ้ว

## ขั้นตอนที่ 2: การเพิ่มหน้าลงใน PDF

ต่อไปเราจะเพิ่มหน้าว่างลงในเอกสาร PDF ซึ่งเราจะใช้รูปแบบการกำหนดหมายเลขในภายหลัง

```csharp
// เพิ่มหน้าใหม่ลงในเอกสาร PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo = pdfDoc.PageInfo; // ใช้การตั้งค่าเดียวกันกับเอกสาร
```

## ขั้นตอนที่ 3: การสร้างกล่องลอย

FloatingBox ช่วยให้คุณสามารถวางเนื้อหาโดยไม่ขึ้นกับการไหลของหน้า ทำให้คุณควบคุมเค้าโครงของคุณได้ดียิ่งขึ้น

```csharp
// สร้าง FloatingBox สำหรับเนื้อหาที่มีโครงสร้าง
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox
{
    Margin = pdfPage.PageInfo.Margin
};
pdfPage.Paragraphs.Add(floatBox);
```

## ขั้นตอนที่ 4: การเพิ่มหัวข้อด้วยตัวเลขโรมัน

ตอนนี้เรามาเพิ่มหัวข้อแรกโดยใช้เลขโรมันตัวพิมพ์เล็กกัน

```csharp
// สร้างหัวข้อแรกด้วยตัวเลขโรมัน
Aspose.Pdf.Heading heading1 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 1,
    Text = "List 1",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading1);
```

## ขั้นตอนที่ 5: การเพิ่มหัวข้อที่สองด้วยหมายเลขเริ่มต้นที่กำหนดเอง

ต่อไปเราจะเพิ่มหัวข้อที่สองโดยเริ่มจากเลขโรมัน 13

```csharp
// สร้างหัวข้อที่สองโดยเริ่มจากเลขโรมัน 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 13,
    Text = "List 2",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading2);
```

## ขั้นตอนที่ 6: การเพิ่มหัวข้อพร้อมการนับตามตัวอักษร

เพื่อความหลากหลาย เราจะเพิ่มหัวข้อที่สามโดยใช้การนับตัวอักษรแบบตัวพิมพ์เล็ก

```csharp
// สร้างหัวข้อด้วยการกำหนดหมายเลขตามตัวอักษร
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2)
{
    IsInList = true,
    StartNumber = 1,
    Text = "The value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed",
    Style = NumberingStyle.LettersLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading3);
```

## ขั้นตอนที่ 7: บันทึก PDF

สุดท้ายนี้เรามาบันทึกไฟล์ PDF ลงในไดเร็กทอรีที่คุณต้องการกัน

```csharp
// บันทึกเอกสาร PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine($"\nNumber style applied successfully in headings.\nFile saved at {dataDir}");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้นำรูปแบบการกำหนดหมายเลขที่หลากหลาย ทั้งเลขโรมันและตัวอักษร มาใช้กับหัวข้อในไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว ความยืดหยุ่นของ Aspose.PDF ช่วยให้คุณควบคุมเค้าโครงหน้า รูปแบบการกำหนดหมายเลข และการจัดวางเนื้อหา ช่วยให้คุณสร้างเอกสาร PDF ที่มีการจัดระบบอย่างดีและเป็นมืออาชีพ

## คำถามที่พบบ่อย

### ฉันสามารถใช้รูปแบบตัวเลขที่แตกต่างกันกับเอกสาร PDF เดียวกันได้หรือไม่  
ใช่ คุณสามารถผสมผสานรูปแบบการนับเลขที่แตกต่างกัน เช่น เลขโรมัน เลขอาหรับ และเลขตัวอักษรภายในเอกสารเดียวกันได้

### ฉันจะกำหนดหมายเลขเริ่มต้นสำหรับหัวเรื่องได้อย่างไร  
คุณสามารถตั้งค่าหมายเลขเริ่มต้นสำหรับหัวข้อใดๆ ได้โดยใช้ `StartNumber` คุณสมบัติ.

### มีวิธีรีเซ็ตลำดับการนับเลขหรือไม่  
ใช่ คุณสามารถรีเซ็ตการนับเลขได้โดยการปรับ `StartNumber` คุณสมบัติของแต่ละหัวข้อ

### ฉันสามารถใช้รูปแบบตัวหนาหรือตัวเอียงกับหัวเรื่องนอกเหนือจากการกำหนดหมายเลขได้หรือไม่  
แน่นอน! คุณสามารถปรับแต่งรูปแบบหัวเรื่องได้โดยการแก้ไขคุณสมบัติต่างๆ เช่น แบบอักษร ขนาด ตัวหนา และตัวเอียง โดยใช้ `TextState` วัตถุ.

### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.PDF ได้อย่างไร  
คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อทดสอบ Aspose.PDF โดยไม่มีข้อจำกัด