---
"description": "Tìm hiểu cách tận dụng lớp trong Aspose.Tasks cho .NET để lọc các tác vụ dự án dựa trên nhiều điều kiện. Bằng cách kết hợp các tiêu chí như tác vụ tóm tắt và các thuộc tính không null."
"linktitle": "Lọc tác vụ VÀ thao tác trong Aspose.Tasks"
"second_title": "API Aspose.Tasks .NET"
"title": "Lọc tác vụ VÀ thao tác trong Aspose.Tasks"
"url": "/vi/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách thực hiện lọc nâng cao các tác vụ dự án trong Aspose.Tasks cho .NET bằng cách sử dụng `Util.And` lớp. Tính năng mạnh mẽ này cho phép các nhà phát triển lọc các tác vụ dựa trên nhiều tiêu chí một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Kiến thức cơ bản về lập trình C#.
2. Đã cài đặt Aspose.Tasks cho .NET. Nếu bạn chưa cài đặt, bạn có thể tải xuống từ [liên kết này](https://releases.aspose.com/tasks/net/).
3. Môi trường phát triển tích hợp (IDE) như Visual Studio để viết và chạy mã.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các không gian tên cần thiết vào dự án C# của mình. Thao tác này sẽ cho phép bạn truy cập các chức năng do Aspose.Tasks cung cấp.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Bước 1: Khởi tạo Dự án và Thu thập Nhiệm vụ

Trước tiên, hãy khởi tạo một dự án Aspose.Tasks và tập hợp tất cả các tác vụ trong đó. Để minh họa, chúng ta sẽ giả định có một tệp dự án có tên là `Project2.mpp`.

```csharp
// Đường dẫn đến thư mục tài liệu
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Thu thập tất cả các nhiệm vụ con
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Bước 2: Xác định Điều kiện Lọc

Trong bước này, chúng ta sẽ xác định các điều kiện để lọc tác vụ. Trong ví dụ này, chúng ta sẽ tạo hai điều kiện: một để lọc các tác vụ tóm tắt và một để đảm bảo các tác vụ không có giá trị null.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Bước 3: Kết hợp Điều kiện với Phép toán AND

Bước tiếp theo là kết hợp các điều kiện này bằng cách sử dụng `Util.And` lớp. Điều này cho phép chúng ta tạo ra một điều kiện tổng hợp yêu cầu cả hai tiêu chí.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Bước 4: Áp dụng Điều kiện kết hợp và Nhiệm vụ lọc

Bây giờ, hãy áp dụng điều kiện kết hợp cho các tác vụ đã thu thập để lọc ra các tác vụ cụ thể đáp ứng cả hai điều kiện.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Bước 5: Xuất các tác vụ đã lọc

Cuối cùng, chúng ta sẽ lặp lại các tác vụ đã lọc và đưa ra các chi tiết liên quan. Điều này sẽ giúp chúng ta hiểu được những tác vụ nào đáp ứng tiêu chí của mình.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách thực hiện các hoạt động lọc nâng cao trong Aspose.Tasks cho .NET bằng cách sử dụng `Util.And` lớp. Bằng cách kết hợp nhiều điều kiện, chúng ta có thể lọc các tác vụ một cách hiệu quả, do đó nâng cao tiện ích của các ứng dụng quản lý dự án.

## Câu hỏi thường gặp

### Aspose.Tasks dành cho .NET là gì?

Aspose.Tasks for .NET là một API toàn diện được thiết kế cho các nhà phát triển để thao tác các tệp Microsoft Project theo cách lập trình trong các ứng dụng .NET.

### Tôi có thể kết hợp nhiều hơn hai điều kiện bằng Util.And không?

Vâng! `Util.And` lớp này cho phép bạn kết hợp nhiều điều kiện, cho phép logic lọc phức tạp phù hợp với nhu cầu của bạn.

### Có phiên bản dùng thử miễn phí nào cho Aspose.Tasks không?

Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ [liên kết này](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu chi tiết về Aspose.Tasks ở đâu?

Tài liệu chi tiết có sẵn [đây](https://reference.aspose.com/tasks/net/).

### Tôi có thể tìm kiếm sự hỗ trợ cho Aspose.Tasks bằng cách nào?

Hỗ trợ có sẵn thông qua diễn đàn cộng đồng Aspose.Tasks, có thể được truy cập [đây](https://forum.aspose.com/c/tasks/15).