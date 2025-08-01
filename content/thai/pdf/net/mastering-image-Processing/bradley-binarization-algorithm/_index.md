---
"description": "เรียนรู้วิธีแปลงหน้า PDF เป็นไฟล์ภาพ TIFF ไบนารีคุณภาพสูงโดยใช้อัลกอริทึม Bradley Binarization ใน Aspose.PDF สำหรับ .NET คู่มือทีละขั้นตอนนี้ประกอบด้วยตัวอย่างโค้ด"
"linktitle": "อัลกอริทึมการแปลงไบนารีของแบรดลีย์"
"second_title": "เอกสารอ้างอิง Aspose.PDF สำหรับ .NET API"
"title": "อัลกอริทึมการแปลงไบนารีของแบรดลีย์"
"url": "/th/pdf/net/mastering-image-Processing/bradley-binarization-algorithm/"
"weight": 30
---

## การแนะนำ

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการแปลงหน้า PDF เป็นไฟล์ภาพ TIFF โดยใช้อัลกอริทึม Bradley Binarization Aspose.PDF สำหรับ .NET ช่วยลดความยุ่งยากของงานนี้ ช่วยให้คุณสามารถจัดการและเพิ่มประสิทธิภาพเวิร์กโฟลว์เอกสารของคุณได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Aspose.PDF สำหรับ .NET: ดาวน์โหลดไลบรารีจาก [ที่นี่](https://releases-aspose.com/pdf/net/).
- Visual Studio (หรือ IDE C# ใดๆ)
- ความรู้พื้นฐานเกี่ยวกับ C#
- ใบอนุญาตที่ถูกต้องหรือ [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) จาก Aspose

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ขั้นแรก ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ของคุณและนำเข้าเนมสเปซที่จำเป็น:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสาร

ระบุเส้นทางไปยังไดเร็กทอรีที่เอกสาร PDF ของคุณตั้งอยู่ รวมถึงเส้นทางเอาต์พุตสำหรับรูปภาพ TIFF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // เส้นทางไปยังไฟล์ PDF ของคุณ
```

ไดเร็กทอรีนี้จะจัดเก็บทั้งไฟล์ PDF ต้นฉบับและไฟล์ TIFF ที่แปลงแล้ว

## ขั้นตอนที่ 3: โหลดเอกสาร PDF

เปิดเอกสาร PDF ที่คุณต้องการแปลง:

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

แทนที่ `PageToTIFF.pdf` พร้อมชื่อไฟล์ PDF ของคุณ

## ขั้นตอนที่ 4: ระบุเส้นทางเอาต์พุต

กำหนดเส้นทางเอาต์พุตสำหรับไฟล์ TIFF ที่สร้างขึ้น:

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## ขั้นตอนที่ 5: ตั้งค่าความละเอียดของภาพ

ตั้งค่าความละเอียดสำหรับภาพ TIFF ค่า DPI ที่สูงขึ้นจะทำให้คุณภาพของภาพดีขึ้น:

```csharp
Resolution resolution = new Resolution(300);
```

## ขั้นตอนที่ 6: กำหนดค่าการตั้งค่า TIFF

กำหนดค่าการตั้งค่าสำหรับภาพ TIFF รวมถึงการบีบอัดและความลึกของสี:

```csharp
TiffSettings tiffSettings = new TiffSettings
{
    Compression = CompressionType.LZW,
    Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp
};
```

การใช้ 1bpp (1 บิตต่อพิกเซล) จะเตรียมภาพสำหรับเอาต์พุตแบบไบนารี

## ขั้นตอนที่ 7: สร้างอุปกรณ์ TIFF

สร้างอุปกรณ์ TIFF ที่จะจัดการการแปลง:

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## ขั้นตอนที่ 8: แปลงหน้า PDF เป็น TIFF

แปลงหน้าแรกของ PDF เป็นภาพ TIFF:

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## ขั้นตอนที่ 9: ใช้อัลกอริทึม Bradley Binarization

ตอนนี้ ให้ใช้อัลกอริทึม Bradley เพื่อแปลงภาพ TIFF ระดับสีเทาเป็นภาพไบนารี:

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

การ `BinarizeBradley` วิธีนี้ใช้สตรีมไฟล์สองสตรีม (อินพุตและเอาต์พุต) และค่าขีดจำกัด ปรับค่าขีดจำกัดตามความจำเป็นเพื่อผลลัพธ์ที่ดีที่สุด

## ขั้นตอนที่ 10: ยืนยันการแปลงสำเร็จ

สุดท้ายยืนยันว่าการแปลงสำเร็จ:

```csharp
Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

## บทสรุป

ขอแสดงความยินดี! คุณแปลงหน้า PDF เป็นไฟล์ภาพ TIFF สำเร็จแล้ว และได้นำอัลกอริทึม Bradley Binarization มาใช้กับ Aspose.PDF สำหรับ .NET กระบวนการนี้จำเป็นสำหรับการจัดเก็บเอกสาร, OCR และแอปพลิเคชันระดับมืออาชีพอื่นๆ ด้วยความละเอียดคุณภาพสูงและการบีบอัดที่มีประสิทธิภาพ รูปภาพเอกสารของคุณจะคมชัดและมีขนาดที่จัดการได้ง่าย

## คำถามที่พบบ่อย

### อัลกอริทึมแบรดลีย์คืออะไร?
อัลกอริทึมแบรดลีย์เป็นเทคนิคการแปลงภาพเป็นไบนารีที่แปลงภาพสีเทาเป็นภาพไบนารีโดยการกำหนดค่าเกณฑ์การปรับตัวสำหรับแต่ละพิกเซลตามสภาพแวดล้อม

### ฉันสามารถแปลงไฟล์ PDF หลายหน้าเป็น TIFF โดยใช้วิธีนี้ได้หรือไม่
ใช่ คุณสามารถปรับเปลี่ยนได้ `Process` วิธีการวนซ้ำผ่านหน้าทั้งหมดในเอกสารเพื่อการแปลง

### ความละเอียดที่เหมาะสมที่สุดในการแปลงไฟล์ PDF เป็น TIFF คือเท่าใด
โดยทั่วไปแนะนำให้ใช้ความละเอียด 300 DPI สำหรับภาพคุณภาพสูง แต่คุณสามารถปรับความละเอียดนี้ได้ตามความต้องการเฉพาะของคุณ

### 1bpp หมายถึงอะไรในความลึกของสี?
1bpp (1 บิตต่อพิกเซล) บ่งบอกว่าภาพจะเป็นสีขาวดำ โดยแต่ละพิกเซลจะเป็นสีดำสนิทหรือสีขาวสนิท

### อัลกอริทึม Bradley เหมาะกับ OCR หรือไม่?
ใช่ อัลกอริทึม Bradley มักใช้ในการประมวลผล OCR ก่อนการประมวลผล เนื่องจากช่วยเพิ่มความคมชัดของข้อความในเอกสารที่สแกน ทำให้ความแม่นยำในการจดจำเพิ่มขึ้น