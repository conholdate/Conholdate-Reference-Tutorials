---
"description": "ค้นพบวิธีนำ Optical Character Recognition (OCR) ไปใช้ในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดายด้วย Aspose.OCR คู่มือทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ"
"linktitle": "คู่มือการใช้ OCR บนรูปภาพจาก URL ใน OCR Image Recognition"
"second_title": "API ของ Aspose.OCR .NET"
"title": "คู่มือการใช้ OCR บนรูปภาพจาก URL ใน OCR Image Recognition"
"url": "/th/ocr/net/optimization-ocr/guide-to-ocr-on-image-from-url/"
"weight": 10
---

## การแนะนำ

การรู้จำอักขระด้วยแสง (OCR) เป็นเทคโนโลยีสำคัญสำหรับการแยกข้อความออกจากรูปภาพ ช่วยให้นักพัฒนาสามารถสร้างแอปพลิเคชันที่สามารถอ่านและประมวลผลข้อมูลข้อความได้อย่างราบรื่น Aspose.OCR สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งออกแบบมาเพื่อลดความซับซ้อนในการผสานรวมความสามารถ OCR เข้ากับแอปพลิเคชัน .NET ของคุณ คู่มือนี้จะอธิบายวิธีการทำ OCR บนรูปภาพโดยตรงจาก URL เพียงไม่กี่ขั้นตอนง่ายๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Aspose.OCR สำหรับ .NET: ดาวน์โหลดและรวมไลบรารี Aspose.OCR ลงในโครงการ .NET ของคุณจาก [หน้าเผยแพร่](https://releases-aspose.com/ocr/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ (แนะนำให้ใช้ Visual Studio)

## ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น

หากต้องการใช้คุณลักษณะที่นำเสนอโดย Aspose.OCR ให้ทำการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ:

```csharp
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using Aspose.OCR;
using Aspose.OCR.Models;
```

## ขั้นตอนที่ 2: ระบุไดเรกทอรีเอกสาร

กำหนดไดเรกทอรีสำหรับเอกสารของคุณ แทนที่ `"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีการทำงานของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 3: ระบุ URL ของรูปภาพ

ระบุ URL ของรูปภาพที่คุณต้องการแยกข้อความออกมา ตรวจสอบให้แน่ใจว่ารูปภาพนั้นสามารถเข้าถึงได้แบบสาธารณะ:

```csharp
string uri = "https://example.com/image.jpg";
```

## ขั้นตอนที่ 4: เริ่มต้น Aspose.OCR

สร้างอินสแตนซ์ของ `AsposeOcr` คลาสที่คุณจะใช้ในการดำเนินการ OCR:

```csharp
AsposeOcr api = new AsposeOcr();
```

## ขั้นตอนที่ 5: จดจำข้อความจากรูปภาพ

ใช้ `RecognizeImageFromUri` วิธีการดึงข้อความจาก URL ของรูปภาพ คุณสามารถปรับการตั้งค่าการจดจำต่างๆ ได้ตามความต้องการเฉพาะของคุณ:

```csharp
RecognitionResult result = api.RecognizeImageFromUri(uri, new RecognitionSettings
{
    DetectAreas = true,
    RecognizeSingleLine = false,
    AutoSkew = true,
    RecognitionAreas = new List<Rectangle>
    {
        new Rectangle(1, 3, 390, 70),
        new Rectangle(1, 72, 390, 70)
    }
});
```

## ขั้นตอนที่ 6: แสดงผลลัพธ์การจดจำ

ส่งออกข้อความที่รู้จักพร้อมกับข้อมูลที่เกี่ยวข้อง รวมถึงพื้นที่ที่รู้จักและคำเตือน:

```csharp
Console.WriteLine($"Text:\n {result.RecognitionText}");
Console.WriteLine("Areas:");
result.RecognitionAreasText.ForEach(a => Console.WriteLine($"{a}"));
Console.WriteLine("Warnings:");
result.Warnings.ForEach(w => Console.WriteLine($"{w}"));
Console.WriteLine($"JSON: {result.GetJson()}");
```

## ขั้นตอนที่ 7: ดำเนินการสมัครของคุณ

เรียกใช้แอปพลิเคชันของคุณ หากกำหนดค่าทุกอย่างถูกต้อง คุณควรเห็นการดำเนินการ OCR สำเร็จ:

```csharp
Console.WriteLine("OCR process executed successfully.");
```

## บทสรุป

การรวมความสามารถ OCR เข้ากับแอปพลิเคชัน .NET ของคุณเป็นเรื่องง่ายด้วย Aspose.OCR คู่มือนี้จะพาคุณผ่านขั้นตอนสำคัญในการทำ OCR กับรูปภาพจาก URL ซึ่งเป็นการสร้างพื้นฐานสำหรับการพัฒนาแอปพลิเคชันที่ใช้ประโยชน์จากเทคโนโลยีการรู้จำข้อความ

## คำถามที่พบบ่อย

### Aspose.OCR เหมาะสำหรับการจดจำหลายภาษาหรือไม่?

ใช่ Aspose.OCR รองรับภาษาต่างๆ จึงเหมาะอย่างยิ่งสำหรับแอปพลิเคชันที่กำหนดเป้าหมายผู้ใช้ระดับนานาชาติ

### Aspose.OCR สามารถจัดการกับการจดจำข้อความทั้งแบบบรรทัดเดียวและหลายบรรทัดได้หรือไม่

แน่นอน! ไลบรารีนี้มีความหลากหลาย รองรับการจดจำข้อความทั้งแบบบรรทัดเดียวและหลายบรรทัดตามความต้องการของโครงการของคุณ

### มีตัวเลือกการอนุญาตสิทธิ์ใช้งานอะไรบ้างสำหรับ Aspose.OCR?

คุณสามารถเรียนรู้เกี่ยวกับตัวเลือกการอนุญาตสิทธิ์ที่แตกต่างกันและทำการซื้อจาก [ร้าน Aspose](https://purchase-conholdate.com/buy).

### มี Aspose.OCR เวอร์ชันทดลองใช้งานหรือไม่

ใช่ มีช่วงทดลองใช้ฟรี คุณสามารถทดลองใช้ได้ที่ [หน้าเผยแพร่](https://releases-aspose.com/).

### ฉันสามารถหาการสนับสนุนสำหรับ Aspose.OCR ได้ที่ไหน

หากต้องการความช่วยเหลือหรือการสนทนาในชุมชนเกี่ยวกับ Aspose.OCR โปรดไปที่ [ฟอรัม Aspose.OCR](https://forum-aspose.com/c/ocr/16).