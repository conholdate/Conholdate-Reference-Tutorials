---
"description": "了解如何使用 Aspose.Email for .NET 在 MHT 轉換過程中變更字體。按照本逐步指南輕鬆自訂。"
"linktitle": "使用 C# 變更 MHT 字型自訂"
"second_title": "Aspose.Email .NET 電子郵件處理 API"
"title": "使用 C# 變更 MHT 字型自訂"
"url": "/zh-hant/email/net/mastering-email-header-manipulation/changing-mht-font-customization/"
"weight": 11
---

## 介紹

在網路通訊領域，MHT (MHTML) 檔案是儲存和分享網頁內容（包括圖片、連結和樣式）的便捷方式。但是，當您需要透過更改字體來美化這些 MHT 檔案時該怎麼辦？有了 Aspose.Email for .NET，這項任務變得輕而易舉。在本教程中，我們將逐步指導您在 MHT 轉換過程中變更字體。無論您是開發處理電子郵件格式的應用程序，還是只想為您的企業定製文檔，本指南都能為您提供所需的知識。

## 先決條件

在深入研究程式碼之前，您應該準備一些必需品：

1. Visual Studio：您需要一個整合開發環境 (IDE) 來處理您的 C# 專案。
2. Aspose.Email for .NET 程式庫：請確保您已安裝該程式庫。您可以從 [關聯](https://releases。aspose.com/email/net/).
3. .NET Framework：您的專案應該與 .NET Framework 相容；通常，.NET Core 或更高版本可以運作良好。

這些都準備好了嗎？太棒了！我們開始吧。

## 導入包

首先，確保你的專案已設定為使用必要的命名空間。你需要在 C# 檔案的頂部添加以下內容：

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Tools;
```

這些軟體包將使您能夠存取處理 MHT 檔案和修改其內容所需的功能。

現在，讓我們分解一下 MHT 轉換期間更改字體所涉及的步驟。

## 步驟1：載入MHT文件

你需要做的第一件事就是將 MHT 檔案載入到 `MailMessage` 對象。您可以在這裡存取和操作其內容。

```csharp
MailMessage message = MailMessage.Load("input.mht", new MhtmlLoadOptions());
```

解釋：這裡， `"input.mht"` 是 MHT 檔案的路徑。 `MhtmlLoadOptions()` 允許您設定檔的載入方式，例如，以不同的方式處理附件或連結資源。

## 步驟 2：迭代替代視圖

MHT 檔案通常有多個可選視圖，尤其是在包含 HTML 內容的情況下。您需要循環瀏覽這些視圖，才能找到要修改的視圖。

```csharp
foreach (var alternateView in message.AlternateViews)
{
    if (alternateView.ContentType.MediaType == "text/html")
    {
        var htmlView = (AlternateView)alternateView;
        var linkedResources = htmlView.LinkedResources;
```

解釋：你正在檢查每一個 `AlternateView` 查看它是否是 HTML 類型。如果是，你可以訪問 `LinkedResources`，HTML 中連結的所有字體通常都儲存在其中。

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

說明：此循環檢查連結資源的內容類型是否為 TrueType 字型。如果匹配，您可以將字體名稱更改為您想要的名稱（例如本例中的“Arial”）。 `TransferEncoding` 還應進行設置，以確保在儲存文件時字體資料被正確編碼。

## 步驟4：儲存更新的MHT文件

自訂字體後，就可以儲存修改後的 MHT 檔案了。您需要確保使用正確的儲存選項來維護文件的完整性。

```csharp
message.Save("output.mht", SaveOptions.DefaultMhtml);
```

解釋：在這行程式碼中， `"output.mht"` 是要儲存更新內容的文件的名稱。使用 `SaveOptions.DefaultMhtml` 確保新文件保持 MHT 格式。

## 結論

更改 MHT 文件中的字體可以顯著提昇文件的外觀和風格。利用 Aspose.Email for .NET，您只需幾行程式碼即可輕鬆載入 MHT 檔案、修改其內容並儲存變更。無論您是在開發個人專案還是大型應用程序，掌握這些技能都能提升您呈現資訊的方式。

## 常見問題解答

### 什麼是 MHT 格式？
MHT 是一種網頁存檔格式，將 HTML 文件、圖像和其他資源儲存在單一文件中。

### 我可以使用 Aspose 更改 MHT 檔案的其他方面嗎？
當然！ Aspose.Email 允許您修改 MHT 檔案的幾乎每個方面，包括附件、標題等等。

### Aspose.Email for .NET 免費嗎？
Aspose 提供免費試用，但完整版需要授權。您可以從 [這裡](https://purchase。aspose.com/temporary-license/).

### 在哪裡可以找到有關 Aspose.Email 的更多文件？
您可以在以下位置找到全面的文件和範例 [Aspose Email 文件頁面](https://reference。aspose.com/email/net/).

### 如果我在使用 Aspose 時遇到問題怎麼辦？
如果您遇到任何問題，可以聯繫 [Aspose 支援論壇](https://forum。aspose.com/c/email/12/).