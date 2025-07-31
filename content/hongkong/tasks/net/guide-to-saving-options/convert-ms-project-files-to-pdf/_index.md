---
"description": "了解如何使用 Aspose.Tasks for .NET 將 Microsoft Project (.mpp) 檔案轉換為 PDF。請依照本逐步指南自訂 PDF 輸出、選擇特定頁面並自動進行批次轉換。"
"linktitle": "Aspose.Tasks 的 PDF 儲存選項"
"second_title": "Aspose.Tasks .NET API"
"title": "使用 Aspose.Tasks for .NET 將 MS Project 檔案轉換為 PDF"
"url": "/zh-hant/tasks/net/guide-to-saving-options/convert-ms-project-files-to-pdf/"
"weight": 13
---

## 介紹

高效的專案文件管理對於簡化工作流程和專案成功起著關鍵作用。使用 Aspose.Tasks for .NET，開發人員可以精確、靈活地將 Microsoft Project 檔案轉換為 PDF 格式。在本指南中，我們將逐步介紹將 Microsoft Project (.mpp) 檔案儲存為 PDF 的過程，並提供可自訂的選項。

## 使用 Aspose.Tasks for .NET 的先決條件

在繼續操作之前，請確保滿足以下先決條件：

1. Aspose.Tasks for .NET 安裝  
   從下載並安裝庫 [網站](https://releases。aspose.com/tasks/net/).

2. 開發環境  
   具備 C# 程式語言和配置的 .NET 開發環境的工作知識。

3. 輸入 Microsoft Project 文件  
   擁有有效的 `.mpp` 可供轉換的文件。

## 導入基本命名空間

編碼之前，包含存取 Aspose.Tasks 功能所需的命名空間。 

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System.Collections.Generic;
```

## 步驟 1：載入 Microsoft Project 文件

首先，載入 `.mpp` 文件到 `Project` 目的。代替 `"Your_Project_File_Path.mpp"` 輸入檔案的路徑。

```csharp
var project = new Project("Your_Project_File_Path.mpp");
```

## 步驟 2：設定 PDF 儲存選項

設定選項以自訂輸出 PDF。 Aspose.Tasks for .NET 提供了控制頁面渲染、佈局和其他方面的靈活性。

```csharp
var options = new PdfSaveOptions
{
    RenderToSinglePage = false, // 是否在單一頁面上渲染所有內容
    Pages = new List<int>()     // PDF 中要包含的頁面
};
```

## 步驟 3：確定頁數

使用 `PageCount` 屬性來標識項目跨越多少頁。這有助於決定是否包含特定頁面或匯出所有頁面。

```csharp
Console.WriteLine("Total Pages: " + options.PageCount);
```

## 步驟 4：選擇要匯出的特定頁面（可選）

透過填入指定要包含在 PDF 中的確切頁面 `Pages` 財產。例如，要匯出第 1 頁和第 4 頁：

```csharp
options.Pages.Add(1);
options.Pages.Add(4);
```

## 步驟 5：將專案文件儲存為 PDF

最後，保存 `.mpp` 透過調用 `Save` 方法。指定輸出檔案路徑並傳遞配置的選項。

```csharp
project.Save("Output_PDF_File_Path.pdf", options);
```

## 結論

使用 Aspose.Tasks for .NET 將 Microsoft Project 檔案轉換為 PDF 可確保無縫且可自訂的體驗。從選擇特定頁面到自動批次匯出，該工具使開發人員能夠有效地處理專案文件。

## 常見問題解答

### 我可以自訂匯出的 PDF 的外觀嗎？
是的，Aspose.Tasks 允許自訂字體、顏色和頁面佈局以滿足您的特定需求。

### 可以轉換嗎 `.mpp` 來自舊版 Microsoft Project 的文件？
Aspose.Tasks 支持 `.mpp` Microsoft Project 2003 及更高版本的檔案。

### 如何在單一 PDF 頁面上呈現所有項目資料？
設定 `RenderToSinglePage` 的財產 `PdfSaveOptions` 反對 `true`。

```csharp
options.RenderToSinglePage = true;
```

### 我可以將項目資料匯出為其他文件格式嗎？
是的，Aspose.Tasks 支援匯出為各種格式，包括 Excel、HTML 和 PNG 和 JPEG 等圖片格式。

### Aspose.Tasks for .NET 有免費試用版嗎？
是的，你可以下載 [免費試用版在這裡](https://releases。aspose.com/).