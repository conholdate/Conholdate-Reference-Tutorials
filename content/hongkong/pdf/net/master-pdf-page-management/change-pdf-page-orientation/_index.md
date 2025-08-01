---
"description": "了解如何使用 Aspose.PDF for .NET 輕鬆調整 PDF 檔案的頁面方向。本逐步指南提供了有關載入、旋轉和儲存文件的清晰說明。"
"linktitle": "更改 PDF 頁面方向"
"second_title": "Aspose.PDF for .NET API參考"
"title": "更改 PDF 頁面方向"
"url": "/zh-hant/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## 介紹

您是否遇到過頁面方向完全錯誤的 PDF 檔案？無論是掃描錯誤的文檔還是僅需要不同佈局的文檔，調整方向都會產生很大的不同。幸運的是，Aspose.PDF for .NET 提供了一種強大且使用者友好的方式來操作 PDF 文件，包括更改頁面的方向。在本指南中，我們將逐步指導您完成整個過程，無論您是想從縱向切換到橫向還是反之亦然。

## 先決條件

在深入討論細節之前，請確保您已做好以下準備：

- Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF 庫。如果你還沒有這樣做，你可以 [點此下載](https://releases。aspose.com/pdf/net/).
- .NET 開發環境：您可以使用 Visual Studio、JetBrains Rider 或任何其他您喜歡的 .NET 開發 IDE。
- C# 基礎知識：熟悉 C# 將協助您更輕鬆地跟進。
- PDF 檔案：準備一個範例 PDF 檔案以供測試。您可以建立一個或在線下載一個範例。

如果您剛開始，請考慮嘗試使用 Aspose.PDF [免費臨時駕照](https://purchase.aspose.com/temporary-license/) 在決定 [購買完整版](https://purchase。aspose.com/buy).

## 導入命名空間

要操作 PDF 頁面，您首先需要在 C# 專案中匯入必要的命名空間。在程式碼檔案頂部新增以下行：

```csharp
using System.IO;
using Aspose.Pdf;
```

現在我們已經設定好了一切，讓我們開始吧！

## 步驟 1：載入 PDF 文檔

第一步是載入您想要修改的 PDF 檔案。使用 `Document` 來自 Aspose.PDF 命名空間的類別：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

確保更換 `"YOUR DOCUMENT DIRECTORY"` 使用您的 PDF 檔案的實際路徑。

## 步驟 2：循環遍歷每一頁

接下來，我們將循環遍歷 PDF 文件中的每一頁。這使我們能夠將方向變更應用於所有頁面：

```csharp
foreach (Page page in doc.Pages)
{
    // 操作每個頁面
}
```

## 步驟 3：造訪頁面的媒體框

每個 PDF 頁面都有一個 `MediaBox` 定義了它的邊界。我們需要訪問它來檢查當前方向並進行調整：

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

這 `MediaBox` 提供頁面的尺寸，包括寬度和高度。

## 步驟 4：交換寬度和高度

要改變頁面方向，我們將交換寬度和高度值。此調整將改變頁面的尺寸：

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

在這裡，我們計算新的尺寸並重新定位左下角（`LLY`） 因此。

## 步驟 5：更新 MediaBox 和 CropBox

現在我們有了新的尺寸，我們將這些變化應用到 `MediaBox` 和 `CropBox` 確保頁面正確顯示：

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## 步驟6：旋轉頁面

為了完成方向的改變，我們將旋轉頁面。使用 Aspose.PDF 非常簡單：

```csharp
page.Rotate = Rotation.on90; // 旋轉 90 度
```

此行可有效地將頁面翻轉到所需的方向。

## 步驟 7：儲存輸出 PDF

修改所有頁面的方向後，將更新的文件儲存到新文件：

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

確保提供新檔案名稱以避免覆蓋原始文件。

## 結論

就是這樣！使用 Aspose.PDF for .NET 變更 PDF 檔案的頁面方向是一個簡單的過程。透過載入文件、循環瀏覽頁面、更新 MediaBox 和儲存文件，您可以輕鬆調整佈局以滿足您的需求。無論您是要修正掃描品質不佳的文件還是要格式化簡報的頁面，本指南都可以幫助您有效率地完成工作。

## 常見問題解答

### 我可以旋轉 PDF 中的特定頁面而不是所有頁面嗎？  
是的，您可以修改循環以透過索引定位特定頁面，而不是遍歷所有頁面。

### 什麼是 `MediaBox`？  
這 `MediaBox` 定義 PDF 檔案中頁面的大小和形狀，確定內容的放置位置。

### Aspose.PDF for .NET 可以與其他文件格式相容嗎？  
是的，Aspose.PDF 可以處理各種檔案格式，包括 HTML、XML、XPS 等。

### 有沒有適用於 .NET 的 Aspose.PDF 免費版本？  
是的，你可以從 [免費試用](https://releases.aspose.com/) 或請求 [臨時執照](https://purchase。aspose.com/temporary-license/).

### 儲存後我可以撤銷更改嗎？  
一旦儲存文檔，更改將是永久性的。建議對原始文件進行複製或保留備份。