---
"description": "เรียนรู้วิธีโหลดไฟล์ DGN ดำเนินการวนซ้ำผ่านองค์ประกอบต่างๆ จัดการเอนทิตีทั้งแบบ 2D และ 3D และส่งออกเป็นภาพแรสเตอร์ ทั้งหมดนี้ในขณะที่ใช้ประโยชน์จากฟีเจอร์อันทรงพลังของไลบรารี Aspose.CAD"
"linktitle": "การเรียนรู้การจัดการไฟล์ DGN"
"second_title": "Aspose.CAD .NET - รูปแบบไฟล์ CAD และ BIM"
"title": "การเรียนรู้การจัดการไฟล์ DGN ด้วย Aspose.CAD ใน .NET"
"url": "/th/cad/net/guide-to-cad-features-and-support/mastering-dgn-file-manipulation/"
"weight": 18
---

## การแนะนำ

คุณเป็นนักพัฒนา .NET ที่อยากผสานรวมไฟล์ DGN เข้ากับแอปพลิเคชันของคุณหรือไม่? Aspose.CAD สำหรับ .NET มีไลบรารีอันทรงพลังที่ออกแบบมาโดยเฉพาะสำหรับการทำงานกับไฟล์ DGN ในบทช่วยสอนนี้ เราจะสำรวจวิธีการจัดการไฟล์ DGN อย่างมีประสิทธิภาพ รวมถึงองค์ประกอบที่รองรับ และวิธีการจัดการไฟล์เหล่านี้ในโปรเจกต์ .NET ของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET: ความคุ้นเคยกับ C# หรือ VB.NET จะเป็นประโยชน์
- Visual Studio: ติดตั้งบนเครื่องของคุณเพื่อการพัฒนาโครงการ
- ไลบรารี Aspose.CAD สำหรับ .NET: ดาวน์โหลดจาก [แอสโพส.CAD](https://releases-aspose.com/cad/net/).

## ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น

หากต้องการใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.CAD ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
using Aspose.CAD.FileFormats.Dgn;
using Aspose.CAD.FileFormats.Dgn.DgnElements;
```

## ขั้นตอนที่ 2: โหลดไฟล์ DGN ของคุณ

เริ่มต้นด้วยการโหลดไฟล์ DGN ที่มีอยู่ลงในแอปพลิเคชันของคุณ ซึ่งทำได้โดยการสร้างอินสแตนซ์ `DgnImage`-

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage dgnImage = (DgnImage)Image.Load(sourceFilePath))
{
    // ดำเนินการตามตรรกะของคุณที่นี่
}
```

## ขั้นตอนที่ 3: ทำซ้ำผ่านองค์ประกอบ DGN

เมื่อโหลดไฟล์ DGN แล้ว คุณสามารถวนซ้ำองค์ประกอบต่างๆ ได้ Aspose.CAD มีประเภทองค์ประกอบ DGN หลากหลายให้คุณเลือกใช้

```csharp
foreach (DgnDrawingElementBase element in dgnImage.Elements)
{
    // ประมวลผลแต่ละองค์ประกอบ
}
```

## ขั้นตอนที่ 4: จัดการเอนทิตี้ 2D และ 3D

คุณสามารถแยกความแตกต่างระหว่างองค์ประกอบ DGN แบบ 2 มิติ และ 3 มิติได้ ด้านล่างนี้คือวิธีจัดการอย่างมีประสิทธิภาพ:

### จัดการเอนทิตี้ 2 มิติ

คุณสามารถจัดการเอนทิตี 2D ที่ได้รับการสนับสนุนก่อนหน้านี้ด้วยบล็อกสวิตช์เคสได้

```csharp
switch (element.Metadata.Type)
{
    case DgnElementType.Line:
    case DgnElementType.Ellipse:
    case DgnElementType.Curve:
        // เพิ่มตรรกะการประมวลผลของคุณที่นี่ 
        break;
}
```

### จัดการเอนทิตี้ 3 มิติ

ในทำนองเดียวกัน จัดการเอนทิตี 3 มิติ ดังต่อไปนี้:

```csharp
switch (element.Metadata.Type)
{
    case DgnElementType.SolidHeader3D:
    case DgnElementType.Cone:
    case DgnElementType.CellHeader:
        // เพิ่มตรรกะการประมวลผลของคุณที่นี่ 
        break;
}
```

## ขั้นตอนที่ 5: ส่งออกไฟล์ DGN

หลังจากจัดการองค์ประกอบ DGN แล้ว คุณอาจต้องการส่งออกไฟล์เป็นภาพแรสเตอร์ ซึ่งสามารถทำได้ง่ายๆ ด้วย Aspose.CAD

```csharp
string outputFilePath = myDir + "Exported_Image.png"; // กำหนดเส้นทางเอาต์พุตของคุณ
dgnImage.Save(outputFilePath, new Aspose.CAD.ImageOptions.PngOptions());
Console.WriteLine($"\nThe DGN file exported successfully to raster image.\nFile saved at {outputFilePath}");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.CAD สำหรับ .NET เพื่อจัดการไฟล์ DGN ได้อย่างมีประสิทธิภาพ เพียงทำตามขั้นตอนที่อธิบายไว้ คุณจะสามารถจัดการองค์ประกอบ DGN ทั้งแบบ 2 มิติและ 3 มิติได้อย่างง่ายดาย และส่งออกเป็นภาพแรสเตอร์ ไลบรารีอันทรงพลังนี้ช่วยให้สามารถผสานรวมการประมวลผล DGN เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ช่วยเพิ่มศักยภาพให้กับโครงการของคุณ

## คำถามที่พบบ่อย

### ฉันสามารถค้นหาเอกสารสำหรับ Aspose.CAD สำหรับ .NET ได้ที่ไหน

มีเอกสารประกอบครบถ้วน [ที่นี่](https://reference-aspose.com/cad/net/).

### ฉันจะดาวน์โหลด Aspose.CAD สำหรับ .NET ได้อย่างไร

คุณสามารถดาวน์โหลดไลบรารีเวอร์ชันล่าสุดได้ [ที่นี่](https://releases-aspose.com/cad/net/).

### มีการทดลองใช้ Aspose.CAD สำหรับ .NET ฟรีหรือไม่

ใช่ สามารถทดลองใช้ฟรีได้ [ที่นี่](https://releases-aspose.com/).

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.CAD สำหรับ .NET ได้อย่างไร

คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-conholdate.com/temporary-license/).

### ต้องการความช่วยเหลือหรือมีคำถาม?

หากต้องการการสนับสนุนหรือถามคำถาม โปรดไปที่ชุมชน Aspose.CAD [ฟอรัมสนับสนุน](https://forum-aspose.com/c/cad/19).