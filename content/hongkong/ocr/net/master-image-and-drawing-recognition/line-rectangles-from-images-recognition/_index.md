---
"description": "了解如何使用 Aspose.OCR 在 .NET 應用程式中實現光學字元辨識 (OCR)。本綜合指南將引導您完成提取已識別線條的矩形的過程。"
"linktitle": "從影像辨識中提取線矩形"
"second_title": "Aspose.OCR .NET API"
"title": "從影像辨識中提取線矩形"
"url": "/zh-hant/ocr/net/master-image-and-drawing-recognition/line-rectangles-from-images-recognition/"
"weight": 10
---

## 介紹

歡迎來到 Aspose.OCR for .NET 的世界，這是一款令人印象深刻的工具，旨在將光學字元辨識 (OCR) 整合到您的 .NET 應用程式中。無論您是經驗豐富的開發人員還是好奇的新手，本指南都將引導您從圖像中識別的文本中獲取代表線條的矩形的步驟。

## 先決條件

在開始之前，請確保已準備好以下事項：

- C# 和 .NET 開發的基本知識。
- 像 Visual Studio 這樣的整合開發環境 (IDE)。
- 已安裝 Aspose.OCR for .NET 程式庫。你可以下載它 [這裡](https://releases。aspose.com/ocr/net/).
- 包含用於識別的文字的範例圖像。

## 必需的命名空間

首先，您需要為項目添加必要的命名空間。在 C# 檔案的頂部包含以下行：

```csharp
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using Aspose.OCR;
```

請依照下列步驟擷取 OCR 影像中的線條矩形。

## 步驟 1：設定文檔目錄

指定圖像檔案所在的目錄：

```csharp
// 定義文檔目錄的路徑
string dataDir = "Your Document Directory";
```

確保更換 `"Your Document Directory"` 與實際路徑。

## 第 2 步：初始化 Aspose.OCR

建立一個實例 `AsposeOcr` 類別來存取其功能：

```csharp
// 初始化 Aspose.OCR API
AsposeOcr api = new AsposeOcr();
```

## 步驟3：指定影像路徑

定義要處理的影像檔案的完整路徑：

```csharp
// 指定影像的完整路徑
string fullPath = dataDir + "sample.png";
```

## 步驟 4：辨識影像並取得線條矩形

現在，您可以使用 `GetRectangles` 提取已識別文字行的矩形的方法：

```csharp
// 擷取指定影像中的線條矩形
List<Rectangle> lines = api.GetRectangles(fullPath, AreasType.LINES, false);
```

## 步驟5：輸出結果

最後，將每個偵測到的線矩形的座標列印到控制台：

```csharp
// 顯示檢測到的矩形的座標
Console.WriteLine("Areas coordinates:");
lines.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
```

## 結論

恭喜！您已成功使用 Aspose.OCR for .NET 擷取 OCR 影像中的線條矩形。這項技術為您的應用程式中的文字擷取和處理開闢了無數的可能性。

## 常見問題解答

### 我可以將 Aspose.OCR for .NET 用於任何類型的圖像嗎？

是的，Aspose.OCR 支援各種圖像格式，為您的 OCR 應用程式提供靈活性。

### OCR辨識的準確率是多少？

Aspose.OCR採用先進的演算法，實現了文字辨識的高精度，適用於多種場景。

### 有試用版嗎？

是的，您可以透過下載 [免費試用](https://releases。aspose.com/).

### 在哪裡可以找到詳細的文件？

可以找到全面的文檔 [這裡](https://reference.aspose.com/ocr/net/)，提供深入的資訊和指導。

### 需要進一步的協助或有疑問嗎？

加入討論 [Aspose.OCR 論壇](https://forum.aspose.com/c/ocr/16) 尋求社區支持。