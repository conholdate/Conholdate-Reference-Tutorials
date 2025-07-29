---
"description": "在本逐步教學中了解如何使用 Aspose.Email for .NET 在 MHTML 中定義自訂資訊順序。"
"linktitle": "使用 Aspose.Email 在 MHTML 中自訂資訊順序"
"second_title": "Aspose.Email .NET 電子郵件處理 API"
"title": "使用 Aspose.Email 在 MHTML 中自訂資訊順序"
"url": "/zh-hant/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## 介紹

創建豐富的電子郵件格式可以大大增強溝通體驗，尤其是在將電子郵件匯出為 MHTML 等不同文件格式時。 Aspose.Email for .NET 為開發人員提供了強大的電子郵件處理工具包，其中包括自訂匯出為 MHTML 時資訊的顯示順序。在本指南中，我們將分解實現此目的所需的步驟，無論您是經驗豐富的開發人員還是剛剛入門，都能輕鬆上手。那麼，就讓我們開始吧！

## 先決條件

在深入定義 MHTML 中的自訂資訊順序之前，您需要檢查清單中的一些先決條件：

1. .NET 開發環境：確保您已設定好 .NET 開發環境。您可以使用 Visual Studio、Visual Studio Code 或任何其他相容的 IDE。

2. Aspose.Email 函式庫：您需要安裝 Aspose.Email for .NET 函式庫。您可以從 [Aspose 發佈頁面](https://releases。aspose.com/email/net/).

3. 對 C# 的基本了解：熟悉 C# 程式設計將幫助您更好地理解程式碼。

4. 範例電子郵件文件：您需要一個範例 `.eml` 文件（例如， `Attachments.eml`）用於測試目的。

一旦滿足了這些先決條件，您就可以繼續學習本教學了！

## 導入包

要開始編寫程式碼，您需要從 Aspose.Email 庫匯入必要的命名空間。這對於存取操作電子郵件文件所需的所有類別和方法至關重要。

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

將這些程式碼加入你的 C# 檔案頂部。現在你就可以開始寫程式了！

現在您已完成所有設置，讓我們將教程分解為易於管理的步驟。

## 步驟 1：設定資料目錄

首先要做的是建立一個用於儲存電子郵件檔案的目錄。該目錄可以是本機上的任何路徑。

```csharp
string dataDir = "Your Data Directory";
```

代替 `"Your Data Directory"` 實際路徑 `.eml` 文件所在位置。例如，如果您的檔案位於 `C:\Emails`，你會寫：

```csharp
string dataDir = @"C:\Emails\";
```

## 第 2 步：載入電子郵件訊息

接下來，您需要加載 `.eml` 文件放入 `MailMessage` 對象。這允許您操作電子郵件的內容和元資料。

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

確保檔案名稱與指定目錄中的檔案名稱相符。如果檔案名稱不同，請相應地更新檔案名稱。

## 步驟 3：設定 MHTML 儲存選項

電子郵件載入完成後，接下來需要定義如何將其儲存為 MHTML。您可以從預設選項開始。

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

此行初始化 MHTML 儲存選項，為稍後自訂標題做好準備。

## 步驟 4：使用預設順序儲存 MHTML

讓我們使用預設順序將電子郵件儲存為 MHTML。這樣，您就可以在自訂後進行比較。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

運行此行，並檢查指定的目錄。現在您應該會看到一個名為“MHTML”的新文件 `CustomOrderOfInformationInMHTML_1.mhtml`。打開看看資訊預設是如何顯示的。

## 步驟 5：自訂標題順序

現在到了最有趣的部分！您可以指定在 MHTML 輸出中包含哪些標題以及包含的順序。我們先從一些常見的標題開始。

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

透過新增這些標題，您可以告訴 Aspose 您希望如何顯示電子郵件。

## 步驟 6：依自訂順序儲存 MHTML

自訂標題後，您需要將電子郵件再次儲存為 MHTML，以查看新順序如何影響輸出。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

運行此程式碼，然後打開 `CustomOrderOfInformationInMHTML_2.mhtml`。將其與第一個進行比較，看看資訊如何根據標題順序發生變化。

## 步驟 7：清除並新增新的標題順序

如果您想要完全不同的訂單怎麼辦？您可以清除現有的標題設置，重新開始。

```csharp
opt.RenderingHeaders.Clear();
```

現在是時候為標題定義新的順序了。例如，如果您要按優先順序排列附件和副本收件者：

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## 步驟 8：使用新的自訂順序儲存 MHTML

最後，使用新的標題設定最後一次儲存電子郵件。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

運行此行後，打開 `CustomOrderOfInformationInMHTML_3.mhtml` 並檢查它如何根據您的新自訂呈現資訊。

## 結論

以上就是使用 Aspose.Email for .NET 在 MHTML 中自訂資訊順序的簡單指南。請依照以下步驟，您可以控制電子郵件在 MHTML 格式中的呈現方式，確保以符合您需求的方式呈現最重要的資訊。 

## 常見問題解答

### 什麼是 MHTML？
MHTML 代表“MIME HTML”，這是一種結合了 HTML 和圖像等其他資源的網頁存檔格式。

### 我可以免費使用 Aspose.Email 嗎？
是的，Aspose 提供免費試用版供開發者探索。您可以找到 [這裡](https://releases。aspose.com/).

### 如果使用 Aspose.Email 時遇到問題怎麼辦？
您可以透過以下方式獲得社區支持 [Aspose 論壇](https://forum。aspose.com/c/email/12/).

### Aspose.Email 有臨時許可證嗎？
是的，你可以申請臨時駕照 [這裡](https://purchase。aspose.com/temporary-license/).

### 在哪裡可以購買 Aspose.Email？
您可以在此處購買圖書館 [關聯](https://purchase。aspose.com/buy).