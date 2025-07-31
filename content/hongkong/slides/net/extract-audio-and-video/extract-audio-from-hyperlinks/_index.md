---
"description": "了解如何使用 Aspose.Slides for .NET 從 PowerPoint 簡報中的超連結中提取音訊。本逐步指南提供了清晰的說明。"
"linktitle": "從超連結中提取音頻"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "使用 Aspose.Slides 從 PowerPoint 中的超連結提取音頻"
"url": "/zh-hant/slides/net/extract-audio-and-video/extract-audio-from-hyperlinks/"
"weight": 12
---

## 介紹

在多媒體簡報中，音訊顯著增強了投影片的影響力。如果您曾經遇到過帶有音訊超連結的 PowerPoint 演示文稿，並想知道如何提取該音訊用於其他用途，那麼您來對地方了。本指南將引導您完成使用 Aspose.Slides for .NET 程式庫從 PowerPoint 簡報中的超連結中提取音訊的過程。

## 先決條件

在開始之前，請確保您具備以下條件：

### Aspose.Slides for .NET 函式庫

確保您已安裝 Aspose.Slides for .NET 程式庫。如果你還沒有下載，你可以從 [Aspose.Slides for .NET 文檔](https://reference。aspose.com/slides/net/).

### 帶有音訊超連結的 PowerPoint 簡報

您需要一個包含具有相關音訊的超連結的 PowerPoint 簡報 (PPTX)。本簡報將成為您擷取音訊的來源。

## 導入所需的命名空間

為了有效地使用 Aspose.Slides for .NET，您需要將下列命名空間匯入到您的 C# 專案中：

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

現在我們已經準備好一切，讓我們將提取過程分解為簡單的步驟。

## 步驟 1：定義文件目錄

首先指定 PowerPoint 簡報所在的目錄。代替 `"Your Document Directory"` 與實際路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 第 2 步：載入 PowerPoint 簡報

接下來，載入包含音訊超連結的 PowerPoint 簡報 (PPTX)。代替 `"HyperlinkSound.pptx"` 使用您的實際簡報文件名稱。

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // 繼續下一步。
}
```

## 步驟 3：造訪超連結聲音

從第一張投影片上的第一個形狀檢索超連結。如果這個超連結有相關的聲音，我們就可以繼續提取它。

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // 繼續下一步。
}
```

## 步驟 4：從超連結中提取音頻

如果超連結包含聲音，我們可以將其提取為位元組數組並將其儲存為媒體檔案。

```csharp
// 將超連結聲音提取為位元組數組
byte[] audioData = link.Sound.BinaryData;

// 指定要儲存提取的音訊的路徑
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// 將提取的音訊儲存到媒體文件
File.WriteAllBytes(outMediaPath, audioData);
```

恭喜！您已成功使用 Aspose.Slides for .NET 從 PowerPoint 簡報中的超連結中提取音訊。現在您可以在多媒體專案中使用此音訊。

## 結論

Aspose.Slides for .NET 提供了一種強大且使用者友好的方式來從 PowerPoint 簡報中的超連結中提取音訊。透過本指南中概述的步驟，您可以輕鬆地重複使用簡報中的音訊內容來增強您的專案。

## 常見問題解答

### Aspose.Slides for .NET 是一個免費函式庫嗎？
不，Aspose.Slides for .NET 是一個商業庫，但您可以下載免費試用版來探索其功能 [這裡](https://releases。aspose.com/).

### 我可以從 PPT 等較舊的 PowerPoint 格式中提取音訊嗎？
是的，Aspose.Slides for .NET 支援 PPTX 和 PPT 格式的音訊擷取。

### 是否有 Aspose.Slides 支持的社區論壇？
絕對地！您可以在 [Aspose.Slides社群論壇](https://forum。aspose.com/).

### 我可以為短期專案購買 Aspose.Slides 的臨時授權嗎？
是的，您可以透過造訪以下網址取得臨時許可證，以滿足您的短期專案需求 [此連結](https://purchase。aspose.com/temporary-license/).

### 除了 MPG 之外，還有其他支援提取的音訊格式嗎？
是的，Aspose.Slides for .NET 允許提取各種音訊格式。提取後，您可以將音訊轉換為您喜歡的格式。