---
"description": "了解如何使用 Aspose.Cells for .NET 輕鬆讀取 Excel 工作表中主題註解的建立時間。請遵循我們詳細的逐步指南。"
"linktitle": "使用 Aspose.Cells 讀取主題評論的建立時間"
"second_title": "Aspose.Cells .NET Excel 處理 API"
"title": "使用 Aspose.Cells 讀取主題評論的建立時間"
"url": "/zh-hant/cells/net/guide-worksheet-operations/read-created-time-of-threaded-comment/"
"weight": 21
---

## 介紹

在使用 Excel 檔案時，管理註釋對於協作和回饋追蹤至關重要。在本指南中，我們將引導您使用 Aspose.Cells for .NET 讀取 Excel 工作表中執行緒註解的建立時間。這個強大的工具提供了一種與 Excel 文件互動的有效方法，使開發人員能夠從註釋中提取詳細信息，這對於在協作場景中追蹤反饋時間特別有用。

## 先決條件

在開始之前，請務必確保您的開發環境已正確設置，以便使用 Aspose.Cells for .NET。您需要準備以下工具：

1. Aspose.Cells for .NET：您需要安裝 Aspose.Cells 函式庫。您可以從 [Aspose 網站](https://releases。aspose.com/cells/net/).
2. IDE：Visual Studio（或您選擇的任何 .NET IDE）用於編寫和執行您的程式碼。
3. 基本 C# 知識：熟悉 C# 程式設計將使理解範例變得更容易。
4. Excel 檔案：在本教學中，我們將使用名為 `ThreadedCommentsSample.xlsx`，其中包含一些主題評論。請確保您的文件包含後續評論。

## 導入所需的套件

首先，您需要匯入使用 Aspose.Cells 所需的命名空間。開啟您的 C# 項目，並在程式碼檔案頂部新增以下 using 指令：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這 `Aspose.Cells` 命名空間可讓您存取操作 Excel 檔案所需的所有類別和方法，同時 `System` 是輸出和異常處理等一般功能所必需的。

## 步驟 1：指定 Excel 檔案的目錄

第一步是定義 Excel 檔案的儲存路徑。此路徑將用於以程式設計方式定位檔案。

```csharp
// 定義Excel檔案的目錄
string sourceDir = "Your Document Directory";
```

代替 `"C:\\YourDirectory\\"` 替換為檔案的實際路徑。這確保程序知道在哪裡找到 `ThreadedCommentsSample。xlsx`.

## 第 2 步：載入工作簿

設定好目錄後，我們現在可以載入 Excel 工作簿了。這可以透過創建一個新的 `Workbook` 物件並將檔案路徑傳遞給它。

```csharp
// 載入 Excel 工作簿
Workbook workbook = new Workbook(sourceDir + "ThreadedCommentsSample.xlsx");
```

如果在指定路徑下找不到文件，則會拋出異常，因此請確保文件路徑正確後再繼續。

## 步驟 3：存取所需的工作表

工作簿載入完成後，您需要存取包含主題評論的工作表。在本例中，我們將擷取工作簿的第一個工作表。

```csharp
// 訪問工作簿中的第一個工作表
Worksheet worksheet = workbook.Worksheets[0];
```

如果您的評論位於其他工作表中，只需相應地修改索引即可。例如，使用 `Worksheets[1]` 對於第二張工作表，依此類推。

## 步驟 4：檢索主題評論

若要檢索主題評論，您需要指定包含評論的儲存格。在本例中，我們將重點放在單元格 `A1`方法 `GetThreadedComments` 用於獲取與特定單元格相關的所有評論。

```csharp
// 從儲存格 A1 取得線索評論
ThreadedCommentCollection threadedComments = worksheet.Comments.GetThreadedComments("A1");
```

這將傳回單元格 A1 中線程評論的集合。如果指定儲存格中不存在評論，則該集合為空。

## 步驟 5：遍歷評論並提取創建時間

檢索主題評論後，下一步是遍歷集合並提取相關詳細信息，包括每條評論的創建時間。我們可以透過循環遍歷以下程式碼輕鬆實現此操作： `ThreadedCommentCollection`。

```csharp
// 循環遍歷每個主題評論並顯示詳細信息
foreach (ThreadedComment comment in threadedComments)
{
    Console.WriteLine("Comment: " + comment.Notes);
    Console.WriteLine("Author: " + comment.Author.Name);
    Console.WriteLine("Created Time: " + comment.CreatedTime);
}
```

此程式碼將輸出評論的內容、作者姓名以及評論的建立時間。 `CreatedTime` 屬性傳回評論最初建立的時間戳記。

## 步驟 6：顯示確認訊息

成功讀取並顯示註解後，在程式碼中新增一條確認訊息始終是一個好習慣。這有助於確認該過程已正確執行。

```csharp
// 確認訊息
Console.WriteLine("Successfully retrieved threaded comment created times.");
```

程式碼執行完成後，此訊息將列印到控制台，確認該過程運行沒有錯誤。

## 結論

現在，您已經學習如何使用 Aspose.Cells for .NET 輕鬆讀取 Excel 工作表中執行緒註解的建立時間。此功能對於在協作環境中追蹤註釋和回饋非常有用，可以為文件審閱流程提供必要的時間戳記。遵循本指南，您可以有效地提取和利用 .NET 應用程式中的註釋數據，從而增強工作流程並改善與團隊成員的協作。

## 常見問題解答

### 什麼是 Aspose.Cells for .NET？

Aspose.Cells for .NET 是一個功能全面的程式庫，可協助開發人員在 .NET 應用程式中建立、操作和管理 Excel 檔案。它提供了強大的工具，以程式設計方式讀取、寫入和修改 Excel 檔案。

### 如何下載 Aspose.Cells for .NET？

您可以從 [Aspose 網站](https://releases。aspose.com/cells/net/).

### 有免費試用嗎？

是的，Aspose 提供 Aspose.Cells for .NET 的免費試用版。您可以從 [免費試用頁面](https://releases。aspose.com/).

### 我可以訪問其他單元格的評論嗎？

是的，您可以透過修改儲存格參考來存取工作表中的任何儲存格中的執行緒註釋 `GetThreadedComments` 方法。只需更改 `"A1"` 到所需單元格的引用。

### 我可以在哪裡獲得 Aspose.Cells 的支援？

如果您需要支援或有疑問，請訪問 [Aspose 論壇](https://forum.aspose.com/c/cells/9)，您可以在這裡找到答案或向社區尋求幫助。