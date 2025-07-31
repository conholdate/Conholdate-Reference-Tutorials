---
"description": "了解如何使用 GroupDocs.Signature for .NET 對帶有文字的文件進行簽署。以程式設計方式新增文字簽名的逐步指南。"
"linktitle": "新增文字簽名"
"second_title": "GroupDocs.簽署 .NET API"
"title": "使用 GroupDocs.Signature 為文件添加文字簽名"
"url": "/zh-hant/signature/net/master-advanced-sign-techniques/add-text-signatures-to-documents/"
"weight": 17
---

## 介紹

在當今的數位環境中，電子文件簽名對於簡化工作流程和節省資源至關重要。 GroupDocs.Signature for .NET 為以程式設計方式為各種文件格式新增文字簽章提供了強大的解決方案。本教學將引導您完成使用 GroupDocs.Signature for .NET 簽署帶有文字的文件的步驟。

## 先決條件

在開始之前，請確保您具備以下條件：

1. GroupDocs.Signature for .NET：從以下位置下載並安裝該程式庫 [這裡](https://releases。groupdocs.com/signature/net/).
2. 開發環境：設定您的 .NET 開發環境。
3. 文件：準備您想要簽署的文件（例如，PDF，Word）。

## 導入必要的命名空間

首先將所需的命名空間匯入到您的 .NET 專案中：

```csharp
using System;
using System.IO;
using System.Drawing;
using GroupDocs.Signature;
using GroupDocs.Signature.Domain;
using GroupDocs.Signature.Options;
```

## 步驟 1：載入文檔

首先載入您要簽署的文件：

```csharp
string filePath = "sample.pdf"; // 文件路徑
string fileName = Path.GetFileName(filePath);
```

## 第 2 步：定義輸出檔路徑

接下來，設定保存簽名文檔的輸出檔案路徑：

```csharp
string outputFilePath = Path.Combine("Your Document Directory", "SignWithText", fileName);
```

## 步驟 3：建立簽名選項

配置文字簽名的選項，包括內容、位置、大小、顏色和字體樣式：

```csharp
TextSignOptions options = new TextSignOptions("John Smith")
{
    Left = 50, // X 位置
    Top = 200, // 位置
    Width = 100, // 簽名的寬度
    Height = 30, // 簽名的高度
    ForeColor = Color.Red, // 文字顏色
    Font = new SignatureFont { Size = 14, FamilyName = "Comic Sans MS" } // 字體設定
};
```

## 步驟4：簽署文件

最後，使用 GroupDocs.Signature 應用文字簽章並儲存簽署的文件：

```csharp
using (Signature signature = new Signature(filePath))
{
    SignResult result = signature.Sign(outputFilePath, options); // 簽署文件
    Console.WriteLine($"\nDocument signed successfully with {result.Succeeded.Count} signature(s).\nFile saved at {outputFilePath}.");
}
```

## 結論

在本教學中，我們示範如何使用 GroupDocs.Signature for .NET 以程式設計方式新增文字簽章。透過遵循這些步驟，您可以有效地增強文件的安全性和真實性。

## 常見問題解答

### 我可以自訂文字簽名的外觀嗎？
是的，您可以自訂文字簽名的各種屬性，例如顏色、字體、大小和位置，以滿足您的需求。

### GroupDocs.Signature 是否相容於多種文件格式？
絕對地！ GroupDocs.Signature 支援多種格式，包括 PDF、Word、Excel、PowerPoint 等。

### 我可以在單一文件中新增多個文字簽名嗎？
是的，您可以新增多個文字簽名，每個簽名都有自己的自訂選項。

### GroupDocs.Signature 簽章後是否能確保文件的完整性？
是的，該庫使用強大的加密演算法來確保文件的完整性並防止簽名後被篡改。

### 購買前是否有可供測試的試用版？
是的，您可以從下載免費試用版 [這裡](https://releases.groupdocs.com/) 在購買之前探索其功能。