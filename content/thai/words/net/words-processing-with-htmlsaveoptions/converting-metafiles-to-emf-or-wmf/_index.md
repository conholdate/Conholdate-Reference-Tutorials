---
"description": "เรียนรู้วิธีแปลงไฟล์ภาพ SVG เป็นรูปแบบ EMF หรือ WMF ในเอกสาร Word ได้อย่างราบรื่นด้วย Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดเพื่อผลลัพธ์ที่แม่นยำและเข้ากันได้"
"linktitle": "การแปลง Metafile เป็น EMF หรือ WMF"
"second_title": "API การประมวลผลเอกสาร Aspose.Words"
"title": "การแปลง Metafile เป็น EMF หรือ WMF"
"url": "/th/words/net/words-processing-with-htmlsaveoptions/converting-metafiles-to-emf-or-wmf/"
"weight": 10
---

## การแนะนำ

การจัดการและแปลงไฟล์ภาพอย่างมีประสิทธิภาพเป็นส่วนสำคัญอย่างยิ่งในการสร้างเอกสาร Word ระดับมืออาชีพ ในคู่มือนี้ เราจะเจาะลึกการใช้ Aspose.Words สำหรับ .NET เพื่อแปลงไฟล์ภาพ SVG เป็นรูปแบบ EMF (Enhanced Metafile) หรือ WMF (Windows Metafile) เพื่อการผสานรวมที่ราบรื่น บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนที่ชัดเจน เพื่อช่วยให้นักพัฒนาสามารถใช้งานการแปลงไฟล์ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้นสำหรับการแปลง SVG เป็น EMF หรือ WMF

เพื่อให้แน่ใจว่าประสบการณ์การพัฒนาจะราบรื่น โปรดยืนยันว่ามีการปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:

- Aspose.Words สำหรับ .NET: รับเวอร์ชันล่าสุดจาก [หน้าเผยแพร่ Aspose](https://releases-aspose.com/words/net/).
- .NET Framework: ตรวจสอบการติดตั้ง .NET Framework (หรือ .NET Core/5/6 ขึ้นอยู่กับสภาพแวดล้อมของคุณ)
- สภาพแวดล้อมการพัฒนา: แนะนำให้ใช้ Visual Studio เนื่องจากมีคุณลักษณะที่แข็งแกร่ง
- ความสามารถด้าน C#: ความคุ้นเคยพื้นฐานกับการเขียนโปรแกรม C# ถือเป็นสิ่งจำเป็น

## การนำเข้าเนมสเปซที่จำเป็น

ในโครงการของคุณ นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Words:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร

ตั้งค่าเส้นทางไดเรกทอรีที่จะจัดเก็บเอกสาร Word ของคุณ ซึ่งเป็นสิ่งสำคัญสำหรับการจัดการไฟล์เอาต์พุตอย่างมีประสิทธิภาพ

```csharp
string dataDir = @"C:\MyDocuments\";
```

แทนที่ `@"C:\MyDocuments\"` ตามเส้นทางที่คุณต้องการ

## ขั้นตอนที่ 2: เตรียมสตริง HTML ที่มี SVG

สร้างสตริง HTML ฝังเนื้อหา SVG ของคุณ ซึ่งจะทำให้ Aspose.Words สามารถเรนเดอร์และประมวลผล SVG ได้

```csharp
string htmlContent = 
    @"<html>
        <body>
            <svg xmlns='http://www.w3.org/2000/svg' ความกว้าง='300' ความสูง='100' viewBox='0 0 300 100'>
                <rect x='10' y='10' width='280' height='80' fill='blue' stroke='black' stroke-width='2'/>
                <text x='20' y='60' fill='white' font-size='20'>Aspose SVG Example</text>
            </svg>
        </body>
    </html>";
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการโหลด HTML

เพื่อให้แน่ใจว่ามีการจัดการการแปลง SVG อย่างเหมาะสม ให้กำหนดค่า `HtmlLoadOptions` กับ `ConvertSvgToEmf`-

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions
{
    ConvertSvgToEmf = true
};
```

## ขั้นตอนที่ 4: โหลด HTML ลงในเอกสาร Word

ใช้ตัวเลือกโหลดที่กำหนดค่าไว้เพื่อสร้าง `Document` วัตถุจากสตริง HTML

```csharp
using (MemoryStream htmlStream = new MemoryStream(Encoding.UTF8.GetBytes(htmlContent)))
{
    Document document = new Document(htmlStream, loadOptions);
}
```

## ขั้นตอนที่ 5: กำหนดค่าตัวเลือกการบันทึกสำหรับ EMF/WMF

ปรับแต่งตัวเลือกการบันทึกเพื่อกำหนดรูปแบบเมตาไฟล์ที่ต้องการ ที่นี่เราเลือก `HtmlMetafileFormat-Emf`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    MetafileFormat = HtmlMetafileFormat.Emf
};
```

## ขั้นตอนที่ 6: บันทึกเอกสาร

บันทึกเอกสารโดยใช้ตัวเลือกบันทึกที่ระบุ

```csharp
document.Save(dataDir + "ConvertedDocument.emf", saveOptions);
```

ไฟล์ผลลัพธ์จะมีเนื้อหา SVG ที่ถูกแปลงเป็นรูปแบบ EMF

## บทสรุป

บทช่วยสอนนี้ได้สาธิตวิธีการแปลงไฟล์ภาพ SVG เป็นรูปแบบ EMF หรือ WMF โดยใช้ Aspose.Words สำหรับ .NET การทำตามขั้นตอนเหล่านี้จะช่วยปรับปรุงความเข้ากันได้และความคมชัดของภาพในเอกสาร Word ของคุณ ไม่ว่าคุณจะกำลังสร้างเอกสารอัตโนมัติหรือจัดทำรายงานคุณภาพสูง วิธีนี้รับประกันผลลัพธ์ที่ราบรื่น

## คำถามที่พบบ่อย

### ฉันสามารถใช้วิธีนี้ในการประมวลผล SVG หลายไฟล์แบบแบตช์ได้หรือไม่
ใช่ คุณสามารถวนซ้ำผ่านไฟล์ HTML หลายไฟล์ที่มี SVG ได้ โดยใช้กระบวนการเดียวกันในลูป

### ความแตกต่างระหว่าง EMF และ WMF คืออะไร?
EMF เป็นเวอร์ชันปรับปรุงของ WMF ซึ่งรองรับกราฟิกที่ซับซ้อนและขนาดข้อมูลขนาดใหญ่ได้ดีขึ้น

### Aspose.Words เข้ากันได้กับ .NET Core ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET รองรับ .NET Core และ .NET 5/6 ทำให้เหมาะกับแอปพลิเคชันข้ามแพลตฟอร์มสมัยใหม่

### ฉันสามารถเก็บรูปแบบ SVG ต้นฉบับไว้ในผลลัพธ์ได้หรือไม่
ไม่ วิธีนี้แปลงไฟล์ SVG เป็น EMF/WMF โดยเฉพาะ อย่างไรก็ตาม คุณสามารถเก็บไฟล์ SVG ต้นฉบับไว้ได้โดยการฝังลงในเอกสารโดยตรงโดยไม่ต้องแปลงไฟล์

### ฉันสามารถดาวน์โหลด Aspose.Words รุ่นทดลองใช้ฟรีได้ที่ไหน
คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก [หน้าเผยแพร่ Aspose](https://releases-aspose.com/).