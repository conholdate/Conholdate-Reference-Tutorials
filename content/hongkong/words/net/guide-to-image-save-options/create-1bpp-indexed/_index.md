---
"description": "本指南提供逐步說明和範例程式碼，協助您有效率地建立 1Bpp 索引影像，用於存檔、列印或節省空間。"
"linktitle": "建立 1Bpp 索引"
"second_title": "Aspose.Words文件處理API"
"title": "建立 1Bpp 索引"
"url": "/zh-hant/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## 介紹

您是否需要將 Word 文件轉換為黑白影像？無論是為了數位存檔、列印還是僅僅為了節省空間，將文件轉換為 1Bpp 索引影像都非常有用。在本指南中，我們將介紹使用 Aspose.Words for .NET 實現此目的的簡單方法。讓我們開始吧！

## 先決條件

在深入研究程式碼之前，請確保您已具備以下條件：

- Aspose.Words for .NET：從以下位置下載並安裝程式庫 [這裡](https://releases。aspose.com/words/net/).
- .NET 開發環境：雖然 Visual Studio 是個受歡迎的選擇，但任何支援 .NET 的 IDE 都可以使用。
- 基本 C# 知識：熟悉 C# 會有所幫助，但我們會讓事情變得簡單。
- 範例 Word 文件：準備好要轉換的文件。

## 步驟 1：導入必要的命名空間

若要使用 Aspose.Words，您需要匯入相關的命名空間。這對於存取文件操作所需的類別和方法至關重要。

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 第 2 步：設定文檔目錄

指定儲存 Word 文件的目錄路徑以及要儲存轉換後影像的目錄路徑。

```csharp
// 文檔目錄的路徑
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## 步驟3：載入Word文檔

將您的 Word 文件載入到 `Aspose.Words.Document` 目的。該物件允許您以程式設計方式操作文件。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步驟 4：設定影像儲存選項

接下來，設定 `ImageSaveOptions` 定義如何將文件儲存為圖像。我們將把它配置為使用 1Bpp 索引顏色模式儲存為 PNG 格式。

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // 僅轉換第一頁
    ImageColorMode = ImageColorMode.BlackAndWhite, // 設定為黑白
    PixelFormat = ImagePixelFormat.Format1bppIndexed // 使用 1Bpp 索引格式
};
```

- SaveFormat.Png：指定輸出格式為 PNG。
- PageSet(1)：表示僅轉換文件的第一頁。
- ImageColorMode.BlackAndWhite：確保影像是黑白色的。
- ImagePixelFormat.Format1bppIndexed：將像素格式設定為 1Bpp 索引，以優化空間。

## 步驟5：將文件儲存為影像

最後，使用 `Save` 方法 `Document` 物件來保存轉換後的影像。

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## 結論

恭喜！您已成功使用 Aspose.Words for .NET 將 Word 文件轉換為 1Bpp 索引圖片。這種方法不僅高效，而且還可以幫助您創建適合各種應用的高對比度影像。請隨意將此功能整合到您的專案中。編碼愉快！

## 常見問題解答

### 什麼是 1Bpp 索引圖像？
1Bpp（每像素 1 位元）索引影像是一種黑白影像格式，其中每個像素由一個位元（0 或 1）表示。這種格式具有很高的空間效率，非常適合存檔。

### 我可以一次轉換 Word 文件的多頁嗎？
是的！只需修改 `PageSet` 財產 `ImageSaveOptions` 包括多個頁面或將其設定為轉換整個文件。

### 我需要許可證才能使用 Aspose.Words for .NET 嗎？
是的，需要許可證才能使用全部功能。您可以獲得 [此處為臨時駕照](https://purchase。aspose.com/temporary-license/).

### 我可以將 Word 文件轉換為哪些其他圖像格式？
Aspose.Words 支援多種格式，包括 JPEG、BMP 和 TIFF。只需改變 `SaveFormat` 在 `ImageSaveOptions` 為您想要的格式。

### 在哪裡可以找到有關 Aspose.Words for .NET 的更多文件？
如需完整文檔，請訪問 [Aspose.Words for .NET 文件頁面](https://reference。aspose.com/words/net/).