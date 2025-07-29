---
"description": "学习如何使用 Aspose.Words for .NET 无缝地将数字签名添加到您的 Word 文档中。本教程内容全面，涵盖从设置环境、插入签名行到保存和验证签名文档的所有内容。"
"linktitle": "创建并签署新的签名行"
"second_title": "Aspose.Words文档处理API"
"title": "创建并签署新的签名行"
"url": "/zh/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## 介绍

想要在 Word 文档中添加数字签名吗？使用 Aspose.Words for .NET，一切比您想象的还要简单！本教程将指导您完成环境设置、添加签名行以及对文档进行数字签名的步骤。让我们开始吧！

## 先决条件

在深入研究代码之前，请确保您已具备以下条件：

1. Aspose.Words for .NET - [点击此处下载](https://releases。aspose.com/words/net/).
2. .NET 开发环境 - Visual Studio 非常适合此任务。
3. 要签名的文件 - 您可以创建一个新的 Word 文档或使用现有的文档。
4. 证书文件-A `.pfx` 文件对于数字签名是必需的。
5. 签名行图像（可选） - 您可以包含签名的图像文件。

## 导入所需的命名空间

要使用 Aspose.Words 的功能，您需要导入以下命名空间：

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## 步骤1：设置文档目录

首先定义文档目录的路径。这将是您保存和检索文档的地方。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // 指定文档目录路径
```

## 步骤2：创建新文档

接下来，让我们创建一个新的Word文档。该文档将作为您签名行的画布。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入签名行

现在，使用 `DocumentBuilder` 类将签名行插入到您的文档中：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 步骤4：保存文档

插入签名行后，请保存文档。这是签名前至关重要的一步。

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## 步骤5：配置签名选项

设置签名流程的选项。这包括指定签名行 ID 以及与签名一起显示的可选图像。

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // 图像路径
};
```

## 步骤6：加载证书

加载签署文档所需的证书文件：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // 调整文件名和密码
```

## 步骤7：签署文件

最后，使用 `DigitalSignatureUtil` 类。用新名称保存已签名的文档以供将来参考。

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## 结论

恭喜！您已成功创建 Word 文档，添加签名行，并使用 Aspose.Words for .NET 对其进行数字签名。这款强大的工具简化了文档自动化流程，确保您的合同和正式文件得到安全签名和验证。

## 常见问题解答

### 我可以使用其他图像格式作为签名行吗？

是的，您可以使用各种图像格式，包括 PNG、JPG 和 BMP。

### 是否有必要使用 `.pfx` 申请证书？

是的， `.pfx` 文件是存储数字签名的证书和私钥的标准格式。

### 我可以在一份文档中添加多个签名行吗？

当然！您可以根据需要重复插入步骤来插入多个签名行。

### 如果我没有数字证书怎么办？

您需要从受信任的证书颁发机构获取数字证书或使用 OpenSSL 等工具生成数字证书。

### 如何验证文档中的数字签名？

您可以通过在 Word 中打开签名的文档并检查签名详细信息来验证数字签名，以确认其真实性和完整性。