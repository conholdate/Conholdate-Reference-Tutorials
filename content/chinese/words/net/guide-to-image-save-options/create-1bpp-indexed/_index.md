---
"description": "本指南提供分步说明和示例代码，帮助您高效地创建 1Bpp 索引图像，用于存档、打印或节省空间。"
"linktitle": "创建 1Bpp 索引"
"second_title": "Aspose.Words文档处理API"
"title": "创建 1Bpp 索引"
"url": "/zh/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## 介绍

您是否曾经需要将 Word 文档转换为黑白图像？无论是出于数字存档、打印还是仅仅为了节省空间，将文档转换为 1Bpp 索引图像都非常实用。在本指南中，我们将介绍一种使用 Aspose.Words for .NET 实现此操作的简单方法。让我们开始吧！

## 先决条件

在深入研究代码之前，请确保您已具备以下条件：

- Aspose.Words for .NET：从以下位置下载并安装库 [这里](https://releases。aspose.com/words/net/).
- .NET 开发环境：虽然 Visual Studio 是一个流行的选择，但任何支持 .NET 的 IDE 都可以使用。
- 基本 C# 知识：熟悉 C# 会有所帮助，但我们会让事情变得简单。
- 示例 Word 文档：准备好要转换的文档。

## 步骤 1：导入必要的命名空间

要使用 Aspose.Words，您需要导入相关的命名空间。这对于访问文档操作所需的类和方法至关重要。

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 第 2 步：设置文档目录

指定存储 Word 文档的目录路径以及要保存转换后图像的目录路径。

```csharp
// 文档目录的路径
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## 步骤3：加载Word文档

将您的 Word 文档加载到 `Aspose.Words.Document` 对象。此对象允许您以编程方式操作文档。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 4：配置图像保存选项

接下来，设置 `ImageSaveOptions` 定义文档如何保存为图像。我们将它配置为 PNG 格式，并使用 1Bpp 索引颜色模式。

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // 仅转换第一页
    ImageColorMode = ImageColorMode.BlackAndWhite, // 设置为黑白
    PixelFormat = ImagePixelFormat.Format1bppIndexed // 使用 1Bpp 索引格式
};
```

- SaveFormat.Png：指定输出格式为 PNG。
- PageSet(1)：表示仅转换文档的第一页。
- ImageColorMode.BlackAndWhite：确保图像是黑白色的。
- ImagePixelFormat.Format1bppIndexed：将像素格式设置为 1Bpp 索引，优化空间。

## 步骤5：将文档保存为图像

最后，使用 `Save` 方法 `Document` 对象来保存转换后的图像。

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## 结论

恭喜！您已成功使用 Aspose.Words for .NET 将 Word 文档转换为 1Bpp 索引图像。此方法不仅高效，还能帮助您创建适用于各种应用程序的高对比度图像。欢迎将此功能集成到您的项目中。祝您编程愉快！

## 常见问题解答

### 什么是 1Bpp 索引图像？
1Bpp（每像素 1 位）索引图像是一种黑白图像格式，其中每个像素由一个位（0 或 1）表示。这种格式具有很高的空间效率，非常适合存档。

### 我可以一次转换 Word 文档的多页吗？
是的！只需修改 `PageSet` 财产 `ImageSaveOptions` 包括多个页面或将其设置为转换整个文档。

### 我需要许可证才能使用 Aspose.Words for .NET 吗？
是的，需要许可证才能使用全部功能。您可以获取 [此处为临时驾照](https://purchase。aspose.com/temporary-license/).

### 我可以将 Word 文档转换为哪些其他图像格式？
Aspose.Words 支持多种格式，包括 JPEG、BMP 和 TIFF。只需更改 `SaveFormat` 在 `ImageSaveOptions` 为您想要的格式。

### 在哪里可以找到有关 Aspose.Words for .NET 的更多文档？
如需完整文档，请访问 [Aspose.Words for .NET 文档页面](https://reference。aspose.com/words/net/).