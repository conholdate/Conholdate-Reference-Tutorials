---
"description": "Tìm hiểu cách thêm và tùy chỉnh đường xu hướng trong biểu đồ bằng Aspose.Slides cho .NET. Hướng dẫn toàn diện này bao gồm các đường xu hướng hàm mũ, tuyến tính, logarit, đa thức và trung bình động để nâng cao khả năng trực quan hóa dữ liệu của bạn."
"linktitle": "Đường xu hướng trong biểu đồ với Aspose.Slides cho .NET"
"second_title": "API xử lý PowerPoint của Aspose.Slides .NET"
"title": "Đường xu hướng trong biểu đồ với Aspose.Slides cho .NET"
"url": "/vi/slides/net/master-advanced-chart-customization/trend-lines-in-charts/"
"weight": 12
---

## Giới thiệu  

Thêm đường xu hướng vào biểu đồ là một kỹ thuật quan trọng để phân tích xu hướng dữ liệu và dự báo giá trị tương lai. Với Aspose.Slides for .NET, bạn có thể dễ dàng thêm và tùy chỉnh đường xu hướng vào biểu đồ trình bày, nâng cao khả năng trực quan hóa dữ liệu. Hướng dẫn này cung cấp hướng dẫn chi tiết về cách thêm đường xu hướng vào các loại biểu đồ khác nhau trong bản trình bày PowerPoint bằng Aspose.Slides for .NET.  

## Điều kiện tiên quyết  

Trước khi bắt đầu triển khai, hãy đảm bảo bạn đã thiết lập xong những điều sau:  

1. Aspose.Slides cho .NET: Tải xuống và cài đặt thư viện từ [trang tải xuống](https://releases.aspose.com/slides/net/).  
2. Môi trường phát triển: Sử dụng IDE như Visual Studio để viết mã.  
3. Kiến thức cơ bản về C#: Cần phải quen thuộc với lập trình C# để làm theo hướng dẫn này.  

## Nhập không gian tên bắt buộc  

Để bắt đầu, hãy nhập các không gian tên cần thiết vào dự án của bạn:  

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Bước 1: Thiết lập bài thuyết trình  

Đầu tiên, hãy khởi tạo một bản trình bày trống. Bản trình bày này sẽ đóng vai trò là vùng chứa biểu đồ của bạn.  

```csharp
string dataDir = "Your/Documents/Directory";

// Đảm bảo thư mục tồn tại
if (!System.IO.Directory.Exists(dataDir))
    System.IO.Directory.CreateDirectory(dataDir);

// Tạo một bài thuyết trình mới
Presentation presentation = new Presentation();
```

## Bước 2: Thêm biểu đồ vào trang chiếu  

Bây giờ, hãy thêm một trang chiếu và đưa vào biểu đồ cột nhóm để trực quan hóa dữ liệu của bạn.  

```csharp
// Thêm một slide trống
ISlide slide = presentation.Slides[0];

// Thêm biểu đồ cột cụm
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
```

## Bước 3: Điền dữ liệu biểu đồ  

Điền dữ liệu mẫu vào biểu đồ.  

```csharp
// Truy cập vào sổ làm việc dữ liệu biểu đồ mặc định
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// Cập nhật các danh mục và giá trị chuỗi mặc định
workbook.Clear(0);
workbook.GetCell(0, 0, 1).Value = "Category 1";
workbook.GetCell(0, 0, 2).Value = "Category 2";

chart.ChartData.Series[0].DataPoints[0].Value.Data = 4.5;
chart.ChartData.Series[0].DataPoints[1].Value.Data = 2.8;
```

## Bước 4: Thêm Đường xu hướng  

### Đường xu hướng hàm mũ  

```csharp
ITrendline expTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
expTrendLine.DisplayEquation = true;
expTrendLine.DisplayRSquaredValue = true;
```

### Đường xu hướng tuyến tính  

```csharp
ITrendline linTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
linTrendLine.Format.Line.FillFormat.FillType = FillType.Solid;
linTrendLine.Format.Line.FillFormat.SolidFillColor.Color = Color.Blue;
```

### Đường xu hướng logarit  

```csharp
ITrendline logTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Logarithmic);
logTrendLine.AddTextFrameForOverriding("Logarithmic Trend");
```

### Đường xu hướng trung bình động  

```csharp
ITrendline movAvgTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.MovingAverage);
movAvgTrendLine.Period = 3;
movAvgTrendLine.TrendlineName = "3-Point Moving Average";
```

### Đường xu hướng đa thức  

```csharp
ITrendline polyTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Polynomial);
polyTrendLine.Order = 2;
polyTrendLine.Forward = 1;
```

### Đường xu hướng điện  

```csharp
ITrendline powerTrendLine = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Power);
powerTrendLine.DisplayEquation = true;
powerTrendLine.Backward = 1;
```

## Bước 5: Lưu bài thuyết trình  

Cuối cùng, hãy lưu bản trình bày với tất cả các đường xu hướng đã được thêm vào biểu đồ của bạn.  

```csharp
presentation.Save(dataDir + "TrendLinesPresentation.pptx", SaveFormat.Pptx);
```

## Phần kết luận  

Với Aspose.Slides cho .NET, việc thêm đường xu hướng vào biểu đồ trở nên đơn giản. Tính năng này cho phép bạn trình bày xu hướng dữ liệu một cách hiệu quả và thêm nét chuyên nghiệp cho bài thuyết trình. Hãy làm theo các bước trên để kết hợp nhiều loại đường xu hướng khác nhau và nâng cao khả năng trực quan hóa dữ liệu của bạn.  

## Câu hỏi thường gặp  

### Tôi có thể tùy chỉnh giao diện của đường xu hướng không?  
Có, bạn có thể tùy chỉnh màu sắc, độ dày và kiểu dáng của các đường xu hướng bằng cách sử dụng `Format.Line` tài sản.  

### Có hỗ trợ cho các loại biểu đồ khác không?  
Có, Aspose.Slides for .NET hỗ trợ nhiều loại biểu đồ khác nhau, bao gồm biểu đồ thanh, biểu đồ tròn và biểu đồ đường.  

### Làm thế nào để hiển thị các phương trình và giá trị R bình phương?  
Cho phép `DisplayEquation` Và `DisplayRSquaredValue` các thuộc tính cho đường xu hướng để hiển thị các giá trị này trên biểu đồ.  

### Tôi có thể sử dụng Aspose.Slides cho .NET với các ngôn ngữ khác không?  
Có, thư viện này tương thích với bất kỳ ngôn ngữ nào hỗ trợ .NET, bao gồm VB.NET và F#.  

### Tôi có thể tìm thêm tài liệu ở đâu?  
Ghé thăm [Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/) để biết thêm thông tin.