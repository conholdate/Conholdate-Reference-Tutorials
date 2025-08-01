---
"description": "ค้นพบวิธีควบคุมการมองเห็นเนื้อหาในเอกสาร Word อย่างมืออาชีพด้วย Aspose.Words สำหรับ .NET คู่มือทีละขั้นตอนนี้"
"linktitle": "จัดการการมองเห็นบุ๊กมาร์กในเอกสาร Word"
"second_title": "API การประมวลผลเอกสาร Aspose.Words"
"title": "จัดการการมองเห็นบุ๊กมาร์กในเอกสาร Word"
"url": "/th/words/net/mastering-bookmarks/manage-bookmark-visibility-word-document/"
"weight": 10
---

## การแนะนำ

คุณพร้อมที่จะยกระดับทักษะการจัดการเอกสารของคุณด้วย Aspose.Words สำหรับ .NET แล้วหรือยัง? ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์และกำลังพัฒนางานเอกสารอัตโนมัติ หรือเป็นบุคคลที่สนใจศึกษาการควบคุมไฟล์ Word ด้วยโปรแกรม คู่มือนี้ออกแบบมาเพื่อคุณโดยเฉพาะ วันนี้เราจะมาเจาะลึกวิธีการแสดงและซ่อนเนื้อหาตามบุ๊กมาร์กในเอกสาร Word เริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึก ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: ทุกเวอร์ชันที่เข้ากันได้กับ .NET
2. Aspose.Words สำหรับ .NET: ดาวน์โหลด [ที่นี่](https://releases-aspose.com/words/net/).
3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# ง่ายๆ ก็เพียงพอแล้ว
4. ตัวอย่างเอกสาร Word: เตรียมเอกสาร Word (เช่น "Bookmarks.docx") ที่มีบุ๊กมาร์กสำหรับบทช่วยสอนนี้

### สร้างโครงการใหม่

1. เปิด Visual Studio และสร้างโปรเจ็กต์ Console App (.NET Core) ใหม่ ตั้งชื่อว่า "BookmarkVisibilityManager"

### ติดตั้ง Aspose.Words สำหรับ .NET

เพิ่ม Aspose.Words ลงในโครงการของคุณผ่านตัวจัดการแพ็คเกจ NuGet:

1. ไปที่เครื่องมือ > ตัวจัดการแพ็กเกจ NuGet > จัดการแพ็กเกจ NuGet สำหรับโซลูชัน
2. ค้นหา "Aspose.Words"
3. ติดตั้งแพ็กเกจ

เมื่อคุณตั้งค่าโครงการของคุณเสร็จแล้ว ให้เราดำเนินการโหลดเอกสาร

## การนำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น ซึ่งจะมีคลาสและเมธอดที่จำเป็นสำหรับการจัดการเอกสาร Word ด้วย Aspose.Words

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

## ขั้นตอนที่ 1: การโหลดเอกสาร

ในการจัดการเอกสาร Word เราต้องโหลดไฟล์ก่อน วิธีทำมีดังนี้:

```csharp
// กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

สไนปเป็ตนี้จะกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณและโหลดเอกสารลงใน `Document` วัตถุ.

## ขั้นตอนที่ 2: แสดง/ซ่อนเนื้อหาที่คั่นหน้าไว้

ทีนี้ มาสร้างเมธอดสำหรับสลับการแสดงผลเนื้อหาตามบุ๊กมาร์กกัน เราจะเรียกเมธอดนี้ว่า `ShowHideBookmarkedContent`-

วิธีการนำไปใช้งานมีดังนี้:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    if (bm != null)
    {
        Node currentNode = bm.BookmarkStart;
        while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
        {
            if (currentNode.NodeType == NodeType.Run)
            {
                Run run = (Run)currentNode;
                run.Font.Hidden = isHidden;
            }
            currentNode = currentNode.NextSibling;
        }
    }
}
```

- การดึงข้อมูลบุ๊กมาร์ก: `Bookmark bm = doc.Range.Bookmarks[bookmarkName];` ดึงบุ๊กมาร์กที่ระบุ
- การข้ามโหนด: เราทำการวนซ้ำผ่านโหนดต่างๆ ภายในบุ๊กมาร์ก
- สลับการมองเห็น: สำหรับแต่ละ `Run` โหนด (แสดงส่วนของข้อความ) เราตั้งค่า `Hidden` ทรัพย์สินที่ขึ้นอยู่กับ `isHidden` พารามิเตอร์.

## ขั้นตอนที่ 3: การประยุกต์ใช้วิธีการ

ตอนนี้เรามีวิธีการพร้อมแล้ว เรามาใช้มันเพื่อแสดงหรือซ่อนเนื้อหาภายในบุ๊กมาร์กที่ระบุกัน:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true); // ซ่อนเนื้อหาภายใน "MyBookmark1"
```

บรรทัดนี้จะซ่อนเนื้อหาที่เกี่ยวข้องกับบุ๊กมาร์กชื่อ "MyBookmark1"

## ขั้นตอนที่ 4: การบันทึกเอกสาร

เมื่อคุณทำการเปลี่ยนแปลงแล้ว อย่าลืมบันทึกเอกสารที่แก้ไขแล้ว:

```csharp
doc.Save(dataDir + "UpdatedBookmarks.docx");
```

การดำเนินการนี้จะบันทึกเอกสารพร้อมการตั้งค่าการมองเห็นที่อัปเดต

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีแสดงและซ่อนเนื้อหาที่คั่นหน้าไว้ในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET สำเร็จแล้ว ไลบรารีอันทรงพลังนี้ช่วยลดความซับซ้อนในการจัดการเอกสาร ทำให้เหมาะอย่างยิ่งสำหรับการสร้างรายงานอัตโนมัติ การสร้างเทมเพลต หรือการทดลองใช้งานไฟล์ Word ขอให้สนุกกับการเขียนโค้ด!

## คำถามที่พบบ่อย

### ฉันสามารถสลับบุ๊กมาร์กหลายรายการพร้อมกันได้หรือไม่
ใช่ เพียงโทรไปที่ `ShowHideBookmarkedContent` วิธีการสำหรับแต่ละบุ๊กมาร์กที่คุณต้องการสลับ

### การซ่อนเนื้อหาจะส่งผลต่อโครงสร้างเอกสารหรือไม่?
ไม่ การซ่อนเนื้อหาจะส่งผลต่อการมองเห็นเท่านั้น เนื้อหาจะยังคงอยู่ในเอกสารเหมือนเดิม

### ฉันสามารถใช้วิธีนี้กับเนื้อหาประเภทอื่นได้หรือไม่?
วิธีนี้ได้รับการออกแบบมาโดยเฉพาะสำหรับการรันข้อความ สำหรับเนื้อหาประเภทอื่น คุณจะต้องปรับตรรกะการท่องโหนดให้เหมาะสม

### Aspose.Words สำหรับ .NET ฟรีหรือเปล่า?
Aspose.Words เสนอการทดลองใช้ฟรี [ที่นี่](https://releases.aspose.com/)แต่จำเป็นต้องมีใบอนุญาตเต็มรูปแบบสำหรับการใช้งานจริง คุณสามารถซื้อได้ [ที่นี่](https://purchase-aspose.com/buy).

### ฉันจะได้รับการสนับสนุนได้อย่างไรหากประสบปัญหา?
หากต้องการความช่วยเหลือ โปรดไปที่ฟอรัมชุมชน Aspose [ที่นี่](https://forum-aspose.com/c/words/8).