---
"description": "了解如何使用 GroupDocs.Signature for .NET 對 PDF 文件進行元資料簽名，從而增強 PDF 文件的安全性和可追溯性。本綜合教程提供了清楚的說明。"
"linktitle": "使用元資料簽署 PDF 的指南"
"second_title": "GroupDocs.簽署 .NET API"
"title": "使用 GroupDocs.Signature 對包含元資料的 PDF 進行簽署的指南"
"url": "/zh-hant/signature/net/master-document-signing/signing-pdf-with-metadata/"
"weight": 11
---

## 介紹

在本教學中，我們將學習如何使用 GroupDocs.Signature for .NET 簽署 PDF 文件並新增元資料。添加元資料可以提供諸如作者、創建日期、文檔 ID 等基本信息，從而增強文檔的功能。

## 先決條件

在開始之前，請確保您具備以下條件：

1. GroupDocs.Signature for .NET：從以下位置下載 [這裡](https://releases。groupdocs.com/signature/net/).
2. PDF 文件：準備好要簽署的範例 PDF 文件。
3. C# 程式設計基礎：熟悉 C# 語法對於理解程式碼範例是必要的。

## 導入命名空間

首先導入所需的命名空間來存取必要的類別和方法：

```csharp
using System;
using System.IO;
using GroupDocs.Signature;
using GroupDocs.Signature.Domain;
using GroupDocs.Signature.Options;
```

## 步驟 1：載入 PDF 文檔

指定要簽署的PDF文件的路徑：

```csharp
string filePath = "sample.pdf";
```

## 第 2 步：指定輸出檔案路徑

定義已簽署且帶有元資料的 PDF 的儲存位置：

```csharp
string outputFilePath = Path.Combine("Your Document Directory", "SignPdfWithMetadata", "SignedWithMetadata.pdf");
```

## 步驟 3：建立簽章實例

初始化一個 `Signature` 帶有 PDF 文件路徑的實例：

```csharp
using (Signature signature = new Signature(filePath))
{
    // 簽名相關程式碼將放在這裡
}
```

## 步驟 4：定義元資料選項

創造 `MetadataSignOptions` 並新增元資料欄位及其值：

```csharp
MetadataSignOptions options = new MetadataSignOptions();
options
    .Add(new PdfMetadataSignature("Author", "Mr. Sherlock Holmes")) // 字串值
    .Add(new PdfMetadataSignature("CreatedOn", DateTime.Now))       // 日期時間值
    .Add(new PdfMetadataSignature("DocumentId", 123456))            // 整數值
    .Add(new PdfMetadataSignature("SignatureId", 123.456D))         // 雙倍值
    .Add(new PdfMetadataSignature("Amount", 123.456M))              // 十進制值
    .Add(new PdfMetadataSignature("Total", 123.456F));              // 浮點數值
```

## 第五步：簽署文件

使用指定的元資料選項對 PDF 文件進行簽署並儲存簽署的文件：

```csharp
SignResult result = signature.Sign(outputFilePath, options);
Console.WriteLine($"\nSource document signed successfully with {result.Succeeded.Count} signature(s).\nFile saved at {outputFilePath}.");
```

## 結論

在本教學中，我們介紹如何使用 GroupDocs.Signature for .NET 使用元資料簽署 PDF 文件。透過遵循這些步驟，您可以輕鬆地使用有價值的元資料來豐富您的 PDF 文件，從而提高其可追溯性和實用性。

## 常見問題解答

### 我可以為我的 PDF 文件新增自訂元資料欄位嗎？

是的，您可以使用 GroupDocs.Signature for .NET 指定欄位名稱及其對應的值來新增自訂元資料欄位。

### GroupDocs.Signature for .NET 是否與所有版本的 .NET Framework 相容？

GroupDocs.Signature for .NET 與各種版本的 .NET Framework 相容，確保靈活性和易於整合。

### GroupDocs.Signature 是否支援簽署 PDF 以外的其他文件格式？

是的，GroupDocs.Signature 支援多種文件格式，包括 Word、Excel、PowerPoint 等。

### 我可以使用 GroupDocs.Signature for .NET 批次簽署多個文件嗎？

絕對地！您可以透過遍歷文件清單並以程式設計方式套用簽名流程來批次簽署多個文件。

### GroupDocs.Signature 用戶可以獲得技術支援嗎？

是的，GroupDocs 透過其論壇提供專門的技術支援。您可以造訪支援論壇 [這裡](https://forum。groupdocs.com/c/signature/13).