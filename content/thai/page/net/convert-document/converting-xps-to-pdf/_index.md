---
"description": "ค้นพบวิธีการแปลงเอกสาร XPS (XML Paper Specification) เป็น PDF (Portable Document Format) ได้อย่างราบรื่นโดยใช้ไลบรารี Aspose.Page สำหรับ .NET อันทรงพลัง"
"linktitle": "การแปลง XPS เป็น PDF"
"second_title": "API ของ Aspose.Page .NET"
"title": "การแปลง XPS เป็น PDF ด้วย Aspose.Page สำหรับ .NET"
"url": "/th/page/net/convert-document/converting-xps-to-pdf/"
"weight": 11
---

## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการแปลงเอกสาร XPS (XML Paper Specification) เป็น PDF (Portable Document Format) โดยใช้ไลบรารี Aspose.Page for .NET อเนกประสงค์ ไลบรารีอันทรงพลังนี้ช่วยลดความยุ่งยากในการแปลงเอกสาร และมีตัวเลือกการปรับแต่งที่หลากหลาย จึงเป็นตัวเลือกที่ยอดเยี่ยมสำหรับนักพัฒนา

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Aspose.Page สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page สำหรับ .NET จาก [เอกสาร Aspose.Page](https://reference-aspose.com/page/net/).
  
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET โดยใช้ Visual Studio หรือ IDE ที่เข้ากันได้อื่น ๆ

- เอกสาร XPS: เตรียมไฟล์ XPS ที่คุณต้องการแปลงให้พร้อมใช้งานและจัดเก็บไว้ในไดเร็กทอรีที่กำหนด

## ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

## ขั้นตอนที่ 2: เริ่มต้นไดเรกทอรีเอกสาร

กำหนดเส้นทางไดเร็กทอรีที่เก็บเอกสารของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

อย่าลืมเปลี่ยน `"Your Document Directory"` โดยมีเส้นทางจริงไปยังไดเร็กทอรีที่มีเอกสาร XPS ของคุณ

### ขั้นตอนที่ 3: เปิด PDF และ XPS Streams

ขั้นตอนต่อไปคือการเริ่มต้นสตรีมสำหรับไฟล์ XPS อินพุตและไฟล์ PDF เอาท์พุต:

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าเส้นทางที่ถูกต้องสำหรับไฟล์ของคุณ

### ขั้นตอนที่ 4: โหลดเอกสาร XPS

ตอนนี้โหลดเอกสาร XPS ของคุณโดยใช้ไลบรารี Aspose.Page:

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### ขั้นตอนที่ 5: กำหนดค่าตัวเลือกการบันทึก PDF

ตั้งค่าตัวเลือกการบันทึกสำหรับ PDF ของคุณ รวมถึงคุณภาพของภาพและพารามิเตอร์การบีบอัด:

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100, // ตั้งค่าระดับคุณภาพ JPEG
    ImageCompression = PdfImageCompression.Jpeg, // ใช้การบีบอัด JPEG สำหรับรูปภาพ
    TextCompression = PdfTextCompression.Flate, // ใช้การบีบอัด Flate สำหรับข้อความ
    PageNumbers = new int[] { 1, 2, 6 } // ระบุหมายเลขหน้าที่จะรวมไว้
};
```

โปรดปรับพารามิเตอร์เหล่านี้ตามความต้องการของคุณ

### ขั้นตอนที่ 6: สร้างอุปกรณ์เรนเดอร์ PDF

สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ PDF:

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### ขั้นตอนที่ 7: บันทึกเอกสารเป็น PDF

สุดท้าย ให้บันทึกเอกสาร XPS เป็น PDF โดยใช้อุปกรณ์และตัวเลือกที่ระบุ:

```csharp
document.Save(device, options);
```

## บทสรุป

ขอแสดงความยินดี! คุณแปลงเอกสาร XPS เป็น PDF สำเร็จแล้วโดยใช้ Aspose.Page สำหรับ .NET ไลบรารีนี้ไม่เพียงแต่ช่วยลดความยุ่งยากในการแปลงเอกสารเท่านั้น แต่ยังมีความสามารถมากมายในการจัดการรูปแบบต่างๆ อีกด้วย

## คำถามที่พบบ่อย

### ฉันสามารถแปลงไฟล์ XPS หลายไฟล์เป็น PDF เดียวได้หรือไม่

แน่นอน! คุณสามารถทำซ้ำไฟล์ XPS หลายไฟล์และรวมเข้าเป็นเอกสาร PDF เดียวได้ โดยทำตามขั้นตอนการแปลงเดียวกัน

### Aspose.Page สำหรับ .NET รองรับรูปแบบเอาต์พุตอื่นใดอีกบ้าง

นอกเหนือจาก PDF แล้ว Aspose.Page สำหรับ .NET ยังรองรับรูปแบบต่างๆ มากมาย รวมถึง TIFF, JPEG และ PNG

### ฉันจะปรับแต่งรูปลักษณ์ของ PDF ที่แปลงแล้วได้อย่างไร

คุณสามารถปรับพารามิเตอร์ใน `PdfSaveOptions` วัตถุ เช่น คุณภาพ JPEG และการตั้งค่าการบีบอัด เพื่อให้ได้รูปลักษณ์ที่คุณต้องการ

### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Page สำหรับ .NET หรือไม่

ใช่ คุณสามารถทดลองใช้ Aspose.Page สำหรับ .NET พร้อมทดลองใช้งานฟรีได้ [ที่นี่](https://releases-aspose.com/).

### ฉันสามารถหาการสนับสนุนชุมชนสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

สำหรับการสนทนาและการสนับสนุนชุมชน โปรดไปที่ [ฟอรั่ม Aspose.Page](https://forum-aspose.com/c/page/39).