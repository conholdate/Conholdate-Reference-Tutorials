---
"description": "了解如何使用 Aspose.Email for .NET 在 MHT 轉換期間變更字體。請按照本逐步指南即可輕鬆進行自訂。"
"linktitle": "使用 C# 變更 MHT 字型自訂"
"second_title": "Aspose.Email .NET 電子郵件處理 API"
"title": "使用 C# 變更 MHT 字型自訂"
"url": "/zh-hant/email/net/mastering-email-header-manipulation/changing-mht-font-customization/"
"weight": 11
---

## 介紹

在網路通訊領域，MHT（MHTML）檔案是一種儲存和分享網路內容的便捷方式，其中包含圖像、連結和樣式。但是當您需要透過更改字體來修飾這些 MHT 檔案時會發生什麼？感謝 Aspose.Email for .NET，這項任務變得輕而易舉。在本教程中，我們將逐步指導您完成在 MHT 轉換期間更改字體的過程。無論您是開發處理電子郵件格式的應用程式還是只想為您的業務定製文檔，本指南都將為您提供所需的知識。

## 先決條件

在深入研究程式碼之前，您應該準備一些必需品：

1. Visual Studio：您需要一個整合開發環境 (IDE) 來處理您的 C# 專案。
2. Aspose.Email for .NET 程式庫：確保您已安裝該程式庫。您可以從 [關聯](https://releases。aspose.com/email/net/).
3. .NET Framework：您的專案應該與.NET Framework相容；通常，.NET Core 或更高版本運作良好。

那些都排好了嗎？驚人的！讓我們開始吧。

## 導入包

首先，請確保您的專案已設定為使用必要的命名空間。您需要在 C# 檔案的頂部包含以下內容：

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Tools;
```

這些軟體包將使您能夠存取處理 MHT 檔案和修改其內容所需的功能。

現在，讓我們分解一下 MHT 轉換期間更改字體所涉及的步驟。

## 步驟1：載入MHT文件

你需要做的第一件事就是將 MHT 檔案載入到 `MailMessage` 目的。您可以在這裡存取和操作其內容。

```csharp
MailMessage message = MailMessage.Load("input.mht", new MhtmlLoadOptions());
```

解釋：這裡， `"input.mht"` 是您的 MHT 檔案的路徑。這 `MhtmlLoadOptions()` 允許您設定檔的載入方式，例如，以不同的方式處理附件或連結資源。

## 步驟 2：迭代替代視圖

MHT 檔案通常有多個備選視圖，尤其是當它們包含 HTML 內容時。您需要循環遍歷這些視圖來找到要修改的視圖。

```csharp
foreach (var alternateView in message.AlternateViews)
{
    if (alternateView.ContentType.MediaType == "text/html")
    {
        var htmlView = (AlternateView)alternateView;
        var linkedResources = htmlView.LinkedResources;
```

解釋：你正在檢查每一個 `AlternateView` 看看它是否是 HTML 類型。如果是，您可以訪問 `LinkedResources`，HTML 中連結的所有字體通常都儲存在其中。

## 步驟3：識別和自訂字體

現在您可以存取連結的資源，您可以識別哪些資源是字體並根據需要進行自訂。

```csharp
foreach (var linkedResource in linkedResources)
{
    if (linkedResource.ContentType.MediaType == "application/x-font-ttf")
    {
        linkedResource.ContentType.Name = "Arial";  // 變更為所需字體
        linkedResource.TransferEncoding = TransferEncoding.Base64;  // 確保其編碼正確
    }
}
```

說明：此循環檢查連結資源的內容類型是否為 TrueType 字型。如果匹配，您可以將字體的名稱更改為您想要的名稱（如本例中的“Arial”）。這 `TransferEncoding` 還應進行設置，以確保在儲存文件時字體資料被正確編碼。

## 步驟4：儲存更新的MHT文件

自訂字體後，就可以儲存修改後的 MHT 檔案了。您需要確保使用正確的儲存選項來維護文件的完整性。

```csharp
message.Save("output.mht", SaveOptions.DefaultMhtml);
```

解釋：在這行程式碼中， `"output.mht"` 是要儲存更新內容的文件的名稱。使用 `SaveOptions.DefaultMhtml` 確保新文件保持 MHT 格式。

## 結論

更改 MHT 文件中的字體可以顯著增強文件的外觀和感覺。透過利用 Aspose.Email for .NET，您可以輕鬆載入 MHT 檔案、修改其內容，並僅使用幾行程式碼儲存變更。無論您正在從事個人專案還是更大的應用程序，掌握這些技能都可以改善您呈現資訊的方式。

## 常見問題解答

### 什麼是 MHT 格式？
MHT 是一種網頁存檔格式，將 HTML 文件、圖像和其他資源儲存在單一文件中。

### 我可以使用 Aspose 更改 MHT 檔案的其他方面嗎？
絕對地！ Aspose.Email 允許您修改 MHT 檔案的幾乎每個方面，包括附件、標題等。

### Aspose.Email for .NET 免費嗎？
Aspose 提供免費試用，但完整版需要授權。您可以從 [這裡](https://purchase。aspose.com/temporary-license/).

### 在哪裡可以找到有關 Aspose.Email 的更多文件？
您可以在以下位置找到全面的文件和範例 [Aspose Email 文件頁面](https://reference。aspose.com/email/net/).

### 如果我在使用 Aspose 時遇到問題怎麼辦？
如果您遇到任何問題，可以聯繫 [Aspose 支援論壇](https://forum。aspose.com/c/email/12/).