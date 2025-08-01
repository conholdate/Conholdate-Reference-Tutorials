---
"description": "เรียนรู้วิธีการถ่ายโอนข้อมูลระหว่างเวิร์กบุ๊ก Excel ในแอปพลิเคชัน .NET ของคุณอย่างราบรื่นด้วย Aspose.Cells บทช่วยสอนที่ครอบคลุมนี้จะแนะนำคุณตลอดทุกขั้นตอนของการคัดลอกเวิร์กชีต"
"linktitle": "คัดลอกแผ่นงานระหว่างสมุดงาน Excel โดยใช้ Aspose.Cells"
"second_title": "API การประมวลผล Excel ของ Aspose.Cells .NET"
"title": "คัดลอกแผ่นงานระหว่างสมุดงาน Excel โดยใช้ Aspose.Cells"
"url": "/th/cells/net/mastering-worksheet-value-operations/copy-worksheet-between-workbooks/"
"weight": 13
---

## การแนะนำ

การถ่ายโอนข้อมูลระหว่างเวิร์กบุ๊ก Excel เป็นงานทั่วไปในแอปพลิเคชัน .NET โดยเฉพาะอย่างยิ่งในการสร้างรายงานหรือการจัดการเทมเพลต โชคดีที่การใช้ Aspose.Cells สำหรับ .NET ช่วยให้กระบวนการนี้ง่ายขึ้นและมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนต่างๆ ในการคัดลอกเวิร์กชีตจากเวิร์กบุ๊กหนึ่งไปยังอีกเวิร์กบุ๊กหนึ่ง ซึ่งจะช่วยให้คุณควบคุมการจัดการข้อมูลได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีเครื่องมือต่อไปนี้:

1. Aspose.Cells สำหรับไลบรารี .NET: ดาวน์โหลดไลบรารี [ที่นี่](https://releases-aspose.com/cells/net/).
2. Visual Studio หรือ IDE ที่คล้ายกัน: คุณจะใช้สิ่งนี้เพื่อเขียนและดำเนินการโค้ด .NET ของคุณ
3. ใบอนุญาต Aspose: เพื่อหลีกเลี่ยงข้อจำกัดในการประเมิน คุณสามารถ [สมัครทดลองใช้ฟรี](https://releases.aspose.com/) หรือได้รับ [ใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).

## แพ็คเกจนำเข้า

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโครงการของคุณ:

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

เนมสเปซเหล่านี้จะช่วยให้คุณสามารถเข้าถึงคลาสที่จำเป็นในการจัดการเวิร์กบุ๊กและเวิร์กชีต Excel ได้อย่างมีประสิทธิภาพ

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเร็กทอรี

ขั้นแรก ให้กำหนดไดเรกทอรีสำหรับเก็บเวิร์กบุ๊ก Excel ของคุณ วิธีนี้จะช่วยให้เข้าถึงไฟล์ได้ง่ายขึ้นในภายหลัง

```csharp
// ตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` กับเส้นทางที่แท้จริงของคุณ

## ขั้นตอนที่ 2: สร้างสมุดงานแรก

มาสร้างสมุดงานใหม่และเพิ่มแผ่นงานเข้าไปกัน

```csharp
// สร้างสมุดงานใหม่
Workbook excelWorkbook0 = new Workbook();
// เข้าถึงแผ่นงานแรกในสมุดงาน
Worksheet ws0 = excelWorkbook0.Worksheets[0];
```

## ขั้นตอนที่ 3: เพิ่มข้อมูลส่วนหัว

เติมแผ่นงานด้วยแถวส่วนหัวเพื่อแสดงชุดข้อมูลของคุณอย่างชัดเจน

```csharp
// เติมแถวส่วนหัว (A1:A4)
for (int i = 0; i < 5; i++)
{
    ws0.Cells[i, 0].PutValue($"Header Row {i}");
}
```

## ขั้นตอนที่ 4: เติมข้อมูลในแถวรายละเอียด

เพิ่มเนื้อหาโดยละเอียดเพื่อให้มีบริบทสำหรับแผ่นงานของคุณ

```csharp
// เติมแถวรายละเอียด (A5:A999)
for (int i = 5; i < 1000; i++)
{
    ws0.Cells[i, 0].PutValue($"Detail Row {i}");
}
```

## ขั้นตอนที่ 5: กำหนดค่าการตั้งค่าการพิมพ์

ตั้งค่าคอนฟิกหน้าเพื่อทำซ้ำแถวส่วนหัวในหน้าที่พิมพ์ ซึ่งมีประโยชน์อย่างยิ่งสำหรับรายงานขนาดใหญ่

```csharp
// กำหนดค่าการตั้งค่าหน้าเพื่อทำซ้ำแถวส่วนหัวในแต่ละหน้า
PageSetup pageSetup = ws0.PageSetup;
pageSetup.PrintTitleRows = "$1:$5";
```

## ขั้นตอนที่ 6: สร้างสมุดงานที่สอง

ขั้นตอนต่อไปคือสร้างเวิร์กบุ๊กที่สองที่จะรับเวิร์กชีตที่คัดลอกมา

```csharp
// สร้างสมุดงานอีกเล่มหนึ่ง
Workbook excelWorkbook1 = new Workbook();
// เข้าถึงแผ่นงานแรกในสมุดงาน
Worksheet ws1 = excelWorkbook1.Worksheets[0];
```

## ขั้นตอนที่ 7: เปลี่ยนชื่อแผ่นงานปลายทาง

เปลี่ยนชื่อเวิร์กชีตในเวิร์กบุ๊กที่สองเพื่อให้ระบุได้ง่าย

```csharp
// เปลี่ยนชื่อแผ่นงาน
ws1.Name = "MySheet";
```

## ขั้นตอนที่ 8: คัดลอกข้อมูลไปยังเวิร์กชีตปลายทาง

ใช้ประโยชน์จาก `Copy` วิธีการถ่ายโอนแผ่นงานทั้งหมดจากสมุดงานแรกไปยังสมุดงานที่สอง

```csharp
// คัดลอกข้อมูลจากเวิร์กชีตแรกของเวิร์กบุ๊กแรกไปยังเวิร์กชีตแรกของเวิร์กบุ๊กที่สอง
ws1.Copy(ws0);
```

## ขั้นตอนที่ 9: บันทึกสมุดงานสุดท้าย

สุดท้ายให้บันทึกสมุดงานที่แก้ไขแล้ว

```csharp
// บันทึกสมุดงานที่สอง
excelWorkbook1.Save(dataDir + "CopyWorksheetFromWorkbookToOther_out.xls");
```

## บทสรุป

และแล้วคุณก็ทำได้! คุณสามารถคัดลอกเวิร์กชีตจากเวิร์กบุ๊กหนึ่งไปยังอีกเวิร์กบุ๊กหนึ่งได้อย่างง่ายดายด้วย Aspose.Cells สำหรับ .NET วิธีนี้เหมาะอย่างยิ่งสำหรับชุดข้อมูลขนาดใหญ่ การสร้างเทมเพลต และการสร้างรายงาน 

## คำถามที่พบบ่อย

### ฉันสามารถคัดลอกแผ่นงานหลายแผ่นพร้อมกันได้หรือไม่  
ใช่ คุณสามารถทำซ้ำผ่านเวิร์กชีตหลายแผ่นและคัดลอกไปยังเวิร์กบุ๊กอื่นทีละแผ่นได้

### Aspose.Cells จะคงรูปแบบเดิมไว้ระหว่างการคัดลอกหรือไม่  
แน่นอน! `Copy` วิธีนี้จะรักษาการจัดรูปแบบและสไตล์ทั้งหมด

### ฉันจะเข้าถึงเซลล์เฉพาะในเวิร์กชีตที่คัดลอกได้อย่างไร  
คุณสามารถเข้าถึงเซลล์เฉพาะได้โดยใช้ `Cells` คุณสมบัติภายในแผ่นงาน

### จะเกิดอะไรขึ้นหากฉันต้องการคัดลอกเฉพาะค่าโดยไม่จัดรูปแบบ?  
คุณสามารถใช้วิธีการที่กำหนดเองเพื่อคัดลอกค่าทีละเซลล์ได้หากต้องการ

### ฉันสามารถทดสอบฟีเจอร์นี้โดยไม่ต้องมีใบอนุญาตได้หรือไม่  
ใช่ Aspose เสนอ [ทดลองใช้ฟรี](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติของมัน