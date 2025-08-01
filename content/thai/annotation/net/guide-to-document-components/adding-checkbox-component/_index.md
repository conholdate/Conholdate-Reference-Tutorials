---
"description": "ค้นพบวิธีเพิ่มคุณค่าให้กับเอกสาร PDF ของคุณด้วยการเพิ่มส่วนประกอบกล่องกาเครื่องหมายแบบโต้ตอบโดยใช้ GroupDocs.Annotation สำหรับ .NET SDK บทช่วยสอนที่ครอบคลุมนี้ให้คำแนะนำทีละขั้นตอนอย่างชัดเจน"
"linktitle": "การเพิ่มส่วนประกอบกล่องกาเครื่องหมายลงในเอกสาร PDF"
"second_title": "API ของ GroupDocs.Annotation .NET"
"title": "การเพิ่มส่วนประกอบกล่องกาเครื่องหมายลงในเอกสาร PDF"
"url": "/th/annotation/net/guide-to-document-components/adding-checkbox-component/"
"weight": 11
---

## การแนะนำ

ในบทช่วยสอนนี้ เราจะแนะนำขั้นตอนการเพิ่มส่วนประกอบ Checkbox ลงในเอกสาร PDF โดยใช้ GroupDocs.Annotation สำหรับ .NET SDK ฟีเจอร์นี้ช่วยให้คุณปรับปรุงเอกสาร PDF ของคุณด้วยองค์ประกอบแบบอินเทอร์แอคทีฟ ทำให้เอกสารน่าสนใจยิ่งขึ้นสำหรับผู้ใช้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. GroupDocs.Annotation สำหรับ .NET SDK: ดาวน์โหลดจาก [ที่นี่](https://releases-groupdocs.com/annotation/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ

## ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น

ขั้นแรก ให้รวมเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Annotation.Models;
using GroupDocs.Annotation.Models.AnnotationModels;
using GroupDocs.Annotation.Models.FormatSpecificComponents.Pdf;
using GroupDocs.Annotation.Options;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางเอาต์พุต

ระบุตำแหน่งที่จะบันทึกเอกสาร PDF ที่แก้ไข:

```csharp
string outputPath = Path.Combine("Your Document Directory", "result" + Path.GetExtension("input.pdf"));
```

## ขั้นตอนที่ 3: เริ่มต้น Annotator

สร้างอินสแตนซ์ของ `Annotator` คลาสที่มีเส้นทางไปยังเอกสาร PDF อินพุตของคุณ:

```csharp
using (Annotator annotator = new Annotator("input.pdf"))
```

## ขั้นตอนที่ 4: สร้างส่วนประกอบกล่องกาเครื่องหมาย

ตอนนี้มาสร้างและปรับแต่งส่วนประกอบกล่องกาเครื่องหมายกัน:

```csharp
CheckBoxComponent checkBox = new CheckBoxComponent
{
    Checked = true,
    Box = new Rectangle(100, 100, 100, 100), // กำหนดตำแหน่งและขนาด
    PenColor = 65535, // ตั้งค่าสี (ในกรณีนี้คือสีเหลือง)
    Style = BoxStyle.Star, // เลือกสไตล์สำหรับกล่องกาเครื่องหมาย
    Replies = new List<Reply>
    {
        new Reply { Comment = "First comment", RepliedOn = DateTime.Now },
        new Reply { Comment = "Second comment", RepliedOn = DateTime.Now }
    }
};
```

## ขั้นตอนที่ 5: เพิ่มกล่องกาเครื่องหมายลงในเอกสาร

เพิ่มส่วนประกอบกล่องกาเครื่องหมายที่สร้างขึ้นลงใน PDF:

```csharp
annotator.Add(checkBox);
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข

บันทึกเอกสาร PDF ที่อัปเดตโดยมีช่องกาเครื่องหมายรวมอยู่ด้วย:

```csharp
annotator.Save("result.pdf");
```

## ขั้นตอนที่ 7: แสดงเส้นทางเอาต์พุต

สุดท้ายแจ้งให้ผู้ใช้ทราบว่าเอกสารที่แก้ไขถูกบันทึกไว้ที่ไหน:

```csharp
Console.WriteLine($"\nDocument saved successfully.\nCheck output in {outputPath}.");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เพิ่มส่วนประกอบ Checkbox ลงในเอกสาร PDF สำเร็จแล้วโดยใช้ GroupDocs.Annotation สำหรับ .NET ฟังก์ชันนี้ช่วยให้คุณสร้าง PDF แบบโต้ตอบที่ช่วยยกระดับประสบการณ์และการมีส่วนร่วมของผู้ใช้

## คำถามที่พบบ่อย

### ฉันสามารถปรับแต่งลักษณะของช่องกาเครื่องหมายได้หรือไม่

แน่นอน! คุณสามารถปรับเปลี่ยนคุณสมบัติต่างๆ เช่น สี สไตล์ และขนาด ให้ตรงกับความต้องการเฉพาะของคุณได้

### GroupDocs.Annotation สำหรับ .NET เหมาะสำหรับการใช้งานเชิงพาณิชย์หรือไม่

ใช่ GroupDocs.Annotation สำหรับ .NET ให้ใบอนุญาตเชิงพาณิชย์สำหรับธุรกิจ

### ฉันสามารถทดลองใช้ GroupDocs.Annotation สำหรับ .NET ก่อนซื้อได้หรือไม่

ใช่ มีช่วงทดลองใช้ฟรี คุณสามารถเข้าถึงได้ [ที่นี่](https://releases-groupdocs.com/).

### ฉันสามารถหาการสนับสนุนสำหรับ GroupDocs.Annotation สำหรับ .NET ได้ที่ไหน

การสนับสนุนและทรัพยากรเพิ่มเติมมีอยู่บน [ฟอรั่ม GroupDocs](https://forum-groupdocs.com/c/annotation/10).

### ฉันต้องมีใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบหรือไม่?

คุณสามารถขอใบอนุญาตชั่วคราวเพื่อการทดสอบได้จาก [ที่นี่](https://purchase-groupdocs.com/temporary-license/).