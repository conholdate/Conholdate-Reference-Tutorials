---
"description": "Khám phá sức mạnh của thao tác PDF với Aspose.PDF cho .NET trong hướng dẫn từng bước này. Tìm hiểu cách tạo tài liệu PDF hấp dẫn bằng lập trình bằng cách vẽ các hình chữ nhật được tô màu."
"linktitle": "Tạo hình chữ nhật tô màu"
"second_title": "Tài liệu tham khảo API Aspose.PDF cho .NET"
"title": "Tạo hình chữ nhật tô màu"
"url": "/vi/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## Giới thiệu

Bạn đã bao giờ muốn tạo ra những tệp PDF đẹp mắt bằng lập trình chưa? Nếu có, bạn đã đến đúng nơi rồi! Trong hướng dẫn này, chúng ta sẽ khám phá Aspose.PDF cho .NET, một thư viện mạnh mẽ giúp đơn giản hóa việc thao tác với tài liệu PDF. Hôm nay, chúng ta sẽ tập trung vào việc tạo một hình chữ nhật tô màu trong tệp PDF. Dù bạn là một lập trình viên dày dạn kinh nghiệm hay chỉ mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn từng bước một cách thân thiện và hấp dẫn. Vậy nên, hãy "vác mũ" lập trình lên và bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có những điều sau:

1. Visual Studio: Cài đặt Visual Studio trên máy của bạn vì đây là IDE tuyệt vời cho phát triển .NET.
2. Aspose.PDF cho .NET: Tải xuống và cài đặt thư viện Aspose.PDF từ [đây](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu các đoạn mã tốt hơn.

## Bước 1: Tạo một dự án mới

1. Mở Visual Studio và tạo một dự án Ứng dụng bảng điều khiển mới.
2. Đặt tên cho dự án của bạn một cách phù hợp.

## Bước 2: Thêm tham chiếu Aspose.PDF

1. Nhấp chuột phải vào dự án của bạn trong Solution Explorer.
2. Chọn Quản lý gói NuGet.
3. Tìm kiếm Aspose.PDF và cài đặt phiên bản mới nhất.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bây giờ chúng ta đã thiết lập xong mọi thứ, hãy cùng tìm hiểu về mã nhé!

## Bước 3: Thiết lập thư mục tài liệu của bạn

Chỉ định đường dẫn nơi tệp PDF của bạn sẽ được lưu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Thay thế `"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế trên máy của bạn nơi bạn muốn lưu tệp PDF.

## Bước 4: Tạo một phiên bản tài liệu

Khởi tạo một tài liệu PDF mới:

```csharp
// Tạo phiên bản Tài liệu
Document doc = new Document();
```

## Bước 5: Thêm trang vào tài liệu

Mỗi tệp PDF cần ít nhất một trang. Hãy thêm một trang:

```csharp
// Thêm trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
```

## Bước 6: Tạo một phiên bản đồ thị

MỘT `Graph` trường hợp này hoạt động như một tấm vải để vẽ hình dạng:

```csharp
// Tạo phiên bản đồ thị
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## Bước 7: Thêm biểu đồ vào trang

Đính kèm biểu đồ vào trang:

```csharp
// Thêm đối tượng đồ thị vào tập hợp đoạn văn của phiên bản trang
page.Paragraphs.Add(graph);
```

## Bước 8: Tạo một thể hiện hình chữ nhật

Xác định vị trí và kích thước của hình chữ nhật:

```csharp
// Tạo phiên bản Rectangle
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## Bước 9: Chỉ định màu tô

Chọn màu cho hình chữ nhật của bạn. Trong ví dụ này, chúng ta sẽ sử dụng màu đỏ:

```csharp
// Chỉ định màu tô cho đối tượng Đồ thị
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Bước 10: Thêm hình chữ nhật vào biểu đồ

Thêm hình chữ nhật vào biểu đồ:

```csharp
// Thêm đối tượng hình chữ nhật vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(rect);
```

## Bước 11: Lưu tài liệu PDF

Cuối cùng, lưu tài liệu của bạn vào thư mục đã chỉ định:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
```

## Bước 12: Thông báo xác nhận

In thông báo xác nhận để báo hiệu thành công:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bạn đã tạo thành công một hình chữ nhật tô màu trong tài liệu PDF bằng Aspose.PDF cho .NET. Thư viện mạnh mẽ này mở ra vô vàn khả năng xử lý PDF, cho phép bạn tạo ra những tài liệu ấn tượng bằng chương trình. Cho dù bạn đang tạo báo cáo, hóa đơn hay bất kỳ loại PDF nào khác, Aspose.PDF đều có thể đáp ứng nhu cầu của bạn.

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF cho .NET là một thư viện cho phép các nhà phát triển tạo, thao tác và chuyển đổi tài liệu PDF theo cách lập trình.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
Có, Aspose cung cấp phiên bản dùng thử miễn phí mà bạn có thể sử dụng để khám phá các tính năng của thư viện. Bạn có thể tải xuống [đây](https://releases.aspose.com/).

### Có cách nào để nhận được hỗ trợ cho Aspose.PDF không?
Chắc chắn rồi! Bạn có thể nhận được hỗ trợ thông qua diễn đàn Aspose [đây](https://forum.aspose.com/c/pdf/10).

### Làm thế nào tôi có thể mua Aspose.PDF?
Bạn có thể mua Aspose.PDF bằng cách truy cập trang mua hàng [đây](https://purchase.aspose.com/buy).

### Tôi có thể tạo những loại hình dạng nào bằng Aspose.PDF?
Bạn có thể tạo nhiều hình dạng khác nhau, bao gồm hình chữ nhật, hình tròn, đường thẳng, v.v. bằng cách sử dụng thư viện Aspose.PDF.