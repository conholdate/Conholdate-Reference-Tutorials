---
"description": "了解如何使用 Aspose.PDF for .NET 建立本地超鏈接，從而改善 PDF 文件的導航體驗。本教學將逐步引導您完成整個過程。"
"linktitle": "在 PDF 文件中建立本地超鏈接"
"second_title": "Aspose.PDF for .NET API參考"
"title": "在 PDF 文件中建立本地超鏈接"
"url": "/zh-hant/pdf/net/mastering-links-and-actions/creating-local-hyperlink/"
"weight": 40
---

## 介紹

在本指南中，我們將引導您使用 Aspose.PDF for .NET 在 PDF 檔案中建立本機超連結。我們將清楚分解每個步驟，確保即使您是 PDF 操作新手，也能輕鬆上手。

## 先決條件

在深入研究程式碼之前，請確保您已具備以下條件：

1. Visual Studio：從下載 [Visual Studio 網站](https://visualstudio。microsoft.com/).
2. Aspose.PDF for .NET：透過下載庫 [Aspose 網站](https://releases.aspose.com/pdf/net/)。該庫提供了一組豐富的 PDF 操作功能。
3. C# 基礎：熟悉 C# 程式設計會有所幫助，但別擔心；我們會逐行解釋程式碼。
4. .NET Framework：確保您的電腦上已安裝 .NET Framework。請查看 Aspose.PDF 上的要求。 [文件](https://reference。aspose.com/pdf/net/).

有了這些先決條件，您就可以學習如何在 PDF 文件中建立本機超連結了！

## 導入所需的套件

現在您已完成所有設置，是時候將必要的套件匯入到您的 C# 專案中了。

### 打開你的專案

開啟您現有的 .NET 專案或在 Visual Studio 中建立一個新專案。如果您是新項目，請在啟動畫面上選擇「建立新項目」。

### 新增對 Aspose.PDF 的引用

在「解決方案資源管理器」中，以滑鼠右鍵按一下專案資料夾中的「依賴項」。選擇“管理 NuGet 套件”，搜尋 `Aspose.PDF`，並安裝最新版本。這將包含您建立和操作 PDF 所需的所有工具。

### 導入命名空間

在 .cs 檔案的頂部，新增以下使用指令：

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

這些指令可讓您無縫存取庫的功能。

讓我們將建立本地超連結的過程分解為簡單的步驟。

## 步驟 1：設定文檔實例

建立一個新的實例 `Document` 類，代表您將使用的 PDF 文件。

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // 設定文檔目錄
Document doc = new Document(); // 建立 Document 實例
```

代替 `"YOUR_DOCUMENT_DIRECTORY"` 使用系統中儲存 PDF 的實際路徑。

## 步驟 2：新增頁面

接下來，為您的 PDF 文件新增一頁。

```csharp
Page page = doc.Pages.Add(); // 新增頁面
```

此行會為文件新增一個頁面，所有內容都將放置在該頁面中。

## 步驟 3：建立文字片段

現在，讓我們建立一段可作為可點擊連結的文字。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7"); // 建立文字片段
```

這 `TextFragment` 將顯示使用者可以點擊的文字。

## 步驟4：建立本地超連結

現在，建立指向第 7 頁的本機超連結。

```csharp
LocalHyperlink link = new LocalHyperlink(); // 建立本地超連結
link.TargetPageNumber = 7; // 設定連結的目標頁面
text.Hyperlink = link; // 設定文字片段的超鏈接
```

這 `LocalHyperlink` 類別允許您指定超連結的目標頁碼。

## 步驟 5：將文字片段新增至頁面

將可點擊的文字新增至您建立的頁面。

```csharp
page.Paragraphs.Add(text); // 將文字片段新增至頁面
```

此行將您的文字新增至頁面的段落集合中。

## 步驟 6：建立另一個文字片段（可選）

讓我們新增另一個超連結以導覽回第 1 頁。

```csharp
TextFragment textBack = new TextFragment("Link to page 1"); // 建立新的文字片段
textBack.IsInNewPage = true; // 指示它應該在新頁面上
```

## 步驟7：設定第二個本地超鏈接

為第 1 頁建立另一個本地超連結。

```csharp
Aspose.Pdf.LocalHyperlink linkBack = new Aspose.Pdf.LocalHyperlink(); // 建立另一個本地超連結
linkBack.TargetPageNumber = 1; // 設定第二個超連結的目標頁面
textBack.Hyperlink = linkBack; // 設定第二個文字片段的超鏈接
```

## 步驟 8：將第二個文字片段新增至新頁面

將第二個文字片段新增至其頁面。

```csharp
Page newPage = doc.Pages.Add(); // 為第二個連結新增頁面
newPage.Paragraphs.Add(textBack); // 將文字片段新增至新頁面
```

## 步驟9：儲存文檔

最後，儲存您的文件。

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // 指定輸出檔名
doc.Save(dataDir); // 儲存更新後的文檔
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```

這一行將您的目錄路徑與檔案名稱結合起來，並且 `Save()` 方法保存您的文件。

## 結論

使用 Aspose.PDF for .NET 在 PDF 檔案中建立本機超連結是一項實用功能，可增強導航和使用者體驗。現在，您可以掌握如何引導讀者直接找到所需信息，從而使您的 PDF 更具互動性，更加用戶友好。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員使用 .NET 框架以程式設計方式建立、操作和轉換 PDF 文件。

### 我可以建立指向外部網頁的超連結嗎？
是的，除了 PDF 內的本機超連結外，Aspose.PDF 還支援建立指向外部 URL 的超連結。

### Aspose.PDF 有免費試用版嗎？
當然！您可以從 [Aspose 網站](https://releases。aspose.com/).

### Aspose 支援哪些程式語言？
Aspose 提供各種程式語言的函式庫，包括 Java、C++ 和 Python 等。

### 如何獲得 Aspose 產品的支援？
您可以透過以下方式尋求支持 [Aspose 論壇](https://forum。aspose.com/c/pdf/10).