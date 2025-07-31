---
"description": "เรียนรู้วิธีการแยก ลบ และเพิ่มรายการลงในไฟล์ zip อย่างมีประสิทธิภาพด้วยโปรแกรม ซึ่งจะช่วยเพิ่มความสามารถในการจัดการไฟล์ของคุณ"
"linktitle": "แก้ไขไฟล์ Zip"
"second_title": "Aspose.Zip .NET API สำหรับการบีบอัดและการเก็บถาวรไฟล์"
"title": "แก้ไขไฟล์ Zip ด้วย Aspose.Zip สำหรับ .NET"
"url": "/th/zip/net/file-compress/modify-zip-files/"
"weight": 15
---

## การแนะนำ

ไฟล์ Zip มีความสำคัญอย่างยิ่งต่อการจัดระเบียบและบีบอัดข้อมูล แต่จะแก้ไขเนื้อหาในโปรแกรมได้อย่างไร? วิธีแก้ปัญหาอยู่ที่ Aspose.Zip สำหรับ .NET ซึ่งเป็นไลบรารีที่มีประสิทธิภาพที่ช่วยลดความซับซ้อนในการจัดการไฟล์ zip ด้วย C# ในบทช่วยสอนนี้ เราจะแนะนำคุณตั้งแต่การแตกไฟล์ ลบไฟล์ และเพิ่มไฟล์ zip ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึก ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Aspose.Zip สำหรับไลบรารี .NET: ติดตั้งไลบรารีในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/zip/net/).
   
2. ไดเรกทอรีเอกสาร: ตั้งค่าไดเรกทอรีสำหรับจัดเก็บไฟล์ zip ของคุณ แทนที่ `"Your Document Directory"` ในโค้ดพร้อมเส้นทางจริงของคุณ

## นำเข้าเนมสเปซที่จำเป็น

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: เปิดไฟล์ Zip ด้านนอก

เริ่มต้นด้วยการเปิดไฟล์ zip หลักของคุณ (zip ภายนอก):

```csharp
string dataDir = "Your Data Directory";
using (Archive outer = new Archive(dataDir + "outer.zip"))
{
    // ดำเนินการระบุรายการซิปด้านใน
}
```

## ขั้นตอนที่ 2: ระบุรายการ Zip ด้านใน

ขั้นตอนต่อไปคือระบุและเตรียมการลบไฟล์ zip ภายใน:

```csharp
List<ArchiveEntry> entriesToDelete = new List<ArchiveEntry>();
List<string> namesToInsert = new List<string>();
List<MemoryStream> contentToInsert = new List<MemoryStream>();

foreach (ArchiveEntry entry in outer.Entries)
{
    if (entry.Name.EndsWith(".zip", StringComparison.InvariantCultureIgnoreCase))
    {
        entriesToDelete.Add(entry);
        
        using (MemoryStream innerCompressed = new MemoryStream())
        {
            entry.Open().CopyTo(innerCompressed);
            
            // แยกรายการภายใน
            using (Archive inner = new Archive(innerCompressed))
            {
                foreach (ArchiveEntry ie in inner.Entries)
                {
                    namesToInsert.Add(ie.Name);
                    MemoryStream content = new MemoryStream();
                    ie.Open().CopyTo(content);
                    contentToInsert.Add(content);
                }
            }
        }
    }
}
```

## ขั้นตอนที่ 3: ลบรายการเก็บถาวรภายใน

เมื่อคุณรวบรวมรายการที่คุณต้องการแล้ว ให้ลบรายการ zip ด้านใน:

```csharp
foreach (ArchiveEntry e in entriesToDelete)
{
    outer.DeleteEntry(e);
}
```

## ขั้นตอนที่ 4: เพิ่มรายการที่แก้ไขลงใน Zip ด้านนอก

ตอนนี้คุณสามารถเพิ่มรายการที่เพิ่งแยกออกมาใหม่กลับเข้าไปในไฟล์ zip ภายนอกของคุณได้:

```csharp
for (int i = 0; i < namesToInsert.Count; i++)
{
    outer.CreateEntry(namesToInsert[i], contentToInsert[i]);
}
```

## ขั้นตอนที่ 5: บันทึกไฟล์ Zip ที่แก้ไขแล้ว

สุดท้ายให้บันทึกการเปลี่ยนแปลงของคุณลงในไฟล์ zip ใหม่:

```csharp
outer.Save(dataDir + "flatten.zip");
```

## บทสรุป

Aspose.Zip สำหรับ .NET มอบวิธีจัดการไฟล์ zip ที่มีประสิทธิภาพและตรงไปตรงมาด้วยโปรแกรม บทช่วยสอนนี้ครอบคลุมการแตกไฟล์ ลบไฟล์ และการเพิ่มรายการลงในไฟล์ zip ซึ่งแสดงให้เห็นถึงความคล่องตัวของไลบรารี สำรวจสถานการณ์ต่างๆ และพัฒนาทักษะการจัดการไฟล์ของคุณ!

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ร่วมกับภาษาการเขียนโปรแกรมอื่น ๆ ได้หรือไม่
Aspose.Zip ได้รับการออกแบบมาโดยเฉพาะสำหรับแอปพลิเคชัน .NET แต่ Aspose ก็มีไลบรารีที่คล้ายคลึงกันสำหรับภาษาการเขียนโปรแกรมต่างๆ เช่นกัน

### มีรุ่นทดลองใช้งานฟรีสำหรับ Aspose.Zip สำหรับ .NET หรือไม่
ใช่ มีให้ทดลองใช้ฟรีสำหรับดาวน์โหลด [ที่นี่](https://releases-aspose.com/).

### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร
เยี่ยมชม [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อการสนับสนุนและการหารือ

### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-conholdate.com/temporary-license/).

### ฉันสามารถค้นหาเอกสารสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน
เอกสารประกอบฉบับสมบูรณ์พร้อมให้บริการ [ที่นี่](https://reference-aspose.com/zip/net/).