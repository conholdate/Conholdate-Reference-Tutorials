---
"description": "เรียนรู้วิธีจัดการเบสไลน์การมอบหมายงานอย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ .NET คู่มือทีละขั้นตอนนี้ครอบคลุมการโหลดโปรเจ็กต์ การตั้งค่าเบสไลน์ การดึงข้อมูล การเปรียบเทียบเบสไลน์ และอื่นๆ เพื่อเพิ่มประสิทธิภาพเวิร์กโฟลว์การจัดการโครงการ"
"linktitle": "การจัดการฐานการมอบหมายงานใน Aspose.Tasks"
"second_title": "API ของ Aspose.Tasks .NET"
"title": "การเรียนรู้พื้นฐานการมอบหมายงานด้วย Aspose.Tasks สำหรับ .NET"
"url": "/th/tasks/net/master-advanced-features/mastering-assignment-baseline/"
"weight": 14
---

## การแนะนำ

การจัดการโครงการอย่างมีประสิทธิภาพขึ้นอยู่กับการติดตามและจัดการข้อมูลพื้นฐานการมอบหมายงานอย่างแม่นยำ ด้วย Aspose.Tasks สำหรับ .NET คุณจะได้รับชุดเครื่องมืออันทรงพลังที่จะช่วยเพิ่มประสิทธิภาพในการจัดการข้อมูลพื้นฐานการมอบหมายงาน เพื่อให้มีข้อมูลเชิงลึกเกี่ยวกับโครงการที่ดีขึ้น ในบทความนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการจัดการข้อมูลพื้นฐานการมอบหมายงาน เพื่อให้มั่นใจว่าโครงการของคุณยังคงดำเนินไปได้ตามแผน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเริ่มใช้งาน โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความเชี่ยวชาญด้านการเขียนโปรแกรม: มีความคุ้นเคยกับ C# ขั้นพื้นฐาน
- สภาพแวดล้อมการพัฒนา: ติดตั้งและกำหนดค่า Visual Studio
- Aspose.Tasks สำหรับไลบรารี .NET: ดาวน์โหลดจาก [การเปิดตัว Aspose.Tasks](https://releases-aspose.com/tasks/net/).
- ไฟล์โครงการ: การเข้าถึงไฟล์โครงการในรูปแบบ MPP

## นำเข้าเนมสเปซที่จำเป็น

ในการใช้ฟังก์ชันการทำงานของ Aspose.Tasks ให้รวมเนมสเปซต่อไปนี้ไว้ในไฟล์โปรเจ็กต์ของคุณ:

```csharp
using Aspose.Tasks;
using System;
```

## ขั้นตอนที่ 1: โหลดโครงการและตั้งค่าพื้นฐาน

การโหลดโปรเจ็กต์และการตั้งค่าพื้นฐานเป็นพื้นฐานในการจัดการพื้นฐานการมอบหมายงาน โค้ดต่อไปนี้แสดงวิธีการโหลดโปรเจ็กต์และตั้งค่าพื้นฐาน

```csharp
string dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ProjectSample.mpp");

// การกำหนดเส้นฐานของโครงการ
project.SetBaseline(BaselineType.Baseline);
Console.WriteLine("Baseline has been set successfully.");
```

## ขั้นตอนที่ 2: ดึงข้อมูลพื้นฐานการมอบหมาย

คุณสามารถดึงข้อมูลพื้นฐานโดยละเอียดสำหรับการมอบหมายทรัพยากรแต่ละรายการได้ ทำได้ดังนี้:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Cost: " + baseline.Cost);
        Console.WriteLine("Baseline Work: " + baseline.Work);
    }
}
```

## ขั้นตอนที่ 3: เปรียบเทียบเกณฑ์พื้นฐานระหว่างงานที่ได้รับมอบหมาย

Aspose.Tasks ช่วยให้คุณสามารถเปรียบเทียบค่าพื้นฐานด้วยโปรแกรมเพื่อประเมินความแตกต่างระหว่างการกำหนดทรัพยากร

```csharp
var assignment1 = project.ResourceAssignments.GetByUid(1);
var assignment2 = project.ResourceAssignments.GetByUid(2);

var baseline1 = assignment1.Baselines.First();
var baseline2 = assignment2.Baselines.First();

bool areEqual = baseline1.Equals(baseline2);
Console.WriteLine("Are the baselines equal? " + areEqual);
```

## ขั้นตอนที่ 4: แก้ไขรายละเอียดพื้นฐานด้วยโปรแกรม

คุณสามารถปรับเปลี่ยนข้อมูลพื้นฐานโดยใช้โปรแกรมเพื่อตอบสนองความต้องการของโครงการที่เปลี่ยนแปลงไปได้:

```csharp
var assignment = project.ResourceAssignments.GetByUid(3);
var baseline = assignment.Baselines.First();

baseline.Cost += 1000;  // การปรับต้นทุนพื้นฐาน
baseline.Work = baseline.Work.Add(TimeSpan.FromHours(10));  // การเพิ่มชั่วโมงการทำงาน

Console.WriteLine("Modified Baseline Cost: " + baseline.Cost);
Console.WriteLine("Modified Baseline Work: " + baseline.Work);
```

## บทสรุป

การจัดการเกณฑ์พื้นฐานการมอบหมายงานอย่างมีประสิทธิภาพเป็นสิ่งสำคัญต่อการควบคุมกำหนดการและงบประมาณของโครงการ Aspose.Tasks สำหรับ .NET ช่วยให้คุณมีเครื่องมือที่จำเป็นในการจัดการเกณฑ์พื้นฐานอย่างแม่นยำ ช่วยให้สามารถตัดสินใจโดยอาศัยข้อมูลได้

## คำถามที่พบบ่อย

### Aspose.Tasks สามารถจัดการฐานข้อมูลพื้นฐานหลายรายการสำหรับโครงการเดียวได้หรือไม่  
ใช่ Aspose.Tasks รองรับฐานข้อมูลพื้นฐานหลายรายการ ซึ่งช่วยให้สามารถติดตามเวอร์ชันต่างๆ ของโครงการได้อย่างยืดหยุ่น

### Aspose.Tasks เข้ากันได้กับไฟล์โปรเจ็กต์ที่ไม่ใช่ MPP ได้หรือไม่  
แน่นอน Aspose.Tasks รองรับรูปแบบต่างๆ เช่น XML, MPX และอื่นๆ

### ฉันสามารถอัปเดตข้อมูลพื้นฐานโดยอัตโนมัติได้หรือไม่  
ใช่ API อนุญาตให้ปรับเปลี่ยนค่าพื้นฐานแบบไดนามิกและอัตโนมัติผ่านโปรแกรมได้

### Aspose.Tasks ให้ข้อมูลพื้นฐานแบบแบ่งตามช่วงเวลาหรือไม่  
ใช่ สามารถเรียกค้นและวิเคราะห์ข้อมูลพื้นฐานแบบแบ่งช่วงเวลาโดยละเอียดได้

### ฉันสามารถเข้าถึงการสนับสนุนและเอกสารได้ที่ไหน  
เยี่ยม [เอกสารประกอบ Aspose.Tasks](https://reference.aspose.com/words/net/) หรือเข้าร่วม [ฟอรัมสนับสนุน Aspose](https://forum.aspose.com/c/words/8) เพื่อขอความช่วยเหลือ