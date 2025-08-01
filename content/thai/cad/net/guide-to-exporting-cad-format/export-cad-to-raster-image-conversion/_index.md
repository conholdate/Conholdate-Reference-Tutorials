---
"description": "เรียนรู้วิธีการแปลงเค้าโครง CAD เป็นรูปแบบภาพแรสเตอร์ต่างๆ อย่างมีประสิทธิภาพโดยใช้ Aspose.CAD สำหรับ .NET คู่มือฉบับสมบูรณ์นี้จะแนะนำคุณตลอดกระบวนการด้วยโค้ดที่ชัดเจน"
"linktitle": "ส่งออก CAD เป็นการแปลงภาพแรสเตอร์"
"second_title": "Aspose.CAD .NET - รูปแบบไฟล์ CAD และ BIM"
"title": "ส่งออก CAD เป็นภาพแรสเตอร์ด้วย Aspose.CAD สำหรับ .NET"
"url": "/th/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## การแนะนำ

คุณกำลังมองหาวิธีแปลงเลย์เอาต์ CAD เป็นรูปแบบภาพแรสเตอร์อย่างง่ายดายด้วย Aspose.CAD สำหรับ .NET อยู่ใช่ไหม? คู่มือทีละขั้นตอนนี้ออกแบบมาเพื่อช่วยคุณนำทางกระบวนการ พร้อมโค้ดสั้นๆ กระชับ เพื่อประสบการณ์การใช้งานที่ราบรื่น ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนนี้ให้ข้อมูลเชิงลึกอันมีค่าสำหรับทุกระดับทักษะ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Aspose.CAD สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [เว็บไซต์ Aspose.CAD](https://releases-aspose.com/cad/net/).
- ไฟล์รูปวาด CAD: มีไฟล์รูปวาด CAD ของคุณ (เช่น `conic_pyramid.dxf`) พร้อมสำหรับการแปลง

## นำเข้าเนมสเปซที่จำเป็น

ในโปรเจ็กต์ .NET ของคุณ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้งานฟังก์ชัน Aspose.CAD เพิ่มข้อมูลต่อไปนี้ไว้ที่ด้านบนของโค้ด:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## ขั้นตอนที่ 1: โหลดแบบ CAD ของคุณ

ขั้นแรก ให้ระบุไดเร็กทอรีและโหลดไฟล์ CAD ของคุณลงในอินสแตนซ์ Image:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// โหลดแบบ CAD
using (var image = Image.Load(sourceFilePath))
{
    // ดำเนินการขั้นตอนต่อไป
}
```

## ขั้นตอนที่ 2: สร้างตัวเลือกการแรสเตอร์

ขั้นตอนต่อไปคือตั้งค่าตัวเลือกการแรสเตอร์ โดยกำหนดขนาดที่ต้องการสำหรับภาพเอาต์พุต:

```csharp
// เริ่มต้น CadRasterizationOptions
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## ขั้นตอนที่ 3: ระบุเลเยอร์สำหรับการแปลง

หากคุณต้องการแปลงเลเยอร์เฉพาะ ให้เพิ่มเลเยอร์เหล่านั้นลงในตัวเลือกการแรสเตอร์ของคุณ:

```csharp
// ระบุเลเยอร์ที่จะแปลง
rasterizationOptions.Layers = new [] { "LayerA" };
```

## ขั้นตอนที่ 4: ตั้งค่าตัวเลือกการส่งออก JPEG

ตอนนี้ ให้สร้างตัวเลือกสำหรับรูปแบบภาพที่คุณต้องการส่งออก (JPEG ในกรณีนี้):

```csharp
// สร้าง JpegOptions สำหรับการส่งออก
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## ขั้นตอนที่ 5: ส่งออกเป็นรูปแบบ JPEG

สุดท้ายบันทึกภาพที่แปลงแล้ว:

```csharp
// กำหนดเส้นทางไฟล์เอาท์พุตและบันทึกภาพ
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## คุณสมบัติเพิ่มเติม: แปลงทุกเลเยอร์

หากต้องการแปลงเลเยอร์ทั้งหมดในภาพวาด CAD ของคุณ คุณสามารถใช้วิธีการดังต่อไปนี้:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // ทำซ้ำผ่านเลเยอร์ต่างๆ และบันทึกแต่ละเลเยอร์เป็นไฟล์ JPEG แยกกัน
    // รหัสการใช้งานของคุณที่นี่
}
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการแปลงเลย์เอาต์ CAD เป็นรูปแบบภาพแรสเตอร์อย่างมีประสิทธิภาพโดยใช้ Aspose.CAD สำหรับ .NET คู่มือนี้นำเสนอแนวทางที่ตรงไปตรงมา เหมาะสำหรับนักพัฒนาที่ต้องการแปลงไฟล์ CAD อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันสามารถส่งออกไปยังรูปแบบภาพอื่นได้หรือไม่

แน่นอน! เพียงแค่สลับ `JpegOptions` พร้อมตัวเลือกการจัดรูปแบบอื่น ๆ เช่น `PngOptions` หรือ `BmpOptions`, ขึ้นอยู่กับความต้องการของคุณ

### มีเวอร์ชันทดลองใช้งานไหม?

ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้เพื่อสำรวจฟังก์ชันการทำงานได้โดยทำตามขั้นตอนต่อไปนี้ [ลิงค์](https://releases-aspose.com/cad/net/).

### ฉันสามารถค้นหาการสนับสนุนสำหรับ Aspose.CAD ได้ที่ไหน

สำหรับการสนับสนุนจากชุมชน โปรดดู Aspose.CAD [ฟอรั่ม](https://forum.aspose.com/c/cad/19)หรือพิจารณาซื้อใบอนุญาตสำหรับความช่วยเหลือเฉพาะเพิ่มเติม

### ใบอนุญาตชั่วคราวเป็นไปได้หรือไม่?

ใช่ มีใบอนุญาตชั่วคราว คุณสามารถขอได้ [ที่นี่](https://purchase-conholdate.com/temporary-license/).

### ฉันสามารถเข้าถึงเอกสารโดยละเอียดได้ที่ไหน

เยี่ยมชมเอกสารประกอบที่ครอบคลุม [ที่นี่](https://reference.aspose.com/cad/net/) สำหรับข้อมูลเพิ่มเติม