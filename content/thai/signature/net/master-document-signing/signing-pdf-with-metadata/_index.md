---
"description": "เรียนรู้วิธีเสริมความแข็งแกร่งให้กับเอกสาร PDF ของคุณด้วยความปลอดภัยและการตรวจสอบย้อนกลับที่มากขึ้น โดยการลงนามด้วยข้อมูลเมตาโดยใช้ GroupDocs.Signature สำหรับ .NET บทช่วยสอนที่ครอบคลุมนี้จะช่วยให้คุณเข้าใจได้อย่างชัดเจน"
"linktitle": "คู่มือการลงนาม PDF ด้วยข้อมูลเมตา"
"second_title": "API ของ GroupDocs.Signature .NET"
"title": "คู่มือการลงนาม PDF ที่มีข้อมูลเมตาโดยใช้ GroupDocs.Signature"
"url": "/th/signature/net/master-document-signing/signing-pdf-with-metadata/"
"weight": 11
---

## การแนะนำ

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีการลงนามในเอกสาร PDF และเพิ่มข้อมูลเมตาโดยใช้ GroupDocs.Signature สำหรับ .NET การเพิ่มข้อมูลเมตาจะช่วยเพิ่มประสิทธิภาพให้กับเอกสารด้วยการให้ข้อมูลสำคัญ เช่น ชื่อผู้แต่ง วันที่สร้าง รหัสเอกสาร และอื่นๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. GroupDocs.Signature สำหรับ .NET: ดาวน์โหลดจาก [ที่นี่](https://releases-groupdocs.com/signature/net/).
2. เอกสาร PDF: เตรียมไฟล์ PDF ตัวอย่างไว้สำหรับการลงนาม
3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#: ความคุ้นเคยกับไวยากรณ์ C# เป็นสิ่งจำเป็นในการทำความเข้าใจตัวอย่างโค้ด

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่จำเป็น:

```csharp
using System;
using System.IO;
using GroupDocs.Signature;
using GroupDocs.Signature.Domain;
using GroupDocs.Signature.Options;
```

## ขั้นตอนที่ 1: โหลดเอกสาร PDF

ระบุเส้นทางของเอกสาร PDF ที่คุณต้องการลงนาม:

```csharp
string filePath = "sample.pdf";
```

## ขั้นตอนที่ 2: ระบุเส้นทางไฟล์เอาต์พุต

กำหนดว่าจะบันทึก PDF ที่ลงนามพร้อมข้อมูลเมตาไว้ที่ไหน:

```csharp
string outputFilePath = Path.Combine("Your Document Directory", "SignPdfWithMetadata", "SignedWithMetadata.pdf");
```

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ลายเซ็น

เริ่มต้น `Signature` อินสแตนซ์ที่มีเส้นทางไปยังเอกสาร PDF:

```csharp
using (Signature signature = new Signature(filePath))
{
    // รหัสที่เกี่ยวข้องกับลายเซ็นจะอยู่ที่นี่
}
```

## ขั้นตอนที่ 4: กำหนดตัวเลือกข้อมูลเมตา

สร้าง `MetadataSignOptions` และเพิ่มฟิลด์เมตาข้อมูลพร้อมกับค่าของมัน:

```csharp
MetadataSignOptions options = new MetadataSignOptions();
options
    .Add(new PdfMetadataSignature("Author", "Mr. Sherlock Holmes")) // ค่าสตริง
    .Add(new PdfMetadataSignature("CreatedOn", DateTime.Now))       // ค่าวันที่และเวลา
    .Add(new PdfMetadataSignature("DocumentId", 123456))            // ค่าจำนวนเต็ม
    .Add(new PdfMetadataSignature("SignatureId", 123.456D))         // ค่าสองเท่า
    .Add(new PdfMetadataSignature("Amount", 123.456M))              // ค่าทศนิยม
    .Add(new PdfMetadataSignature("Total", 123.456F));              // ค่าลอยตัว
```

## ขั้นตอนที่ 5: ลงนามในเอกสาร

ลงนามในเอกสาร PDF ด้วยตัวเลือกเมตาข้อมูลที่ระบุและบันทึกเอกสารที่ลงนามแล้ว:

```csharp
SignResult result = signature.Sign(outputFilePath, options);
Console.WriteLine($"\nSource document signed successfully with {result.Succeeded.Count} signature(s).\nFile saved at {outputFilePath}.");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีการลงนามในเอกสาร PDF ด้วยข้อมูลเมตาโดยใช้ GroupDocs.Signature สำหรับ .NET การทำตามขั้นตอนเหล่านี้จะช่วยให้คุณเพิ่มข้อมูลเมตาที่มีประโยชน์ในไฟล์ PDF ได้อย่างง่ายดาย ช่วยเพิ่มความสามารถในการตรวจสอบย้อนกลับและประโยชน์ใช้สอยของไฟล์

## คำถามที่พบบ่อย

### ฉันสามารถเพิ่มฟิลด์เมตาข้อมูลที่กำหนดเองลงในเอกสาร PDF ของฉันได้หรือไม่

ใช่ คุณสามารถเพิ่มฟิลด์เมตาข้อมูลที่กำหนดเองได้โดยระบุชื่อฟิลด์และค่าที่สอดคล้องกันโดยใช้ GroupDocs.Signature สำหรับ .NET

### GroupDocs.Signature สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่

GroupDocs.Signature สำหรับ .NET เข้ากันได้กับ .NET Framework หลายเวอร์ชัน ช่วยให้มีความยืดหยุ่นและบูรณาการได้ง่าย

### GroupDocs.Signature รองรับการลงนามในรูปแบบเอกสารอื่นนอกเหนือจาก PDF หรือไม่

ใช่ GroupDocs.Signature รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง Word, Excel, PowerPoint และอื่นๆ อีกมากมาย

### ฉันสามารถลงนามในเอกสารหลายฉบับพร้อมกันโดยใช้ GroupDocs.Signature สำหรับ .NET ได้หรือไม่

แน่นอน! คุณสามารถลงนามในเอกสารหลายฉบับพร้อมกันได้โดยการวนซ้ำผ่านรายการไฟล์และใช้กระบวนการลงนามผ่านโปรแกรม

### ผู้ใช้ GroupDocs.Signature มีการสนับสนุนด้านเทคนิคหรือไม่

ใช่ GroupDocs ให้การสนับสนุนทางเทคนิคเฉพาะทางผ่านฟอรัม คุณสามารถเข้าถึงฟอรัมสนับสนุนได้ [ที่นี่](https://forum-groupdocs.com/c/signature/13).