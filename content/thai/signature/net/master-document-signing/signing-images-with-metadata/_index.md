---
"description": "เรียนรู้วิธีการเซ็นชื่อรูปภาพด้วยเมตาดาต้าในแอปพลิเคชัน .NET ของคุณอย่างมีประสิทธิภาพด้วย GroupDocs.Signature บทช่วยสอนแบบทีละขั้นตอนนี้ครอบคลุมทุกอย่างตั้งแต่การติดตั้งไปจนถึงการใช้งานจริง ช่วยให้คุณปรับปรุงเอกสารของคุณด้วยลายเซ็นเมตาดาต้าได้อย่างง่ายดาย"
"linktitle": "คู่มือการลงนามภาพด้วยข้อมูลเมตา"
"second_title": "API ของ GroupDocs.Signature .NET"
"title": "คู่มือการลงนามภาพด้วยข้อมูลเมตาโดยใช้ GroupDocs.Signature"
"url": "/th/signature/net/master-document-signing/signing-images-with-metadata/"
"weight": 10
---

## การแนะนำ

GroupDocs.Signature สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถเซ็นชื่อบนรูปภาพด้วยข้อมูลเมตาได้อย่างมีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. GroupDocs.Signature สำหรับ .NET: ติดตั้งแพ็กเกจ GroupDocs.Signature ในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/signature/net/).
2. ไฟล์ภาพ: เตรียมไฟล์ภาพที่คุณต้องการลงนามด้วยข้อมูลเมตา

## นำเข้าเนมสเปซที่จำเป็น

ในโค้ด C# ของคุณ ให้ทำการนำเข้าเนมสเปซต่อไปนี้:

```csharp
using System;
using System.IO;
using GroupDocs.Signature;
using GroupDocs.Signature.Domain;
using GroupDocs.Signature.Options;
```

## ขั้นตอนที่ 1: โหลดไฟล์รูปภาพของคุณ

เริ่มต้นด้วยการระบุเส้นทางไปยังไฟล์รูปภาพของคุณและไดเร็กทอรีเอาต์พุตสำหรับรูปภาพที่ลงนาม:

```csharp
string filePath = "sample.png";            
string outputFilePath = Path.Combine("Your Document Directory", "SignImageWithMetadata", "SignedWithMetadata.png");
```

## ขั้นตอนที่ 2: สร้างลายเซ็นข้อมูลเมตา

ขั้นตอนต่อไป ให้สร้างลายเซ็นเมตาข้อมูลและเพิ่มลงในตัวเลือกการลงนาม:

```csharp
using (Signature signature = new Signature(filePath))
{
    ushort imgsMetadataId = 41996; // ID เริ่มต้นสำหรับข้อมูลเมตา
    MetadataSignOptions options = new MetadataSignOptions();

    // เพิ่มลายเซ็นข้อมูลเมตาประเภทต่างๆ
    options
        .Add(new ImageMetadataSignature(imgsMetadataId++, "Mr. Sherlock Holmes")) // ค่าสตริง
        .Add(new ImageMetadataSignature(imgsMetadataId++, DateTime.Now))          // ค่าวันที่และเวลา
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123456))                // ค่าจำนวนเต็ม
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123.456D))              // ค่าสองเท่า
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123.456M))              // ค่าทศนิยม
        .Add(new ImageMetadataSignature(imgsMetadataId++, 123.456F));             // ค่าลอยตัว

    // ลงนามในเอกสารและบันทึกผลลัพธ์
    SignResult result = signature.Sign(outputFilePath, options);
    Console.WriteLine($"\nDocument signed successfully with {result.Succeeded.Count} signature(s).\nFile saved at: {outputFilePath}");
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีการเซ็นชื่อรูปภาพด้วยเมตาดาต้าโดยใช้ GroupDocs.Signature สำหรับ .NET ทำตามขั้นตอนเหล่านี้เพื่อเพิ่มลายเซ็นเมตาดาต้าลงในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย ซึ่งจะช่วยเพิ่มประสิทธิภาพการทำงานและความสมบูรณ์ของรูปภาพของคุณ

## คำถามที่พบบ่อย

### ฉันสามารถลงนามภาพหลายภาพพร้อมข้อมูลเมตาโดยใช้ GroupDocs.Signature สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถลงนามในรูปภาพหลายภาพได้โดยการวนซ้ำผ่านไฟล์รูปภาพแต่ละไฟล์และใช้ลายเซ็นเมตาข้อมูล

### มีเวอร์ชันทดลองใช้สำหรับ GroupDocs.Signature สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ได้จาก [ที่นี่](https://releases-groupdocs.com/).

### GroupDocs.Signature สำหรับ .NET รองรับรูปแบบไฟล์อื่นนอกเหนือจากรูปภาพหรือไม่
แน่นอน! GroupDocs.Signature รองรับรูปแบบต่างๆ รวมถึง PDF, Word, Excel และอื่นๆ อีกมากมาย

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นข้อมูลเมตาได้หรือไม่
ใช่ คุณสามารถปรับแต่งลักษณะต่างๆ เช่น ขนาดตัวอักษร สี และตำแหน่งของลายเซ็นเมตาเดตาได้

### ฉันจะได้รับการสนับสนุนสำหรับ GroupDocs.Signature สำหรับ .NET ได้ที่ไหน
หากต้องการความช่วยเหลือ โปรดไปที่ฟอรัม GroupDocs.Signature [ที่นี่](https://forum-groupdocs.com/c/signature/13).