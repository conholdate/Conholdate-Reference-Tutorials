---
"description": "了解如何使用 Aspose.Words for .NET 以程式設計方式將簽名行新增至 Word 文件。本指南內容全面，涵蓋從設定開發環境到插入簽名行以及安全簽署文件的所有內容。"
"linktitle": "建立新的數位簽章行並設定提供者 ID"
"second_title": "Aspose.Words文件處理API"
"title": "建立新的數位簽章行並設定提供者 ID"
"url": "/zh-hant/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## 介紹

各位科技愛好者們，大家好！您是否想過在 Word 文件中自動新增簽名行？今天，我們將深入探討如何使用 Aspose.Words for .NET 來實現這一目標。本逐步指南將指導您建立簽名行並設定提供者 ID，讓您的文件處理任務更有效率、更流暢。

## 先決條件

在我們開始之前，請確保您已完成所有設定：

1. Aspose.Words for .NET：如果您尚未安裝，請下載 [這裡](https://releases。aspose.com/words/net/).
2. 開發環境：使用 Visual Studio 或任何 C# 開發設定。
3. .NET Framework：確保您的機器上安裝了 .NET Framework。
4. PFX 憑證：您需要一個 PFX 憑證來簽署文檔，該憑證可以從受信任的憑證授權單位取得。

## 導入必要的命名空間

首先，將所需的命名空間匯入到您的 C# 專案中：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

現在，讓我們深入了解建立新簽章行和設定提供者 ID 的細節。

## 步驟 1：建立新文檔

首先，我們需要建立一個新的 Word 文檔，它將作為我們簽名行的畫布：

```csharp
// 指定文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

在這裡，我們初始化一個新的 `Document` 和一個 `DocumentBuilder`，這使我們能夠輕鬆添加元素。

## 第 2 步：定義簽章行選項

接下來，我們將定義簽名行的選項，包括簽署者的姓名、職位、電子郵件和其他相關詳細資訊：

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

這些選項有助於個性化簽名行，使其清晰、專業。

## 步驟 3：插入簽名行

準備好選項後，我們現在可以將簽名行插入文件：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

這 `InsertSignatureLine` 方法新增簽章行，我們為其指派一個唯一的提供者ID。

## 步驟4：儲存文檔

插入簽名行後，我們儲存文件：

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

這將保存您的文件以及新新增的簽名行。

## 步驟 5：設定簽名選項

現在，我們將配置簽名選項，包括簽名行 ID、提供者 ID、註解和簽名時間：

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

這些設定確保文件使用正確的詳細資訊進行簽名。

## 步驟 6：建立證書持有者

要簽署該文檔，我們需要使用 PFX 憑證建立憑證持有者：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

代替 `"morzal.pfx"` 您的實際憑證檔案名稱和 `"aw"` 使用您的證書密碼。

## 步驟 7：簽署文件

最後，我們將使用數位簽章實用程式對文件進行簽章：

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

此程序對文件進行簽名並將其儲存為新文件。

## 結論

恭喜！您已成功使用 Aspose.Words for .NET 在 Word 文件中建立簽名行並設定提供者 ID。這個強大的庫可以簡化文件處理任務，提高您的工作流程效率。快來試用，看看它如何提升您的專案效率！

## 常見問題解答

### 我可以自訂簽名行的外觀嗎？
當然！您可以在 `SignatureLineOptions` 以滿足您的風格和要求。

### 如果我沒有 PFX 憑證怎麼辦？
您需要從受信任的證書頒發機構獲取一個證書，因為它對於數位簽署文件至關重要。

### 我可以在一份文件中新增多個簽名行嗎？
是的，您可以透過使用不同的選項重複插入程序來新增多個簽名行。

### Aspose.Words for .NET 是否與 .NET Core 相容？
是的，Aspose.Words for .NET 支援 .NET Core，使其適用於各種開發環境。

### 數位簽章有多安全？
只要您使用有效且可信賴的證書，使用 Aspose.Words 建立的數位簽章就非常安全。