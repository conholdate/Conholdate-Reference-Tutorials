---
"description": "了解如何使用 GroupDocs.Viewer 輕鬆地將文件檢視功能整合到您的 .NET 應用程式中。本教程提供了全面的、循序漸進的指南。"
"linktitle": "載入受密碼保護的文檔"
"second_title": "GroupDocs.Viewer .NET API"
"title": "載入受密碼保護的文檔"
"url": "/zh-hant/viewer/net/advanced-document-loading/loading-password-protected-document/"
"weight": 12
---

## 介紹

在數位領域，管理和查看各種文件格式的能力對於企業和個人來說至關重要。 GroupDocs.Viewer for .NET 為開發人員提供了一個強大的解決方案，使他們能夠毫不費力地將文件檢視功能整合到他們的應用程式中。本教學將逐步引導您完成載入受密碼保護的文件的過程，確保您可以在專案中無縫實現此功能。

## 先決條件

在開始之前，請確保您具備以下條件：

1. 已安裝 GroupDocs.Viewer for .NET：從 [網站](https://releases。groupdocs.com/viewer/net/).
2. 受密碼保護的文件：準備好受密碼保護的文件以供測試。

## 導入所需的命名空間

首先將必要的命名空間匯入到您的專案中：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 步驟 1：定義輸出目錄

指定渲染輸出的儲存位置：

```csharp
string outputDirectory = "Your Document Directory";
```
確保更換 `"Your Document Directory"` 使用您想要使用的實際路徑。

## 步驟2：設定頁面檔案路徑格式

定義每個渲染頁面的檔案路徑的格式：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

這將產生類似的路徑 `"Your Document Directory/page_1.html"`， `"Your Document Directory/page_2.html"`， ETC。

## 步驟 3：配置載入選項

設定受密碼保護的文件的載入選項，包括密碼：

```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"  // 替換為您的文件密碼
};
```

## 步驟 4：初始化檢視器

使用您的文件和載入選項建立 GroupDocs.Viewer 的實例：

```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // 下一步將新增查看選項的程式碼。
}
```
確保更換 `"Path_to_your_document"` 使用您的文件的實際路徑。

## 步驟 5：配置 HTML 視圖選項

設定 HTML 視圖選項以呈現具有嵌入資源的文件：

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## 步驟 6：渲染文檔

現在，使用配置的檢視器和視圖選項呈現文件：

```csharp
viewer.View(options);
```

## 步驟 7：顯示成功訊息

最後，通知使用者文件已成功呈現：

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

在本教學中，我們探討如何使用 GroupDocs.Viewer for .NET 載入受密碼保護的文件。透過遵循這些步驟，開發人員可以輕鬆地將此功能整合到他們的應用程式中，從而使用戶能夠毫不費力地查看受保護的文件。

## 常見問題解答

### 除了受密碼保護的文件之外，GroupDocs.Viewer 還能處理其他文件格式嗎？

是的，GroupDocs.Viewer 支援多種格式，包括 PDF、DOCX、XLSX、PPTX 等。

### GroupDocs.Viewer 是否與 .NET Core 相容？

絕對地！ GroupDocs.Viewer 與 .NET Framework 和 .NET Core 環境相容。

### 我可以自訂文件的渲染選項嗎？

是的，GroupDocs.Viewer 提供各種渲染選項，讓您可以根據自己的需求自訂觀看體驗。

### GroupDocs.Viewer 是否支援文件註解？

是的，它支援文件註釋，使用戶可以添加評論、突出顯示和其他註釋。

### GroupDocs.Viewer 有試用版嗎？

是的，您可以從 [網站](https://releases。groupdocs.com/).