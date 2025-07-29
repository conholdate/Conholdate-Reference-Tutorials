---
"description": "ค้นพบวิธีจัดการชุดข้อมูลขนาดใหญ่ใน Excel อย่างมีประสิทธิภาพด้วยการใช้ไลบรารี Aspose.Cells สำหรับ .NET คู่มือนี้อธิบายวิธีการทีละขั้นตอนในการระบุจำนวนแถวและคอลัมน์สูงสุดที่รองรับโดยรูปแบบไฟล์ XLS และ XLSX"
"linktitle": "ค้นหาแถวและคอลัมน์สูงสุดในรูปแบบ XLS และ XLSX"
"second_title": "API การประมวลผล Excel ของ Aspose.Cells .NET"
"title": "ค้นหาแถวและคอลัมน์สูงสุดในรูปแบบ XLS และ XLSX"
"url": "/th/cells/net/mastering-workbook-settings/find-maximum-rows-and-columns/"
"weight": 11
---

## การแนะนำ

การจัดการชุดข้อมูลขนาดใหญ่ใน Excel อาจเป็นเรื่องท้าทาย โดยเฉพาะอย่างยิ่งเมื่อพิจารณาถึงข้อจำกัดของรูปแบบไฟล์ต่างๆ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการใช้ไลบรารี Aspose.Cells สำหรับ .NET เพื่อกำหนดจำนวนแถวและคอลัมน์สูงสุดที่รองรับโดยรูปแบบ XLS (Excel 97-2003) และ XLSX (Excel 2007 ขึ้นไป) เมื่อจบหลักสูตร คุณจะพร้อมสำหรับการจัดการงานที่เกี่ยวข้องกับ Excel ได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. [.NET Framework](https://dotnet.microsoft.com/en-us/download) หรือ [.NET คอร์](https://dotnet.microsoft.com/en-us/download) ติดตั้งอยู่บนระบบของคุณ
2. [Aspose.Cells สำหรับ .NET](https://releases.aspose.com/cells/net/) ไลบรารีที่ดาวน์โหลดและอ้างอิงในโครงการของคุณ (คุณยังสามารถติดตั้งได้ผ่าน [นูเก็ต](https://www.nuget.org/packages/Aspose.Cells/)-

## การนำเข้าแพ็คเกจที่จำเป็น

เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์ C# ของคุณเพื่อนำเข้าแพ็คเกจที่จำเป็นจากไลบรารี Aspose.Cells:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## ขั้นตอนที่ 1: จำนวนแถวและคอลัมน์สูงสุดสำหรับรูปแบบ XLS

เริ่มต้นด้วยการค้นหาจำนวนแถวและคอลัมน์สูงสุดที่รองรับโดยรูปแบบ XLS

```csharp
// พิมพ์ข้อความเกี่ยวกับรูปแบบ XLS
Console.WriteLine("Maximum Rows and Columns supported by XLS format:");

// สร้างสมุดงานในรูปแบบ XLS
Workbook wb = new Workbook(FileFormatType.Excel97To2003);

// ดึงข้อมูลจำนวนแถวและคอลัมน์สูงสุด
int maxRows = wb.Settings.MaxRow + 1;
int maxCols = wb.Settings.MaxColumn + 1;

// แสดงผลลัพธ์
Console.WriteLine("Maximum Rows: " + maxRows);
Console.WriteLine("Maximum Columns: " + maxCols);
Console.WriteLine();
```

1. พิมพ์ข้อความเพื่อระบุว่าเรากำลังทำงานกับรูปแบบ XLS
2. สร้าง `Workbook` อินสแตนซ์สำหรับรูปแบบ XLS โดยใช้ `FileFormatType-Excel97To2003`.
3. รับจำนวนแถวและคอลัมน์สูงสุดด้วย `wb.Settings.MaxRow` และ `wb.Settings.MaxColumn`โดยเพิ่ม 1 เนื่องจากค่าเหล่านี้มีฐานเป็นศูนย์
4. ส่งออกจำนวนแถวและคอลัมน์สูงสุดไปยังคอนโซล

## ขั้นตอนที่ 2: จำนวนแถวและคอลัมน์สูงสุดสำหรับรูปแบบ XLSX

ต่อไปเราจะสำรวจจำนวนแถวและคอลัมน์สูงสุดที่รองรับโดยรูปแบบ XLSX

```csharp
// พิมพ์ข้อความเกี่ยวกับรูปแบบ XLSX
Console.WriteLine("Maximum Rows and Columns supported by XLSX format:");

// สร้างสมุดงานในรูปแบบ XLSX
wb = new Workbook(FileFormatType.Xlsx);

// ดึงข้อมูลจำนวนแถวและคอลัมน์สูงสุด
maxRows = wb.Settings.MaxRow + 1;
maxCols = wb.Settings.MaxColumn + 1;

// แสดงผลลัพธ์
Console.WriteLine("Maximum Rows: " + maxRows);
Console.WriteLine("Maximum Columns: " + maxCols);
```

1. พิมพ์ข้อความระบุว่าเรากำลังทำงานกับรูปแบบ XLSX
2. สร้าง `Workbook` อินสแตนซ์สำหรับรูปแบบ XLSX โดยใช้ `FileFormatType-Xlsx`.
3. ดึงข้อมูลและส่งออกจำนวนแถวและคอลัมน์สูงสุดเหมือนเดิม

## ขั้นตอนที่ 3: การแสดงข้อความแสดงความสำเร็จ

หลังจากดำเนินการตามขั้นตอนแล้ว เรามาแสดงว่าสำเร็จ

```csharp
Console.WriteLine("Execution completed successfully: Maximum Rows and Columns retrieval for both formats.");
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ไลบรารี Aspose.Cells สำหรับ .NET เพื่อค้นหาจำนวนแถวและคอลัมน์สูงสุดที่รองรับโดยรูปแบบไฟล์ XLS และ XLSX การทำความเข้าใจขีดจำกัดเหล่านี้เป็นสิ่งสำคัญสำหรับการจัดการข้อมูล Excel อย่างมีประสิทธิภาพ เพื่อให้มั่นใจว่าชุดข้อมูลของคุณสอดคล้องกับความสามารถของรูปแบบ

## คำถามที่พบบ่อย

### จำนวนแถวสูงสุดที่รองรับโดยรูปแบบ XLS คือเท่าใด
จำนวนแถวสูงสุดที่รองรับโดยรูปแบบ XLS คือ 65,536 แถว

### จำนวนคอลัมน์สูงสุดที่รองรับโดยรูปแบบ XLS คือเท่าใด
จำนวนคอลัมน์สูงสุดที่รองรับโดยรูปแบบ XLS คือ 256 คอลัมน์

### จำนวนแถวสูงสุดที่รองรับโดยรูปแบบ XLSX คือเท่าใด
จำนวนแถวสูงสุดที่รองรับโดยรูปแบบ XLSX คือ 1,048,576

### จำนวนคอลัมน์สูงสุดที่รองรับโดยรูปแบบ XLSX คือเท่าใด
จำนวนคอลัมน์สูงสุดที่รองรับโดยรูปแบบ XLSX คือ 16,384

### ฉันสามารถใช้ไลบรารี Aspose.Cells สำหรับ .NET ร่วมกับรูปแบบไฟล์ Excel อื่นๆ ได้หรือไม่
ใช่ Aspose.Cells สำหรับ .NET รองรับรูปแบบไฟล์ต่างๆ รวมถึง XLS, XLSX, ODS และอื่นๆ ตรวจสอบ [เอกสารประกอบ](https://reference.aspose.com/cells/net/) สำหรับรายละเอียดเกี่ยวกับคุณลักษณะและฟังก์ชันที่รองรับ