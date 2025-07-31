---
"description": "เรียนรู้วิธีแปลงไฟล์ DGN เป็น PDF ได้อย่างง่ายดายด้วยไลบรารี Aspose.CAD อันทรงพลังสำหรับ .NET คู่มือทีละขั้นตอนนี้ออกแบบมาสำหรับนักพัฒนาทุกระดับ"
"linktitle": "แปลง DGN เป็น PDF ใน Aspose.CAD สำหรับ .NET"
"second_title": "Aspose.CAD .NET - รูปแบบไฟล์ CAD และ BIM"
"title": "แปลง DGN เป็น PDF ใน Aspose.CAD สำหรับ .NET"
"url": "/th/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## การแนะนำ

การสำรวจโลกของไฟล์ CAD อาจเป็นเรื่องท้าทาย แต่ด้วย Aspose.CAD สำหรับ .NET นักพัฒนาสามารถจัดการและแปลงไฟล์ CAD ต่างๆ ได้อย่างง่ายดาย หนึ่งในความต้องการทั่วไปคือการแปลงไฟล์ DGN เป็น PDF ซึ่งเราจะอธิบายทีละขั้นตอนในบทช่วยสอนนี้

## ข้อกำหนดเบื้องต้น

เพื่อติดตาม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- มีความสามารถพื้นฐานใน C# และ .NET framework
- ติดตั้งไลบรารี Aspose.CAD สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/cad/net/).
- ไฟล์ DGN ตัวอย่าง (เช่น Nikon_D90_Camera.dgn) 

## ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น

เริ่มต้นด้วยการนำเข้าเนมสเปซที่เกี่ยวข้องลงในโครงการ C# ของคุณ:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## ขั้นตอนที่ 2: โหลดไฟล์ DGN

ระบุไดเร็กทอรีสำหรับไฟล์ DGN ของคุณและโหลดโดยใช้โค้ดต่อไปนี้:

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // การประมวลผลเพิ่มเติมจะไปที่นี่...
}
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการแรสเตอร์

ขั้นตอนต่อไป ตั้งค่าตัวเลือกการแรสเตอร์เพื่อกำหนดว่า DGN ของคุณจะถูกเรนเดอร์ใน PDF อย่างไร:

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // ปรับความกว้างได้ตามต้องการ
    PageHeight = 300, // ปรับความสูงได้ตามต้องการ
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## ขั้นตอนที่ 4: สร้างตัวเลือก PDF

กำหนดตัวเลือก PDF โดยบูรณาการการตั้งค่าการแรสเตอร์ที่กำหนดค่าไว้ก่อนหน้านี้:

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## ขั้นตอนที่ 5: บันทึก DGN เป็น PDF

สุดท้าย ให้บันทึกไฟล์ DGN เป็น PDF โดยใช้ตัวเลือกที่คุณกำหนดค่าไว้:

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## บทสรุป

ขอแสดงความยินดี! คุณแปลงไฟล์ DGN เป็น PDF โดยใช้ Aspose.CAD สำหรับ .NET สำเร็จแล้ว บทช่วยสอนแบบตรงไปตรงมานี้จะแนะนำคุณตั้งแต่ขั้นตอนการโหลดไฟล์ DGN ตั้งค่าตัวเลือกแรสเตอร์ และบันทึกผลลัพธ์เป็น PDF

## คำถามที่พบบ่อย

### ฉันจำเป็นต้องมีความรู้ CAD ล่วงหน้าเพื่อใช้ Aspose.CAD หรือไม่  
แน่นอน! Aspose.CAD ถูกออกแบบมาเพื่อลดความซับซ้อนของงาน CAD ทำให้นักพัฒนาทุกคนสามารถเข้าถึงได้ไม่ว่าจะมีความรู้ CAD หรือไม่ก็ตาม

### ฉันสามารถหาทรัพยากรและเอกสารเพิ่มเติมสำหรับ Aspose.CAD ได้ที่ไหน  
คุณสามารถสำรวจคำแนะนำและตัวอย่างที่ครอบคลุมได้ใน [เอกสาร Aspose.CAD](https://reference-aspose.com/cad/net/).

### มีการทดลองใช้ Aspose.CAD ฟรีหรือไม่  
ใช่ สามารถทดลองใช้ฟรีได้ [ที่นี่](https://releases-aspose.com/).

### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.CAD ได้อย่างไร  
คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-conholdate.com/temporary-license/).

### ต้องการความช่วยเหลือหรือมีคำถาม?  
ร่วมสนทนาได้ใน [ฟอรั่ม Aspose.CAD](https://forum.aspose.com/c/cad/19) สำหรับการสนับสนุนและการสอบถามจากชุมชน