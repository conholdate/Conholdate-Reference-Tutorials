---
"description": "在本逐步教學中，使用 Aspose.PDF for .NET 解鎖 PDF 操作的強大功能。了解如何透過繪製填充矩形以程式設計方式建立具有視覺吸引力的 PDF 文件。"
"linktitle": "建立填滿矩形"
"second_title": "Aspose.PDF for .NET API參考"
"title": "建立填滿矩形"
"url": "/zh-hant/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## 介紹

您是否曾經想過以程式設計方式創建視覺效果令人驚嘆的 PDF？如果是這樣，那麼您來對地方了！在本教學中，我們將探索 Aspose.PDF for .NET，這是一個簡化 PDF 文件操作的強大函式庫。今天，我們將重點介紹如何在 PDF 文件中建立填充矩形。無論您是經驗豐富的開發人員還是剛起步，本指南都將以友好且引人入勝的方式引導您完成每個步驟。那麼，戴上你的編碼帽，讓我們開始吧！

## 先決條件

在深入研究程式碼之前，請確保您具有以下內容：

1. Visual Studio：在您的機器上安裝 Visual Studio，因為它是 .NET 開發的優秀 IDE。
2. Aspose.PDF for .NET：從下列位置下載並安裝 Aspose.PDF 庫 [這裡](https://releases。aspose.com/pdf/net/).
3. C# 基礎知識：熟悉 C# 程式設計將幫助您更好地理解程式碼片段。

## 步驟 1：建立新項目

1. 開啟 Visual Studio 並建立一個新的控制台應用程式專案。
2. 適當地命名您的項目。

## 第 2 步：新增 Aspose.PDF 引用

1. 在解決方案資源管理器中以滑鼠右鍵按一下您的專案。
2. 選擇管理 NuGet 套件。
3. 搜尋 Aspose.PDF 並安裝最新版本。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

現在我們已經設定好了一切，讓我們深入研究程式碼！

## 步驟3：設定文檔目錄

指定 PDF 的儲存路徑：

```csharp
// 文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替 `"YOUR DOCUMENT DIRECTORY"` 使用您想要儲存 PDF 的機器上的實際路徑。

## 步驟 4：建立文件實例

初始化一個新的 PDF 文件：

```csharp
// 建立 Document 實例
Document doc = new Document();
```

## 步驟 5：新增頁面

每個 PDF 至少需要一頁。讓我們新增一個：

```csharp
// 將頁面新增至 PDF 檔案的頁面集合
Page page = doc.Pages.Add();
```

## 步驟 6：建立圖形實例

一個 `Graph` 實例充當繪製形狀的畫布：

```csharp
// 建立 Graph 實例
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## 步驟 7：將圖表新增至頁面

將圖表附加到頁面：

```csharp
// 將圖形物件加入到頁面實例的段落集合中
page.Paragraphs.Add(graph);
```

## 步驟 8：建立矩形實例

定義矩形的位置和大小：

```csharp
// 建立 Rectangle 實例
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## 步驟 9：指定填滿顏色

為矩形選擇一種顏色。對於此範例，我們將使用紅色：

```csharp
// 指定圖形物件的填滿顏色
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 步驟 10：將矩形加入圖形中

將矩形新增至圖形：

```csharp
// 將矩形物件新增至圖形物件的形狀集合中
graph.Shapes.Add(rect);
```

## 步驟11：儲存PDF文檔

最後，將文檔儲存到指定目錄：

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// 儲存 PDF 文件
doc.Save(dataDir);
```

## 步驟12：確認訊息

列印確認訊息以表示成功：

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## 結論

恭喜！您已成功使用 Aspose.PDF for .NET 在 PDF 文件中建立了一個填滿矩形。這個強大的函式庫為 PDF 操作開啟了無限可能，讓您能夠以程式設計方式產生令人驚嘆的文件。無論您建立報告、發票或任何其他類型的 PDF，Aspose.PDF 都能滿足您的需求。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員以程式設計方式建立、操作和轉換 PDF 文件。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版，您可以使用它來探索該程式庫的功能。你可以下載它 [這裡](https://releases。aspose.com/).

### 有沒有辦法獲得對 Aspose.PDF 的支援？
絕對地！您可以透過 Aspose 論壇獲得支持 [這裡](https://forum。aspose.com/c/pdf/10).

### 我該如何購買 Aspose.PDF？
您可以透過造訪購買頁面購買 Aspose.PDF [這裡](https://purchase。aspose.com/buy).

### 我可以使用 Aspose.PDF 建立哪些類型的形狀？
您可以使用 Aspose.PDF 庫建立各種形狀，包括矩形、圓形、線條等。