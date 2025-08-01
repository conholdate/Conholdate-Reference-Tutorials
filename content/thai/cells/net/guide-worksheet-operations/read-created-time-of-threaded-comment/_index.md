---
"description": "เรียนรู้วิธีการอ่านเวลาที่สร้างความคิดเห็นแบบเธรดในเวิร์กชีต Excel ได้อย่างง่ายดายโดยใช้ Aspose.Cells สำหรับ .NET ทำตามคำแนะนำโดยละเอียดของเราพร้อมคำแนะนำทีละขั้นตอน"
"linktitle": "อ่านเวลาที่สร้างของความคิดเห็นแบบเธรดด้วย Aspose.Cells"
"second_title": "API การประมวลผล Excel ของ Aspose.Cells .NET"
"title": "อ่านเวลาที่สร้างของความคิดเห็นแบบเธรดด้วย Aspose.Cells"
"url": "/th/cells/net/guide-worksheet-operations/read-created-time-of-threaded-comment/"
"weight": 21
---

## การแนะนำ

เมื่อทำงานกับไฟล์ Excel การจัดการความคิดเห็นอาจเป็นสิ่งสำคัญสำหรับการทำงานร่วมกันและการติดตามผลตอบรับ ในคู่มือนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการอ่านเวลาที่สร้างความคิดเห็นแบบเธรดในเวิร์กชีต Excel โดยใช้ Aspose.Cells สำหรับ .NET เครื่องมืออันทรงพลังนี้มอบวิธีการโต้ตอบกับไฟล์ Excel ได้อย่างมีประสิทธิภาพ ช่วยให้นักพัฒนาสามารถดึงข้อมูลโดยละเอียดจากความคิดเห็น ซึ่งมีประโยชน์อย่างยิ่งสำหรับการติดตามเวลาของความคิดเห็นในสถานการณ์การทำงานร่วมกัน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น สิ่งสำคัญคือต้องตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนาของคุณได้รับการตั้งค่าอย่างเหมาะสมเพื่อใช้ Aspose.Cells สำหรับ .NET สิ่งที่คุณต้องมีมีดังนี้:

1. Aspose.Cells สำหรับ .NET: คุณต้องติดตั้งไลบรารี Aspose.Cells คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก [เว็บไซต์ Aspose](https://releases-aspose.com/cells/net/).
2. IDE: Visual Studio (หรือ .NET IDE ใดๆ ที่คุณเลือก) เพื่อเขียนและดำเนินการโค้ดของคุณ
3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# จะทำให้การทำตามตัวอย่างต่างๆ ง่ายขึ้น
4. ไฟล์ Excel: สำหรับบทช่วยสอนนี้ เราจะใช้ไฟล์ Excel ชื่อ `ThreadedCommentsSample.xlsx`ซึ่งรวมถึงความคิดเห็นแบบเธรดบางส่วน ตรวจสอบให้แน่ใจว่าไฟล์ของคุณมีความคิดเห็นเพื่อประกอบการพิจารณา

## การนำเข้าแพ็คเกจที่จำเป็น

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นสำหรับการใช้งาน Aspose.Cells เปิดโปรเจกต์ C# ของคุณ และเพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์โค้ด:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

การ `Aspose.Cells` เนมสเปซช่วยให้คุณเข้าถึงคลาสและวิธีการทั้งหมดที่จำเป็นสำหรับการจัดการไฟล์ Excel ในขณะที่ `System` จำเป็นสำหรับฟังก์ชันทั่วไป เช่น เอาต์พุตและการจัดการข้อยกเว้น

## ขั้นตอนที่ 1: ระบุไดเรกทอรีของไฟล์ Excel

ขั้นตอนแรกคือการกำหนดเส้นทางที่เก็บไฟล์ Excel ของคุณ เส้นทางนี้จะใช้ในการค้นหาไฟล์ผ่านโปรแกรม

```csharp
// กำหนดไดเรกทอรีของไฟล์ Excel
string sourceDir = "Your Document Directory";
```

แทนที่ `"C:\\YourDirectory\\"` ด้วยเส้นทางจริงไปยังไฟล์ของคุณ วิธีนี้ช่วยให้โปรแกรมรู้ว่าจะค้นหาไฟล์ได้จากที่ใด `ThreadedCommentsSample-xlsx`.

## ขั้นตอนที่ 2: โหลดเวิร์กบุ๊ก

เมื่อตั้งค่าไดเรกทอรีเรียบร้อยแล้ว เราก็สามารถโหลดเวิร์กบุ๊ก Excel ได้แล้ว ซึ่งทำได้โดยการสร้างไฟล์ใหม่ `Workbook` วัตถุและส่งเส้นทางไฟล์ไปยังวัตถุนั้น

```csharp
// โหลดสมุดงาน Excel
Workbook workbook = new Workbook(sourceDir + "ThreadedCommentsSample.xlsx");
```

หากไม่พบไฟล์ในเส้นทางที่ระบุ จะมีการโยนข้อยกเว้น ดังนั้นโปรดตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ถูกต้องก่อนดำเนินการต่อ

## ขั้นตอนที่ 3: เข้าถึงแผ่นงานที่ต้องการ

เมื่อโหลดเวิร์กบุ๊กแล้ว คุณต้องเข้าถึงเวิร์กชีตที่มีความคิดเห็นแบบเธรด ในตัวอย่างนี้ เราจะดึงข้อมูลเวิร์กชีตแรกของเวิร์กบุ๊ก

```csharp
// เข้าถึงแผ่นงานแรกในสมุดงาน
Worksheet worksheet = workbook.Worksheets[0];
```

หากความคิดเห็นของคุณอยู่ในเวิร์กชีตอื่น ให้แก้ไขดัชนีให้เหมาะสม เช่น ใช้ `Worksheets[1]` สำหรับแผ่นงานที่สอง และอื่นๆ

## ขั้นตอนที่ 4: ดึงความคิดเห็นแบบเธรด

ในการดึงความคิดเห็นแบบเธรด คุณจะต้องระบุเซลล์ที่มีความคิดเห็น ในกรณีนี้ เราจะเน้นที่เซลล์ `A1`. วิธีการ `GetThreadedComments` ใช้เพื่อรับความคิดเห็นทั้งหมดที่เกี่ยวข้องกับเซลล์ที่ระบุ

```csharp
// รับความคิดเห็นแบบเธรดจากเซลล์ A1
ThreadedCommentCollection threadedComments = worksheet.Comments.GetThreadedComments("A1");
```

การดำเนินการนี้จะส่งคืนชุดความคิดเห็นแบบเธรดสำหรับเซลล์ A1 หากไม่มีความคิดเห็นอยู่ในเซลล์ที่ระบุ ชุดความคิดเห็นจะว่างเปล่า

## ขั้นตอนที่ 5: ทำซ้ำผ่านความคิดเห็นและแยกเวลาที่สร้างขึ้น

เมื่อดึงความคิดเห็นแบบเธรดแล้ว ขั้นตอนต่อไปคือการวนซ้ำผ่านคอลเลกชันและดึงรายละเอียดที่เกี่ยวข้อง รวมถึงเวลาที่สร้างสำหรับแต่ละความคิดเห็น เราสามารถทำสิ่งนี้ได้อย่างง่ายดายโดยการวนซ้ำผ่าน `ThreadedCommentCollection`-

```csharp
// วนซ้ำผ่านความคิดเห็นแบบเธรดแต่ละข้อและแสดงรายละเอียด
foreach (ThreadedComment comment in threadedComments)
{
    Console.WriteLine("Comment: " + comment.Notes);
    Console.WriteLine("Author: " + comment.Author.Name);
    Console.WriteLine("Created Time: " + comment.CreatedTime);
}
```

โค้ดนี้จะแสดงผลเนื้อหาของความคิดเห็น ชื่อผู้เขียน และเวลาที่สร้างความคิดเห็น `CreatedTime` คุณสมบัติส่งคืนค่าประทับเวลาเมื่อสร้างความคิดเห็นครั้งแรก

## ขั้นตอนที่ 6: แสดงข้อความยืนยัน

หลังจากอ่านความคิดเห็นแบบเธรดและแสดงข้อมูลเรียบร้อยแล้ว การเพิ่มข้อความยืนยันลงในโค้ดของคุณถือเป็นแนวทางปฏิบัติที่ดีเสมอ การทำเช่นนี้จะช่วยยืนยันว่ากระบวนการทำงานถูกต้อง

```csharp
// ข้อความยืนยัน
Console.WriteLine("Successfully retrieved threaded comment created times.");
```

ข้อความนี้จะถูกพิมพ์ไปยังคอนโซลเมื่อการดำเนินการโค้ดเสร็จสิ้น เพื่อยืนยันว่ากระบวนการทำงานโดยไม่มีข้อผิดพลาด

## บทสรุป

ตอนนี้คุณได้เรียนรู้วิธีการอ่านเวลาที่สร้างความคิดเห็นแบบเธรดในเวิร์กชีต Excel ได้อย่างง่ายดายโดยใช้ Aspose.Cells สำหรับ .NET ฟังก์ชันนี้มีประโยชน์อย่างยิ่งสำหรับการติดตามความคิดเห็นและข้อเสนอแนะในสภาพแวดล้อมการทำงานร่วมกัน พร้อมให้การประทับเวลาที่จำเป็นสำหรับกระบวนการตรวจสอบเอกสาร การปฏิบัติตามคู่มือนี้จะช่วยให้คุณดึงและใช้ประโยชน์จากข้อมูลความคิดเห็นในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ ช่วยเพิ่มประสิทธิภาพเวิร์กโฟลว์และยกระดับการทำงานร่วมกันกับสมาชิกในทีม

## คำถามที่พบบ่อย

### Aspose.Cells สำหรับ .NET คืออะไร?

Aspose.Cells สำหรับ .NET คือไลบรารีที่ครอบคลุมซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และจัดการไฟล์ Excel ในแอปพลิเคชัน .NET ได้ ไลบรารีนี้มีเครื่องมือที่ทรงประสิทธิภาพสำหรับการอ่าน เขียน และแก้ไขไฟล์ Excel ผ่านทางโปรแกรม

### ฉันจะดาวน์โหลด Aspose.Cells สำหรับ .NET ได้อย่างไร

คุณสามารถดาวน์โหลด Aspose.Cells เวอร์ชันล่าสุดสำหรับ .NET ได้จาก [เว็บไซต์ Aspose](https://releases-aspose.com/cells/net/).

### มีการทดลองใช้ฟรีหรือไม่?

ใช่ Aspose เสนอรุ่นทดลองใช้ Aspose.Cells สำหรับ .NET ฟรี คุณสามารถดาวน์โหลดรุ่นทดลองใช้ได้จาก [หน้าทดลองใช้ฟรี](https://releases-aspose.com/).

### ฉันสามารถเข้าถึงความคิดเห็นจากเซลล์อื่นได้หรือไม่

ใช่ คุณสามารถเข้าถึงความคิดเห็นแบบเธรดจากเซลล์ใดๆ ในเวิร์กชีตได้โดยการแก้ไขการอ้างอิงเซลล์ใน `GetThreadedComments` วิธีการ. เพียงแค่เปลี่ยน `"A1"` ไปยังการอ้างอิงเซลล์ที่ต้องการ

### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Cells ได้ที่ไหน

หากคุณต้องการความช่วยเหลือหรือมีคำถาม โปรดไปที่ [ฟอรั่ม Aspose](https://forum.aspose.com/c/cells/9)ซึ่งคุณสามารถหาคำตอบหรือขอความช่วยเหลือจากชุมชนได้