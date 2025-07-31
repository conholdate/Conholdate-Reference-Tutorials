---
"description": "使用 Aspose.Cells for .NET 充分释放 Excel 转 PDF 的潜力。本指南将帮助您了解如何管理图像等外部资源，确保您的 PDF 完全符合您的格式要求。"
"linktitle": "使用 Aspose.Cells for .NET 控制外部资源"
"second_title": "Aspose.Cells .NET Excel 处理 API"
"title": "使用 Aspose.Cells for .NET 控制外部资源"
"url": "/zh/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## 介绍

在当今的数字环境中，将 Excel 电子表格转换为 PDF 文档是一项常见且必不可少的任务。无论您是准备报告、财务数据还是演示文稿，确保 PDF 能够反映预期的格式都至关重要。Aspose.Cells for .NET 提供了一个强大的库，可让您详细控制此转换过程，尤其是在处理图像等外部资源时。在本指南中，我们将探讨如何在 Excel 到 PDF 的转换过程中使用 Aspose.Cells 有效地管理外部资源。让我们开始吧！

## 先决条件

在我们开始之前，请确保您已准备好以下内容：

1. Visual Studio 或任何与 .NET 兼容的 IDE：这将是您的开发环境。
2. Aspose.Cells for .NET：如果您尚未安装，请访问 [Aspose 下载](https://releases.aspose.com/cells/net/) 页面获取最新版本。
3. C# 基础知识：熟悉 C# 将会很有帮助。如果您需要了解任何概念，请随时查阅。
4. 示例 Excel 文件：准备一个 Excel 文件，例如“samplePdfSaveOptions_StreamProvider.xlsx”，其中包含您想要转换的外部资源。
5. 用于测试的图像文件：在转换期间使用“newPdfSaveOptions_StreamProvider.png”之类的图像文件作为外部资源。

## 导入必要的包

首先，您需要从 Aspose.Cells 库导入所需的命名空间。在 C# 文件的顶部添加以下 using 指令：

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

这些命名空间为您的任务提供了必要的类和方法。

## 步骤 1：创建流提供程序类

首先，创建一个实现 `IStreamProvider` 接口。该类将使您能够控制外部资源的加载方式。

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // 将图像加载到内存流中
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream：当流关闭时调用此方法，当前记录调试消息。
- InitStream：该方法将外部图像文件读取为字节数组，将其转换为内存流，并将其分配给 `options.Stream` 财产。

## 步骤 2：设置源和输出目录

接下来，定义 Excel 文件和输出 PDF 的目录。

```csharp
// 源目录
string sourceDir = "Your Document Directory";
// 输出目录
string outputDir = "Your Document Directory";
```

代替 `"Your Document Directory"` 使用您的系统上文件所在的实际路径。

## 步骤3：加载Excel文件

现在，加载您想要创建 PDF 的 Excel 文件。

```csharp
// 加载包含外部图像的源 Excel 文件
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

这 `Workbook` Aspose.Cells 中的类代表您的 Excel 文件，其中可能包含各种外部资源，如图像。

## 步骤 4：设置 PDF 保存选项

在将工作簿保存为 PDF 之前，请指定所需的保存选项。

```csharp
// 指定 PDF 保存选项 - 流提供商
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // 将每张表保存在新页面上
};
```

这将创建一个 `PdfSaveOptions`，允许您自定义 PDF 格式。 `OnePagePerSheet` 选项确保每个 Excel 表出现在最终 PDF 中的单独页面上。

## 步骤 5：指定您的流媒体提供商

连接您的 `Workbook` 实例 `MyStreamProvider` 您之前创建的类。

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

此行确保在转换过程中遇到外部资源时，您的自定义提供程序将对其进行相应的管理。

## 步骤 6：将工作簿保存为 PDF

现在，将您的 Excel 工作簿保存为 PDF。

```csharp
// 将工作簿保存为 PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

通过调用 `Save` 方法在工作簿对象上并传递输出目录以及 PDF 选项，您可以将 Excel 文件转换为格式良好的 PDF。

## 步骤7：确认执行成功

最后，确认该过程已成功完成是一种很好的做法。

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

此消息将告知您操作的状态，提供有用的反馈。

## 结论

现在您已经掌握了使用 Aspose.Cells 在 Excel 到 PDF 转换过程中控制外部资源的流程！按照这些步骤，您可以确保您的文档准确包含图像和其他外部元素，从而每次都能获得完美的最终产品。

## 常见问题解答

### 什么是 Aspose.Cells？
Aspose.Cells 是一个面向 .NET 开发人员的强大库，可以创建、操作、转换和呈现各种格式的 Excel 文件。

### 如何下载 Aspose.Cells？
您可以从 [下载链接](https://releases。aspose.com/cells/net/).

### 我可以免费试用 Aspose.Cells 吗？
是的！您可以访问以下链接获取免费试用 [免费试用页面](https://releases。aspose.com/).

### 在哪里可以找到对 Aspose.Cells 的支持？
对于与支持相关的疑问，请访问 [Aspose 支持论坛](https://forum。aspose.com/c/cells/9).

### 如何获得 Aspose.Cells 的临时许可证？
您可以申请临时驾照 [这里](https://purchase。aspose.com/temporary-license/).