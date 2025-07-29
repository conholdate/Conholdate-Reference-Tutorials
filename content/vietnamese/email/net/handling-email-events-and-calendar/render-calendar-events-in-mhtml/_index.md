---
"description": "Kết xuất sự kiện lịch sang định dạng MHTML bằng Aspose.Email cho .NET. Tìm hiểu từng bước cách tùy chỉnh và lưu tệp MSG bằng C#."
"linktitle": "Hiển thị sự kiện lịch trong MHTML bằng Aspose.Email"
"second_title": "API xử lý email Aspose.Email .NET"
"title": "Hiển thị sự kiện lịch trong MHTML bằng Aspose.Email"
"url": "/vi/email/net/handling-email-events-and-calendar/render-calendar-events-in-mhtml/"
"weight": 15
---

## Giới thiệu

Aspose.Email for .NET là một thư viện mạnh mẽ để xử lý các tác vụ liên quan đến email trong các ứng dụng .NET. Một trường hợp sử dụng thú vị là hiển thị sự kiện lịch theo chương trình bằng C#. Cho dù bạn đang xây dựng tính năng tích hợp lịch hay tạo trình xem email tùy chỉnh, hướng dẫn này sẽ hướng dẫn bạn cách hiển thị sự kiện lịch sang định dạng MHTML một cách chính xác và tùy chỉnh.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng chúng ta đã chuẩn bị mọi thứ để làm theo hướng dẫn này:

1. Aspose.Email cho Thư viện .NET: Tải xuống phiên bản mới nhất của thư viện từ [Trang tải xuống Aspose.Email cho .NET](https://releases.aspose.com/email/net/).
2. Môi trường phát triển: Visual Studio (hoặc IDE C# mà bạn thích) được cài đặt trên hệ thống của bạn.
3. Giấy phép: Nhận giấy phép hợp lệ cho Aspose.Email. Để đánh giá, bạn có thể sử dụng [giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
4. Tệp MSG mẫu: Tệp MSG sự kiện lịch. Bạn có thể sử dụng bất kỳ `.msg` tệp có sự kiện lịch, chẳng hạn như "Cuộc họp có sự kiện định kỳ.msg."

## Nhập gói

Để bắt đầu, hãy đưa các không gian tên cần thiết vào dự án của bạn. 

```csharp
using System;
using Aspose.Email;
using Aspose.Email.Mht;
```

Bây giờ, chúng ta hãy cùng xem hướng dẫn từng bước nhé!

## Bước 1: Tải tệp MSG sự kiện lịch

Đầu tiên, chúng ta tải tệp MSG chứa sự kiện lịch. Bước này rất quan trọng vì nó đóng vai trò là đầu vào để hiển thị sự kiện sang định dạng MHTML.


```csharp
string dataDir = "Your Data Directory";
string fileName = "Meeting with Recurring Occurrences.msg";

// Tải tệp MSG
MailMessage msg = MailMessage.Load(dataDir + fileName);
```

- `dataDir`: Chỉ định thư mục lưu trữ tệp MSG của bạn.
- `fileName`: Tên của tệp sự kiện lịch.
- `MailMessage.Load`: Đọc tệp và tải nó vào `MailMessage` sự vật.

## Bước 2: Cấu hình Tùy chọn Lưu MHTML

Tiếp theo, chúng tôi cấu hình các tùy chọn để hiển thị sự kiện lịch sang định dạng MHTML. Điều này bao gồm việc bật các định dạng, tiêu đề và thuộc tính cụ thể khác để tùy chỉnh.

```csharp
MhtSaveOptions options = new MhtSaveOptions
{
    MhtFormatOptions = MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent
};
```

- `MhtSaveOptions`: Biểu thị các thiết lập để lưu tệp MHTML.
- `MhtFormatOptions`: Cấu hình các tùy chọn như bao gồm tiêu đề và hiển thị sự kiện lịch.

## Bước 3: Tùy chỉnh mẫu hiển thị

Ở đây, chúng tôi xác định cách các thuộc tính cụ thể, chẳng hạn như thời gian bắt đầu sự kiện, sẽ xuất hiện trong kết quả đầu ra. Bước này cho phép tạo ra kết quả đầu ra có khả năng tùy chỉnh cao và dễ đọc.


```csharp
if (options.FormatTemplates.ContainsKey(MhtTemplateName.Start))
    options.FormatTemplates[MhtTemplateName.Start] = @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>";
else
    options.FormatTemplates.Add(MhtTemplateName.Start, @"<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

- `MhtTemplateName.Start`: Chỉ đến thuộc tính "Bắt đầu" của sự kiện lịch.
- `options.FormatTemplates`: Tùy chỉnh mẫu hiển thị cho các thuộc tính cụ thể.

## Bước 4: Lưu sự kiện lịch dưới dạng MHTML

Cuối cùng, lưu sự kiện lịch vào tệp MHTML với các tùy chọn đã cấu hình.


```csharp
msg.Save(dataDir + "Meeting with Recurring Occurrences.mhtml", options);
```

- `msg.Save`: Lưu tin nhắn theo định dạng và vị trí đã chỉ định.
- `Meeting with Recurring Occurrences.mhtml`: Tên tập tin đầu ra.

## Phần kết luận

Việc hiển thị sự kiện lịch bằng Aspose.Email cho .NET vừa hiệu quả vừa có khả năng tùy chỉnh cao. Bằng cách làm theo các bước trên, bạn có thể dễ dàng chuyển đổi sự kiện lịch sang tệp MHTML, hoàn chỉnh với định dạng được tùy chỉnh.

## Câu hỏi thường gặp

### MHTML là gì?
MHTML là định dạng tệp lưu trữ web chứa HTML và các tài nguyên liên quan như hình ảnh, phù hợp để hiển thị và chia sẻ các sự kiện lịch.

### Tôi có thể hiển thị các sự kiện định kỳ không?
Có! Aspose.Email hỗ trợ hiển thị các sự kiện định kỳ, đảm bảo mọi chi tiết đều được ghi lại chính xác.

### Có cần giấy phép không?
Có, cần phải có giấy phép hợp lệ. Bạn có thể yêu cầu [giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.

### Tôi có thể thêm thuộc tính tùy chỉnh vào đầu ra không?
Chắc chắn rồi! Bạn có thể tùy chỉnh các mẫu cho các thuộc tính bổ sung bằng cách sử dụng `FormatTemplates` bộ sưu tập.

### Làm thế nào để khắc phục sự cố?
Ghé thăm [Diễn đàn hỗ trợ Aspose.Email](https://forum.aspose.com/c/email/12/) để được hỗ trợ chuyên môn.