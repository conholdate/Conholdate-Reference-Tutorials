---
"description": "Khám phá cách kiểm soát khả năng hiển thị nội dung trong tài liệu Word một cách chuyên nghiệp bằng Aspose.Words cho .NET. Hướng dẫn từng bước này."
"linktitle": "Quản lý khả năng hiển thị dấu trang trong tài liệu Word"
"second_title": "API xử lý tài liệu Aspose.Words"
"title": "Quản lý khả năng hiển thị dấu trang trong tài liệu Word"
"url": "/vi/words/net/mastering-bookmarks/manage-bookmark-visibility-word-document/"
"weight": 10
---

## Giới thiệu

Bạn đã sẵn sàng nâng cao kỹ năng thao tác tài liệu với Aspose.Words for .NET chưa? Cho dù bạn là một lập trình viên dày dạn kinh nghiệm tự động hóa các tác vụ tài liệu hay một cá nhân tò mò muốn khám phá khả năng kiểm soát theo chương trình trên các tệp Word, hướng dẫn này được thiết kế riêng cho bạn. Hôm nay, chúng ta sẽ tìm hiểu sâu hơn về cách hiển thị và ẩn nội dung dựa trên dấu trang trong tài liệu Word. Hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Visual Studio: Bất kỳ phiên bản nào tương thích với .NET.
2. Aspose.Words cho .NET: Tải xuống [đây](https://releases.aspose.com/words/net/).
3. Kiến thức cơ bản về C#: Có khả năng viết các chương trình C# đơn giản là đủ.
4. Một tài liệu Word mẫu: Chuẩn bị một tài liệu Word (ví dụ: "Bookmarks.docx") có chứa dấu trang cho hướng dẫn này.

### Tạo một dự án mới

1. Mở Visual Studio và tạo một dự án Console App (.NET Core) mới. Đặt tên cho dự án là "BookmarkVisibilityManager".

### Cài đặt Aspose.Words cho .NET

Thêm Aspose.Words vào dự án của bạn thông qua Trình quản lý gói NuGet:

1. Điều hướng đến Công cụ > Trình quản lý gói NuGet > Quản lý gói NuGet cho Giải pháp.
2. Tìm kiếm "Aspose.Words".
3. Cài đặt gói.

Sau khi thiết lập xong dự án, chúng ta hãy tiến hành tải tài liệu.

## Nhập không gian tên

Bắt đầu bằng cách nhập các không gian tên thiết yếu. Chúng cung cấp các lớp và phương thức cần thiết để thao tác với tài liệu Word bằng Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

## Bước 1: Tải tài liệu

Để thao tác với tài liệu Word, trước tiên chúng ta cần tải nó. Cách thực hiện như sau:

```csharp
// Xác định đường dẫn đến thư mục tài liệu của bạn.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

Đoạn mã này thiết lập đường dẫn đến thư mục tài liệu của bạn và tải tài liệu vào `Document` sự vật.

## Bước 2: Hiển thị/Ẩn nội dung đã đánh dấu

Bây giờ, hãy tạo một phương thức để chuyển đổi chế độ hiển thị nội dung dựa trên dấu trang. Chúng ta sẽ gọi phương thức này là `ShowHideBookmarkedContent`.

Sau đây là cách triển khai phương pháp:

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

- Truy xuất dấu trang: `Bookmark bm = doc.Range.Bookmarks[bookmarkName];` lấy dấu trang đã chỉ định.
- Duyệt nút: Chúng ta lặp qua các nút trong dấu trang.
- Chuyển đổi hiển thị: Đối với mỗi `Run` nút (đại diện cho một đoạn văn bản), chúng tôi thiết lập nó `Hidden` tài sản dựa trên `isHidden` tham số.

## Bước 3: Áp dụng phương pháp

Bây giờ chúng ta đã có phương pháp, hãy sử dụng nó để hiển thị hoặc ẩn nội dung trong một dấu trang cụ thể:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true); // Ẩn nội dung trong "MyBookmark1"
```

Dòng này sẽ ẩn nội dung liên quan đến dấu trang có tên "MyBookmark1".

## Bước 4: Lưu tài liệu

Sau khi thực hiện thay đổi, đừng quên lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "UpdatedBookmarks.docx");
```

Thao tác này sẽ lưu tài liệu với cài đặt hiển thị đã cập nhật.

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách hiển thị và ẩn nội dung được đánh dấu trong tài liệu Word bằng Aspose.Words for .NET. Thư viện mạnh mẽ này giúp đơn giản hóa thao tác tài liệu, lý tưởng cho việc tự động hóa báo cáo, tạo mẫu hoặc thử nghiệm với các tệp Word. Chúc bạn lập trình vui vẻ!

## Câu hỏi thường gặp

### Tôi có thể chuyển đổi nhiều dấu trang cùng lúc không?
Vâng, chỉ cần gọi `ShowHideBookmarkedContent` phương pháp cho mỗi dấu trang bạn muốn chuyển đổi.

### Việc ẩn nội dung có ảnh hưởng đến cấu trúc của tài liệu không?
Không, việc ẩn nội dung chỉ ảnh hưởng đến khả năng hiển thị của nội dung đó; nội dung vẫn được giữ nguyên trong tài liệu.

### Tôi có thể sử dụng phương pháp này cho các loại nội dung khác không?
Phương pháp này được thiết kế riêng cho các chuỗi văn bản. Đối với các loại nội dung khác, bạn sẽ cần điều chỉnh logic duyệt nút cho phù hợp.

### Aspose.Words cho .NET có miễn phí không?
Aspose.Words cung cấp bản dùng thử miễn phí [đây](https://releases.aspose.com/), nhưng cần có giấy phép đầy đủ để sử dụng sản xuất. Bạn có thể mua nó [đây](https://purchase.aspose.com/buy).

### Tôi có thể nhận được hỗ trợ như thế nào nếu gặp vấn đề?
Để được hỗ trợ, hãy truy cập diễn đàn cộng đồng Aspose [đây](https://forum.aspose.com/c/words/8).