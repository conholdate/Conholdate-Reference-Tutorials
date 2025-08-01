---
"description": "เรียนรู้วิธีบันทึกเอกสาร Microsoft OneNote เป็นไฟล์ PDF อย่างมีประสิทธิภาพโดยใช้ Aspose.Note สำหรับ .NET คู่มือนี้จะแนะนำคุณเกี่ยวกับข้อกำหนดเบื้องต้นที่จำเป็น และมีคำถามที่พบบ่อยที่เป็นประโยชน์"
"linktitle": "การบันทึกเอกสาร OneNote ในรูปแบบ PDF"
"second_title": "API ของ Aspose.Note .NET"
"title": "การบันทึกเอกสาร OneNote ในรูปแบบ PDF โดยใช้ Aspose.Note สำหรับ .NET"
"url": "/th/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการบันทึกเอกสารเป็น PDF โดยใช้ Aspose.Note สำหรับ .NET Aspose.Note เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft OneNote ได้ด้วยการเขียนโปรแกรม เราจะครอบคลุมข้อกำหนดเบื้องต้น การนำเข้าเนมสเปซ และให้คำแนะนำทีละขั้นตอนสำหรับการบันทึกเอกสารเป็น PDF ในเลย์เอาต์หน้าต่างๆ

## ข้อกำหนดเบื้องต้น
1. Visual Studio: ตรวจสอบให้แน่ใจว่ามีการติดตั้งแล้ว
2. Aspose.Note สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี
3. ความรู้ C#: ต้องมีความเข้าใจพื้นฐานของภาษา

## การนำเข้าเนมสเปซที่จำเป็น
ก่อนที่จะดำเนินการต่อ ให้ทำการนำเข้าเนมสเปซต่อไปนี้ลงในโค้ดของคุณ:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## ขั้นตอนที่ 1: บันทึกเป็น PDF ด้วยการตั้งค่าหน้าจดหมาย
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // อัปเดตเส้นทางนี้
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
โหลดเอกสาร OneNote และบันทึกเป็น PDF โดยใช้การตั้งค่าหน้าขนาด Letter

## ขั้นตอนที่ 2: บันทึกเป็น PDF ด้วยการตั้งค่าหน้า A4 (ไม่มีขีดจำกัดความสูง)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // อัปเดตเส้นทางนี้
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
คล้ายกับขั้นตอนที่ 1 แต่ใช้การตั้งค่าหน้ากระดาษ A4 โดยไม่มีข้อจำกัดด้านความสูง

## บทสรุป
บทช่วยสอนนี้สาธิตวิธีการแปลงไฟล์ OneNote เป็นรูปแบบ PDF โดยใช้ Aspose.Note ได้อย่างมีประสิทธิภาพ นักพัฒนาจะได้รับความยืดหยุ่นในการจัดการเอกสารด้วยการตั้งค่าหน้าต่างๆ

## คำถามที่พบบ่อย
### Aspose.Note สามารถจัดการไฟล์ OneNote ที่ซับซ้อนได้หรือไม่
ใช่ มันจัดการฟีเจอร์ต่างๆ ของไฟล์ OneNote ที่ซับซ้อนได้อย่างมีประสิทธิภาพ

### Aspose.Note เหมาะกับโครงการเชิงพาณิชย์หรือไม่?
ใช่ คุณสามารถใช้งานเพื่อการใช้งานเชิงพาณิชย์ได้หลังจากซื้อใบอนุญาต

### Aspose.Note มีการทดลองใช้ฟรีหรือไม่?
ใช่ มีช่วงทดลองใช้งานฟรีสำหรับการสำรวจ

### ฉันสามารถหาเอกสารสำหรับ Aspose.Note ได้ที่ไหน
เอกสารโดยละเอียดสามารถดูได้ที่ไซต์อ้างอิง Aspose

### ต้องการความช่วยเหลือเพิ่มเติมหรือไม่?
สำหรับคำถามและการสนับสนุน โปรดดูที่ฟอรัม Aspose.Note