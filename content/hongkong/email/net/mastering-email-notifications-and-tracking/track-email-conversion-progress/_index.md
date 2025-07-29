---
"description": "逐步學習如何使用 Aspose.Email for .NET 在 C# 中追蹤電子郵件轉換進度。本詳細教學將幫助您提升專案效率。"
"linktitle": "使用 Aspose.Email for .NET 追蹤電子郵件轉換進度"
"second_title": "Aspose.Email .NET 電子郵件處理 API"
"title": "使用 Aspose.Email for .NET 追蹤電子郵件轉換進度"
"url": "/zh-hant/email/net/mastering-email-notifications-and-tracking/track-email-conversion-progress/"
"weight": 12
---

## 介紹

高效管理電子郵件文件通常需要追蹤其轉換進度。 Aspose.Email for .NET 提供了強大的工具來實現這一點，使開發人員能夠無縫地處理電子郵件操作。本教學將深入講解如何在 C# 中追蹤電子郵件文件轉換進度，並逐步分解該過程以便於理解。  

## 先決條件  

在深入學習本教學之前，請確保您已完成所有設定：  

1. Aspose.Email for .NET：下載並安裝 [Aspose.Email for .NET](https://releases.aspose.com/email/net/) 圖書館.  
2. 開發環境：安裝 Visual Studio 或任何其他與 .NET 相容的 IDE。  
3. .NET Framework：請確保已安裝了 .NET Framework 4.5 或更高版本。  
4. 臨時執照：考慮取得 [臨時執照](https://purchase.aspose.com/temporary-license/) 探索 Aspose.Email 的全部功能。  
5. 範例電子郵件文件：準備 `.eml` 文件（例如， `test.eml`) 作為樣本。  

## 導入包  

若要在專案中使用 Aspose.Email，您需要匯入所需的命名空間。在文件頂部加入以下 using 語句：  

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.SaveOptions;
using System;
using System.IO;
```

## 步驟 1：設定您的項目  

首先在 Visual Studio 中建立一個新的 C# 控制台應用程式。這將作為實現電子郵件文檔轉換追蹤的基礎。  
  
1. 開啟 Visual Studio 並建立一個新的控制台應用程式專案。  
2. 安裝 Aspose.Email NuGet 套件：  
```sh
Install-Package Aspose.Email
```  
3. 添加 `.eml` 文件到您的專案目錄。  

## 第 2 步：載入電子郵件文件  

現在，將電子郵件檔案載入到 `MailMessage` 對象。這是處理電子郵件資料的第一步。  
 
```csharp
string dataDir = "Your Document Directory";
var fileName = dataDir + "test.eml";
MailMessage msg = MailMessage.Load(fileName);
```
 
- `dataDir`：指定您的電子郵件檔案所在的目錄。  
- `MailMessage.Load`：閱讀 `.eml` 文件並準備進行進一步的操作。  

## 步驟3：初始化記憶體流  

接下來，創建一個 `MemoryStream` 物件來暫時儲存轉換後的電子郵件資料。  
 
```csharp
MemoryStream ms = new MemoryStream();
```

一個 `MemoryStream` 在這裡用於管理轉換過程的輸出，而不將資料直接保存到磁碟。  

## 步驟 4：定義轉換選項  

設定 `EmlSaveOptions` 使用自訂進度處理程序來追蹤轉換進度。  
 
```csharp
EmlSaveOptions opt = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
opt.CustomProgressHandler = new ConversionProgressEventHandler(ShowEmlConversionProgress);
```
  
- `MailMessageSaveType.EmlFormat`：指定輸出格式。  
- `CustomProgressHandler`：指派自訂處理程序函數來監視進度。  

## 步驟 5：將電子郵件儲存到記憶體流  

儲存 `MailMessage` 物件使用指定的選項，啟用進度追蹤功能。  
 
```csharp
msg.Save(ms, opt);
```
 
此步驟啟動電子郵件轉換程序並將更新傳送給進度處理程序。  

## 步驟 6：實現進度處理程序  

定義 `ShowEmlConversionProgress` 方法來處理進度更新並在控制台中顯示它們。  
 
```csharp
private static void ShowEmlConversionProgress(ProgressEventHandlerInfo info)
{
    int total;
    int saved;

    switch (info.EventType)
    {
        case ProgressEventType.MimeStructureCreated:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine($"MimeStructureCreated - TotalMimePartCount: {total}");
            Console.WriteLine($"MimeStructureCreated - SavedMimePartCount: {saved}");
            break;

        case ProgressEventType.MimePartSaved:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine($"MimePartSaved - TotalMimePartCount: {total}");
            Console.WriteLine($"MimePartSaved - SavedMimePartCount: {saved}");
            break;

        case ProgressEventType.SavedToStream:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine($"SavedToStream - TotalMimePartCount: {total}");
            Console.WriteLine($"SavedToStream - SavedMimePartCount: {saved}");
            break;
    }
}
```
 
- `ProgressEventHandlerInfo`：提供有關轉換過程的詳細資訊。  
- Switch Case：處理轉換的不同階段： `MimeStructureCreated`， `MimePartSaved`， 和 `SavedToStream`。  

### 預期結果如何？  
隨著轉換的進行，您將看到列印到控制台的詳細更新，例如：  
```plaintext
MimeStructureCreated - TotalMimePartCount: 10  
MimeStructureCreated - SavedMimePartCount: 3  
MimePartSaved - TotalMimePartCount: 10  
MimePartSaved - SavedMimePartCount: 5  
```

## 結論  

透過 Aspose.Email for .NET，使用 C# 追蹤電子郵件文件的轉換進度變得前所未有的輕鬆。透過本教學課程，您學習如何載入電子郵件檔案、設定進度處理程序以及儲存電子郵件數據，同時監控整個流程。此功能可確保您在電子郵件文件操作過程中隨時掌握並掌控一切。  

## 常見問題解答  

### 我可以將此程式碼用於除以下格式之外的其他格式嗎？ `.eml`？  
是的，修改 `MailMessageSaveType` 以適應 MSG 或 MHTML 等其他格式。  

### 如何處理大型電子郵件文件？  
考慮使用 `FileStream` 而不是 `MemoryStream` 以獲得更好的大文件性能。  

### 什麼是臨時駕照？如何獲得？  
臨時許可證可讓您免費評估該庫的全部功能。獲取 [這裡](https://purchase。aspose.com/temporary-license/).  

### 我可以將此程式碼整合到 Web 應用程式中嗎？  
是的，程式碼與使用 ASP.NET 或類似框架的 Web 應用程式相容。  

### 在哪裡可以找到更多資源？  
查看 [文件](https://reference.aspose.com/email/net/) 或訪問 [支援論壇](https://forum.aspose.com/c/email/12/) 尋求幫助。