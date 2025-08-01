---
"description": "了解如何使用 Aspose.Cells for .NET 為現有已簽署的 Excel 檔案新增新的數位簽章。本綜合指南涵蓋了所有先決條件、逐步說明和程式碼範例。"
"linktitle": "在已簽名的 Excel 檔案中新增新的數位簽名"
"second_title": "Aspose.Cells .NET Excel 處理 API"
"title": "在已簽名的 Excel 檔案中新增新的數位簽名"
"url": "/zh-hant/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## 介紹

在當今的數位環境中，確保文件的真實性和完整性比以往任何時候都更加重要。數位簽章提供了一種可靠的方法來驗證文件是否已更改以及是否來自合法來源。如果您正在 .NET 中使用 Excel 文件，並且需要在已簽署的文件中新增的數位簽名，那麼本指南適合您！我們將介紹使用 Aspose.Cells for .NET 為現有簽章 Excel 檔案新增數位簽章的過程。

## 先決條件

在深入實施之前，請確保您已具備以下條件：

1. Aspose.Cells for .NET：下載並安裝 Aspose.Cells [發布頁面](https://releases。aspose.com/cells/net/).
2. .NET Framework：確保您的機器已安裝 .NET Framework，並且您熟悉基本的 .NET 程式設計概念。
3. 數位憑證：取得.pfx格式的有效數位憑證。為了測試，您可以建立一個自簽名憑證。
4. 開發環境：使用 Visual Studio 等 IDE 編寫和執行 C# 程式碼。
5. 範例 Excel 文件：有一個已經過數位簽章的現有 Excel 文件，它將作為新增簽章的目標。

有了這些先決條件，我們就可以開始寫程式了！

## 導入必要的套件

在 C# 檔案的頂部，包含以下命名空間以存取所需的類別和方法：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 步驟 1：定義目錄

指定來源檔案的目錄以及儲存輸出檔案的位置：

```csharp
// 來源目錄
string sourceDir = "Your Document Directory"; // 替換為您的實際目錄
// 輸出目錄
string outputDir = "Your Document Directory"; // 替換為您的實際目錄
```

## 步驟 2：載入現有的簽章工作簿

載入已經簽署的Excel工作簿：

```csharp
// 載入已經過數位簽章的工作簿
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## 步驟3：建立數位簽章集合

建立一個集合來管理您的數位簽名：

```csharp
// 建立數位簽章集合
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## 步驟 4：載入您的證書

加載您的數位證書，它將用於創建新的簽名：

```csharp
// 證書文件及其密碼
string certFileName = sourceDir + "AsposeDemo.pfx"; // 您的證書文件
string password = "aspose"; // 您的憑證密碼

// 建立新證書
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## 步驟5：建立新的數位簽名

現在，建立一個新的數位簽名並將其添加到您的收藏中：

```csharp
// 建立新的數位簽章並將其新增至集合中
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## 步驟 6：將簽章集合新增至工作簿

將數位簽章集合新增至工作簿：

```csharp
// 將數位簽章集合新增至工作簿
workbook.AddDigitalSignature(dsCollection);
```

## 步驟 7：儲存工作簿

儲存包含新數位簽章的工作簿：

```csharp
// 儲存工作簿
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## 步驟8：確認成功

執行成功後提供回饋：

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## 結論

恭喜！您已成功使用 Aspose.Cells for .NET 將新的數位簽章新增至已簽署的 Excel 檔案。此過程增強了您的文件的安全性並確保了其真實性和完整性。

## 常見問題解答

### 什麼是數位簽章？

數位簽名是一種數學方案，用於驗證數位訊息或文件的真實性和完整性，確保它們沒有被更改並確認簽名者的身份。

### 我是否需要特殊憑證來建立數位簽章？

是的，需要由受信任的憑證授權單位 (CA) 頒發的數位憑證才能建立有效的數位簽章。

### 我可以使用自簽名憑證進行測試嗎？

絕對地！您可以使用自簽名憑證進行開發和測試目的，但對於生產，建議使用來自受信任 CA 的憑證。

### 如果我嘗試在未簽名的文檔中添加簽名會發生什麼？

如果您嘗試將數位簽章新增至尚未簽署的文件中，它將正常運作，但原始簽名將不存在。

### 在哪裡可以找到有關 Aspose.Cells 的更多資訊？

有關詳細指南和 API 參考，請查看 [Aspose.Cells 文檔](https://reference。aspose.com/cells/net/).