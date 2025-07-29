---
"description": "Hướng dẫn này cung cấp hướng dẫn từng bước và mã mẫu để giúp bạn tạo hình ảnh được lập chỉ mục 1Bpp một cách hiệu quả cho mục đích lưu trữ, in ấn hoặc tiết kiệm không gian."
"linktitle": "Tạo 1Bpp được lập chỉ mục"
"second_title": "API xử lý tài liệu Aspose.Words"
"title": "Tạo 1Bpp được lập chỉ mục"
"url": "/vi/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## Giới thiệu

Bạn đã bao giờ cần chuyển đổi một tài liệu Word sang ảnh đen trắng chưa? Dù là để lưu trữ kỹ thuật số, in ấn hay đơn giản là tiết kiệm dung lượng, việc chuyển đổi tài liệu sang ảnh được lập chỉ mục 1Bpp có thể cực kỳ hữu ích. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn một phương pháp đơn giản để thực hiện việc này bằng Aspose.Words for .NET. Hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo bạn có những điều sau:

- Aspose.Words cho .NET: Tải xuống và cài đặt thư viện từ [đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển .NET: Mặc dù Visual Studio là lựa chọn phổ biến nhưng bất kỳ IDE nào hỗ trợ .NET đều có thể hoạt động.
- Kiến thức cơ bản về C#: Sự quen thuộc với C# sẽ hữu ích, nhưng chúng ta sẽ giữ mọi thứ đơn giản.
- Mẫu tài liệu Word: Chuẩn bị sẵn một tài liệu để chuyển đổi.

## Bước 1: Nhập các không gian tên cần thiết

Để sử dụng Aspose.Words, bạn cần nhập các không gian tên liên quan. Điều này rất cần thiết để truy cập các lớp và phương thức cần thiết cho việc thao tác tài liệu.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Bước 2: Thiết lập thư mục tài liệu của bạn

Chỉ định đường dẫn đến thư mục lưu trữ tài liệu Word của bạn và nơi bạn muốn lưu hình ảnh đã chuyển đổi.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Bước 3: Tải tài liệu Word

Tải tài liệu Word của bạn vào `Aspose.Words.Document` đối tượng. Đối tượng này cho phép bạn thao tác tài liệu theo cách lập trình.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 4: Cấu hình tùy chọn lưu hình ảnh

Tiếp theo, thiết lập `ImageSaveOptions` để xác định cách tài liệu sẽ được lưu dưới dạng hình ảnh. Chúng tôi sẽ cấu hình để lưu ở định dạng PNG với chế độ màu được lập chỉ mục 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // Chỉ chuyển đổi trang đầu tiên
    ImageColorMode = ImageColorMode.BlackAndWhite, // Đặt thành đen trắng
    PixelFormat = ImagePixelFormat.Format1bppIndexed // Sử dụng định dạng được lập chỉ mục 1Bpp
};
```

- SaveFormat.Png: Chỉ định định dạng đầu ra sẽ là PNG.
- PageSet(1): Chỉ ra rằng chỉ có trang đầu tiên của tài liệu sẽ được chuyển đổi.
- ImageColorMode.BlackAndWhite: Đảm bảo hình ảnh có màu đen và trắng.
- ImagePixelFormat.Format1bppIndexed: Đặt định dạng pixel thành 1Bpp được lập chỉ mục, tối ưu hóa không gian.

## Bước 5: Lưu tài liệu dưới dạng hình ảnh

Cuối cùng, sử dụng `Save` phương pháp của `Document` đối tượng để lưu hình ảnh đã chuyển đổi.

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## Phần kết luận

Xin chúc mừng! Bạn đã chuyển đổi thành công một tài liệu Word thành hình ảnh được lập chỉ mục 1Bpp bằng Aspose.Words cho .NET. Phương pháp này không chỉ hiệu quả mà còn giúp bạn tạo ra hình ảnh có độ tương phản cao, phù hợp với nhiều ứng dụng khác nhau. Hãy thoải mái tích hợp chức năng này vào các dự án của bạn. Chúc bạn viết code vui vẻ!

## Câu hỏi thường gặp

### Hình ảnh được lập chỉ mục 1Bpp là gì?
Hình ảnh được lập chỉ mục 1Bpp (1 Bit trên mỗi Pixel) là định dạng hình ảnh đen trắng, trong đó mỗi pixel được biểu diễn bằng một bit duy nhất, là 0 hoặc 1. Định dạng này rất tiết kiệm không gian, lý tưởng để lưu trữ.

### Tôi có thể chuyển đổi nhiều trang của một tài liệu Word cùng một lúc không?
Vâng! Chỉ cần sửa đổi `PageSet` tài sản trong `ImageSaveOptions` để bao gồm nhiều trang hoặc thiết lập để chuyển đổi toàn bộ tài liệu.

### Tôi có cần giấy phép để sử dụng Aspose.Words cho .NET không?
Có, cần phải có giấy phép để sử dụng đầy đủ chức năng. Bạn có thể xin giấy phép [giấy phép tạm thời ở đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể chuyển đổi tài liệu Word của mình sang định dạng hình ảnh nào khác?
Aspose.Words hỗ trợ nhiều định dạng khác nhau, bao gồm JPEG, BMP và TIFF. Chỉ cần thay đổi `SaveFormat` trong `ImageSaveOptions` theo định dạng bạn mong muốn.

### Tôi có thể tìm thêm tài liệu về Aspose.Words cho .NET ở đâu?
Để có tài liệu đầy đủ, hãy truy cập [Trang tài liệu Aspose.Words cho .NET](https://reference.aspose.com/words/net/).