---
"description": "Khám phá cách dễ dàng trích xuất các tệp video nhúng từ bản trình bày PowerPoint bằng Aspose.Slides for .NET. Hướng dẫn từng bước toàn diện này bao gồm mọi thứ, từ thiết lập môi trường đến lưu video đã trích xuất."
"linktitle": "Trích xuất video từ slide PowerPoint"
"second_title": "API xử lý PowerPoint của Aspose.Slides .NET"
"title": "Trích xuất video từ slide PowerPoint bằng Aspose.Slides"
"url": "/vi/slides/net/extract-audio-and-video/extract-videos-from-powerpoint-slides/"
"weight": 14
---

## Giới thiệu

Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tương tác với các bài thuyết trình PowerPoint theo chương trình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình trích xuất video nhúng trong các slide PowerPoint bằng Aspose.Slides for .NET. 

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Aspose.Slides cho .NET: Tải và cài đặt thư viện từ [Trang web Aspose](https://purchase.aspose.com/buy).
- Bài thuyết trình PowerPoint: Chuẩn bị một tệp PowerPoint (ví dụ: `Video.pptx`) với video bạn muốn trích xuất.

## Không gian tên cần thiết

Để làm việc với Aspose.Slides cho .NET, bạn cần nhập các không gian tên phù hợp. Hãy thêm các nội dung sau vào mã của bạn:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

## Bước 1: Chỉ định thư mục tài liệu

Đầu tiên, hãy xác định đường dẫn đến bản trình bày PowerPoint của bạn:

```csharp
string dataDir = "Your Document Directory";
```

Thay thế `"Your Document Directory"` với đường dẫn thực tế đến thư mục chứa tệp PowerPoint của bạn.

## Bước 2: Tải bài thuyết trình

Tải bài thuyết trình PowerPoint vào `Presentation` sự vật:

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Điều này khởi tạo `Presentation` đối tượng có tệp PowerPoint bạn chỉ định.

## Bước 3: Lặp lại qua các slide và hình dạng

Tiếp theo, hãy duyệt qua từng trang chiếu trong bài thuyết trình và kiểm tra các khung hình video:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in slide.Shapes)
    {
        if (shape is VideoFrame videoFrame)
        {
            // Tiến hành trích xuất video
        }
    }
}
```

## Bước 4: Trích xuất dữ liệu video

Khi bạn tìm thấy một khung video, hãy trích xuất các thuộc tính và dữ liệu nhị phân của nó:

```csharp
IVideoFrame vf = (IVideoFrame)shape;  // Lưu trữ hình dạng dưới dạng khung video
string contentType = vf.EmbeddedVideo.ContentType;
Byte[] buffer = vf.EmbeddedVideo.BinaryData;

// Nhận phần mở rộng tập tin
string fileExtension = contentType.Substring(contentType.LastIndexOf('/') + 1);
```

## Bước 5: Lưu video

Cuối cùng, ghi dữ liệu video đã trích xuất vào một tệp:

```csharp
using (FileStream stream = new FileStream(dataDir + "ExtractedVideo." + fileExtension, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Đoạn mã này tạo một tệp mới trong thư mục bạn chỉ định và ghi dữ liệu video vào đó.

## Phần kết luận

Với Aspose.Slides for .NET, việc trích xuất video từ các slide PowerPoint trở nên vô cùng đơn giản. Bằng cách làm theo hướng dẫn này, bạn có thể dễ dàng quản lý nội dung đa phương tiện trong các ứng dụng .NET của mình, nâng cao trải nghiệm người dùng và chức năng.

## Câu hỏi thường gặp

### Aspose.Slides cho .NET là gì?
Aspose.Slides for .NET là một thư viện được thiết kế để hoạt động với các bài thuyết trình PowerPoint, cho phép người dùng tạo, chỉnh sửa và thao tác các tệp bài thuyết trình theo cách lập trình.

### Tôi có thể tìm tài liệu về Aspose.Slides cho .NET ở đâu?
Bạn có thể truy cập tài liệu đầy đủ [đây](https://reference.aspose.com/slides/net/).

### Aspose.Slides cho .NET có bản dùng thử miễn phí không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ [liên kết này](https://releases.aspose.com/).

### Làm thế nào tôi có thể xin được giấy phép tạm thời cho Aspose.Slides dành cho .NET?
Có thể yêu cầu cấp giấy phép tạm thời [đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể nhận hỗ trợ cho Aspose.Slides cho .NET ở đâu?
Hỗ trợ có sẵn thông qua [Diễn đàn Aspose.Slides](https://forum.aspose.com/).