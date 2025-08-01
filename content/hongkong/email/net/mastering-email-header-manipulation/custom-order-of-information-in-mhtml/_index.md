---
"description": "在本逐步教學中了解如何使用 Aspose.Email for .NET 在 MHTML 中定義自訂資訊順序。"
"linktitle": "使用 Aspose.Email 在 MHTML 中自訂資訊順序"
"second_title": "Aspose.Email .NET 電子郵件處理 API"
"title": "使用 Aspose.Email 在 MHTML 中自訂資訊順序"
"url": "/zh-hant/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## 介紹

建立豐富的電子郵件格式可以大大增強溝通，尤其是在將電子郵件匯出為 MHTML 等不同文件格式時。 Aspose.Email for .NET 為開發人員提供了一個強大的電子郵件處理工具包，其中包括定義匯出為 MHTML 時資訊顯示的自訂順序。在本指南中，我們將分解實現此目標所需的步驟，無論您是經驗豐富的開發人員還是剛起步，都可以輕鬆遵循。那麼，就讓我們開始吧！

## 先決條件

在深入定義 MHTML 中的自訂資訊順序之前，您需要檢查清單中的一些先決條件：

1. .NET 開發環境：確保您已設定 .NET 開發環境。您可以使用 Visual Studio、Visual Studio Code 或任何其他相容的 IDE。

2. Aspose.Email 函式庫：您需要安裝 Aspose.Email for .NET 函式庫。您可以從 [Aspose 發佈頁面](https://releases。aspose.com/email/net/).

3. 對 C# 的基本了解：熟悉 C# 程式設計將幫助您更好地理解程式碼。

4. 範例電子郵件文件：您需要一個範例 `.eml` 文件（例如， `Attachments.eml`）用於測試目的。

一旦滿足了這些先決條件，您就可以繼續學習本教學了！

## 導入包

要開始使用程式碼，您需要從 Aspose.Email 庫匯入必要的命名空間。這對於存取操作電子郵件文件所需的所有類別和方法至關重要。

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

將它們包含在 C# 檔案的頂部。現在您已準備好開始編碼了！

現在您已完成所有設置，讓我們將教程分解為易於管理的步驟。

## 步驟 1：設定資料目錄

首先要做的是建立一個儲存電子郵件檔案的目錄。這可以是您本機上的任何路徑。

```csharp
string dataDir = "Your Data Directory";
```

代替 `"Your Data Directory"` 實際路徑 `.eml` 文件所在位置。例如，如果你的檔案位於 `C:\Emails`，你會寫：

```csharp
string dataDir = @"C:\Emails\";
```

## 第 2 步：載入電子郵件訊息

接下來，您需要加載 `.eml` 文件放入 `MailMessage` 目的。這使您可以操作電子郵件的內容和元資料。

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

確保檔案名稱與指定目錄中的檔案名稱相符。如果您的檔案有不同的名稱，請相應地更新檔案名稱。

## 步驟 3：設定 MHTML 儲存選項

載入完電子郵件後，就該定義如何將其儲存為 MHTML 了。您可以從預設選項開始。

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

此行初始化 MHTML 儲存選項，為稍後自訂標題做好準備。

## 步驟 4：使用預設順序儲存 MHTML

讓我們使用預設順序將電子郵件儲存為 MHTML。這為您提供了定制後進行比較的基準。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

運行此行，並檢查指定的目錄。現在您應該會看到一個名為 `CustomOrderOfInformationInMHTML_1.mhtml`。打開它，看看資訊預設是如何顯示的。

## 步驟 5：自訂標題順序

現在到了有趣的部分！您可以指定在 MHTML 輸出中包含哪些標題以及包含的順序。我們將從一些常見的標題開始。

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

如果您想要完全不同的訂單怎麼辦？您可以透過清除現有的標題設定來重新開始。

```csharp
opt.RenderingHeaders.Clear();
```

現在是時候為標題定義一個新的順序了。例如，如果您想要確定附件和副本收件者的優先順序：

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

現在您已經擁有了使用 Aspose.Email for .NET 在 MHTML 中定義自訂資訊順序的簡單指南。遵循這些步驟，您可以控制電子郵件以 MHTML 格式呈現的方式，確保以符合您需求的方式呈現最重要的資訊。 

## 常見問題解答

### 什麼是 MHTML？
MHTML 代表“MIME HTML”，這是一種結合了 HTML 和圖像等其他資源的網頁存檔格式。

### 我可以免費使用 Aspose.Email 嗎？
是的，Aspose 為開發人員提供免費試用版供探索。你可以找到它 [這裡](https://releases。aspose.com/).

### 如果使用 Aspose.Email 時遇到問題怎麼辦？
您可以透過以下方式獲得社區支持 [Aspose 論壇](https://forum。aspose.com/c/email/12/).

### Aspose.Email 有臨時許可證嗎？
是的，你可以申請臨時駕照 [這裡](https://purchase。aspose.com/temporary-license/).

### 在哪裡可以購買 Aspose.Email？
您可以在此處購買圖書館 [關聯](https://purchase。aspose.com/buy).