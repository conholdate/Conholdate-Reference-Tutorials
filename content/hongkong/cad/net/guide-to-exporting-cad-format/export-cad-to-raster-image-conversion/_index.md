---
"description": "了解如何使用 Aspose.CAD for .NET 將 CAD 佈局有效率地轉換為各種光柵影像格式。本綜合指南將透過清晰的程式碼引導您完成整個過程。"
"linktitle": "匯出 CAD 到光柵影像轉換"
"second_title": "Aspose.CAD .NET - CAD 和 BIM 檔案格式"
"title": "使用 Aspose.CAD for .NET 將 CAD 匯出為光柵影像"
"url": "/zh-hant/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## 介紹

您是否希望使用 Aspose.CAD for .NET 輕鬆地將 CAD 佈局轉換為光柵影像格式？本逐步指南旨在幫助您完成整個過程，並附有簡潔的程式碼片段以獲得流暢的體驗。無論您是經驗豐富的開發人員還是剛起步，本教程都為所有技能水平的人提供了寶貴的見解。

## 先決條件

在開始之前，請確保您已具備以下條件：

- Aspose.CAD for .NET Library：從下載並安裝本庫 [Aspose.CAD 網站](https://releases。aspose.com/cad/net/).
- CAD 圖面檔案：準備好您的 CAD 圖面檔案（例如， `conic_pyramid.dxf`) 準備轉換。

## 導入所需的命名空間

在您的 .NET 專案中，您需要匯入必要的命名空間才能使用 Aspose.CAD 功能。將以下內容新增至程式碼頂部：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## 步驟 1：載入 CAD 繪圖

首先，指定目錄並將 CAD 檔案載入到 Image 實例中：

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// 載入 CAD 繪圖
using (var image = Image.Load(sourceFilePath))
{
    // 繼續下一步
}
```

## 步驟 2：建立光柵化選項

接下來，設定光柵化選項，定義輸出影像所需的尺寸：

```csharp
// 初始化 CadRasterizationOptions
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## 步驟 3：指定轉換層

如果要轉換特定圖層，請將它們新增至柵格化選項中：

```csharp
// 指定要轉換的圖層
rasterizationOptions.Layers = new [] { "LayerA" };
```

## 步驟4：設定JPEG導出選項

現在，為您想要匯出的影像格式建立選項（在本例中為 JPEG）：

```csharp
// 建立用於匯出的 JpegOptions
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## 步驟5：導出為JPEG格式

最後儲存轉換後的影像：

```csharp
// 定義輸出檔案路徑並儲存影像
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## 附加功能：轉換所有圖層

要轉換 CAD 繪圖中的所有圖層，可以實現以下方法：

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // 遍歷各個圖層並將每個圖層儲存為單獨的 JPEG 文件
    // 您的實作程式碼在這裡
}
```

## 結論

恭喜！您已經了解如何使用 Aspose.CAD for .NET 將 CAD 佈局有效轉換為光柵影像格式。本指南提供了一種簡單的方法，適合追求高效能 CAD 轉換的開發人員。

## 常見問題解答

### 我可以匯出不同的圖像格式嗎？

絕對地！簡單交換 `JpegOptions` 與其他格式選項，例如 `PngOptions` 或者 `BmpOptions`，取決於您的需求。

### 有試用版嗎？

是的，您可以按照以下步驟下載試用版來探索功能 [關聯](https://releases。aspose.com/cad/net/).

### 在哪裡可以找到對 Aspose.CAD 的支援？

如需社區支持，請查看 Aspose.CAD [論壇](https://forum.aspose.com/c/cad/19)，或考慮購買許可證以獲得更專業的幫助。

### 可以申請臨時執照嗎？

是的，有臨時許可證；你可以請求一個 [這裡](https://purchase。conholdate.com/temporary-license/).

### 我可以在哪裡取得詳細文件？

存取綜合文檔 [這裡](https://reference.aspose.com/cad/net/) 了解更多。