---
"description": "Khám phá cách kiểm soát liền mạch các tài nguyên bên ngoài trong sổ làm việc Excel bằng Aspose.Cells for .NET. Hướng dẫn toàn diện này sẽ hướng dẫn bạn từng bước, từ việc triển khai trình cung cấp luồng tùy chỉnh đến việc hiển thị bảng tính."
"linktitle": "Quản lý tài nguyên bên ngoài trong Excel với Aspose.Cells cho .NET"
"second_title": "API xử lý Excel của Aspose.Cells .NET"
"title": "Quản lý tài nguyên bên ngoài trong Excel với Aspose.Cells cho .NET"
"url": "/vi/cells/net/mastering-workbook-settings/manage-external-resources-in-excel/"
"weight": 10
---

## Giới thiệu

Khi làm việc với dữ liệu trong Excel, việc quản lý tài nguyên bên ngoài một cách liền mạch có thể cải thiện đáng kể chức năng của ứng dụng. Nếu bạn đang tìm cách kiểm soát hình ảnh và các thành phần bên ngoài khác trong sổ làm việc Excel bằng Aspose.Cells for .NET, bạn đã đến đúng nơi rồi! Hướng dẫn này sẽ hướng dẫn bạn từng bước, cho phép bạn triển khai một giải pháp tùy chỉnh để xử lý các tài nguyên này một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi đi sâu vào khía cạnh mã hóa, hãy đảm bảo bạn đã thiết lập những điều sau:

1. Visual Studio: Một IDE để viết và kiểm thử các ứng dụng .NET của bạn. Visual Studio được khuyến nghị vì hỗ trợ toàn diện và giao diện thân thiện với người dùng.
2. Aspose.Cells cho .NET: Tải xuống thư viện từ [Trang phát hành Aspose Cells](https://releases.aspose.com/cells/net/).
3. Kiến thức cơ bản về C#: Sự quen thuộc với các khái niệm về C# và .NET sẽ giúp bạn hiểu rõ hơn về cách triển khai.
4. Thiết lập dự án của bạn: Đảm bảo dự án của bạn tham chiếu đến thư viện Aspose.Cells, bạn có thể thêm thư viện này thông qua Trình quản lý gói NuGet trong Visual Studio.
5. Tệp mẫu: Chuẩn bị một tệp Excel mẫu có chứa các tài nguyên bên ngoài (ví dụ: hình ảnh được liên kết) để trình diễn.

Khi bạn đã có đủ tất cả các điều kiện tiên quyết này, hãy bắt đầu quản lý các tài nguyên bên ngoài bằng Aspose.Cells.

## Nhập gói
Để bắt đầu viết mã, bạn cần import các gói cần thiết vào tệp C#. Dưới đây là những gì bạn cần:
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using Aspose.Cells.Rendering;
using System.Drawing.Imaging;
```

## Bước 1: Xác định thư mục

Đầu tiên, hãy chỉ định thư mục nguồn và thư mục đầu ra nơi lưu trữ các tệp của bạn và nơi bạn muốn lưu các tệp đầu ra.

```csharp
// Xác định thư mục nguồn
static string sourceDir = @"C:\Path\To\Your\Documents\"; // Tùy chỉnh đường dẫn
// Xác định thư mục đầu ra
static string outputDir = @"C:\Path\To\Your\Output\";
```

Hãy đảm bảo thay thế các đường dẫn bằng các thư mục thực tế trên máy của bạn.

### Bước 2: Triển khai Giao diện IStreamProvider

Tiếp theo, tạo một lớp tùy chỉnh để triển khai `IStreamProvider` giao diện. Lớp này sẽ quản lý cách truy cập các tài nguyên bên ngoài như hình ảnh.

```csharp
class CustomStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        // Dọn dẹp tài nguyên nếu cần thiết
        options.Stream?.Close();
    }

    public void InitStream(StreamProviderOptions options)
    {
        // Mở luồng tệp cho tài nguyên bên ngoài
        options.Stream = new FileStream(Path.Combine(sourceDir, "image.png"), FileMode.Open, FileAccess.Read);
    }
}
```

Trong `InitStream` phương pháp, chúng tôi mở tệp đóng vai trò là tài nguyên bên ngoài của bạn và gán nó cho `Stream` tài sản.

### Bước 3: Tải tệp Excel

Bây giờ, hãy tải bảng tính Excel có chứa tài nguyên bên ngoài.

```csharp
public static void Execute()
{
    // Tải tệp Excel
    Workbook workbook = new Workbook(Path.Combine(sourceDir, "sample.xlsx"));
    
    // Chỉ định nhà cung cấp luồng tùy chỉnh
    workbook.Settings.StreamProvider = new CustomStreamProvider();
```

Đoạn mã này tải tệp Excel của bạn và chỉ định nhà cung cấp luồng tùy chỉnh để xử lý các tài nguyên bên ngoài.

### Bước 4: Truy cập vào Bảng tính

Sau khi tải bảng tính, bạn có thể dễ dàng truy cập vào bảng tính mong muốn.

```csharp
    // Truy cập vào bảng tính đầu tiên
    Worksheet worksheet = workbook.Worksheets[0];
```

Bạn có thể truy cập bất kỳ bảng tính nào bằng cách chỉ định mục lục của nó.

### Bước 5: Cấu hình tùy chọn hình ảnh và in

Xác định hình ảnh đầu ra mà bạn muốn hiển thị bằng cách cấu hình tùy chọn hình ảnh hoặc in.

```csharp
    // Chỉ định tùy chọn hình ảnh hoặc in
    ImageOrPrintOptions options = new ImageOrPrintOptions
    {
        OnePagePerSheet = true,
        ImageType = Drawing.ImageType.Png
    };
```

Chọn PNG sẽ đảm bảo đầu ra sắc nét và rõ ràng.

### Bước 6: Kết xuất bảng tính thành hình ảnh

Bây giờ đến phần thú vị — chuyển đổi bảng tính thành tệp hình ảnh!

```csharp
    // Tạo một trang tính và chuyển đổi trang tính thành hình ảnh
    SheetRender sheetRender = new SheetRender(worksheet, options);
    sheetRender.ToImage(0, Path.Combine(outputDir, "output.png"));
    
    Console.WriteLine("Excel sheet rendered successfully to an image!");
}
```

Mã này chuyển đổi toàn bộ bảng tính thành hình ảnh PNG, hình ảnh này sẽ được lưu vào thư mục đầu ra được chỉ định của bạn.

## Phần kết luận

Xin chúc mừng! Giờ đây, bạn đã học cách kiểm soát tài nguyên bên ngoài trong tệp Excel bằng Aspose.Cells for .NET. Chức năng này không chỉ nâng cao khả năng của ứng dụng mà còn đơn giản hóa cách bạn quản lý tập dữ liệu và bản trình bày. Bằng cách làm theo các bước được nêu ở trên, bạn có thể điều chỉnh giải pháp này cho phù hợp với các yêu cầu riêng của dự án.

## Câu hỏi thường gặp

### Aspose.Cells là gì?
Aspose.Cells là một thư viện mạnh mẽ được thiết kế cho các nhà phát triển .NET để tạo, thao tác và quản lý các tệp Excel mà không cần đến Microsoft Excel.

### Làm thế nào tôi có thể tải xuống Aspose.Cells cho .NET?
Bạn có thể tải xuống từ [Trang web Aspose](https://releases.aspose.com/cells/net/).

### Có bản dùng thử miễn phí không?
Có! Aspose cung cấp bản dùng thử miễn phí Aspose.Cells, có sẵn trên [trang phát hành](https://releases.aspose.com/cells/net/).

### Aspose.Cells hỗ trợ những loại tệp nào?
Aspose.Cells hỗ trợ nhiều định dạng Excel khác nhau, bao gồm XLS, XLSX, CSV, v.v.

### Tôi có thể tìm thấy hỗ trợ cho Aspose.Cells ở đâu?
Ghé thăm [Diễn đàn Aspose](https://forum.aspose.com/c/cells/9) để được hỗ trợ và hỗ trợ cộng đồng.