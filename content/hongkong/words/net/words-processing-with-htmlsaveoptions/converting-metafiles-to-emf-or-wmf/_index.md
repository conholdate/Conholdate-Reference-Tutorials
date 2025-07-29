---
"description": "了解如何使用 Aspose.Words for .NET 將 Word 文件中的 SVG 影像無縫轉換為 EMF 或 WMF 格式。本指南包含程式碼範例，可協助您獲得準確且相容的結果。"
"linktitle": "將圖元檔轉換為 Emf 或 Wmf"
"second_title": "Aspose.Words文件處理API"
"title": "將圖元檔轉換為 Emf 或 Wmf"
"url": "/zh-hant/words/net/words-processing-with-htmlsaveoptions/converting-metafiles-to-emf-or-wmf/"
"weight": 10
---

## 介紹

高效率管理和轉換圖像格式是建立專業 Word 文件的關鍵。在本指南中，我們將深入探討如何使用 Aspose.Words for .NET 將 SVG 映像轉換為 EMF（增強圖元檔案）或 WMF（Windows 圖元檔案）格式，以實現無縫整合。本教學提供了清晰的逐步說明，幫助開發人員輕鬆完成轉換。

## 將 SVG 轉換為 EMF 或 WMF 的先決條件

為了確保順利的開發體驗，請確認符合以下先決條件：

- Aspose.Words for .NET：從 [Aspose 發佈頁面](https://releases。aspose.com/words/net/).
- .NET Framework：驗證 .NET Framework（或 .NET Core/5/6，取決於您的環境）的安裝。
- 開發環境：推薦使用 Visual Studio，因為它功能強大。
- C# 熟練程度：必須熟悉基本的 C# 程式設計。

## 導入所需的命名空間

在您的專案中，匯入必要的命名空間以存取 Aspose.Words 功能：

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 步驟1：定義文檔目錄

設定儲存Word文檔的目錄路徑。這對於有效管理輸出文件至關重要。

```csharp
string dataDir = @"C:\MyDocuments\";
```

代替 `@"C:\MyDocuments\"` 按照您想要的路徑。

## 步驟2：準備包含SVG的HTML字串

寫一個嵌入 SVG 內容的 HTML 字串。這將允許 Aspose.Words 渲染和處理 SVG。

```csharp
string htmlContent = 
    @"<html>
        <body>
            <svg xmlns='http://www.w3.org/2000/svg' width='300' height='100' viewBox='0 0 300 100'>
                <rect x='10' y='10' width='280' height='80' fill='blue' stroke='black' stroke-width='2'/>
                <text x='20' y='60' fill='white' font-size='20'>Aspose SVG Example</text>
            </svg>
        </body>
    </html>";
```

## 步驟3：設定HTML載入選項

為了確保正確處理 SVG 轉換，請配置 `HtmlLoadOptions` 和 `ConvertSvgToEmf`。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions
{
    ConvertSvgToEmf = true
};
```

## 步驟 4：將 HTML 載入到 Word 文件中

使用配置的載入選項來建立 `Document` HTML 字串中的物件。

```csharp
using (MemoryStream htmlStream = new MemoryStream(Encoding.UTF8.GetBytes(htmlContent)))
{
    Document document = new Document(htmlStream, loadOptions);
}
```

## 步驟 5：配置 EMF/WMF 的儲存選項

自訂儲存選項以定義所需的圖元檔案格式。在這裡，我們選擇 `HtmlMetafileFormat。Emf`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    MetafileFormat = HtmlMetafileFormat.Emf
};
```

## 步驟6：儲存文檔

使用指定的儲存選項儲存文件。

```csharp
document.Save(dataDir + "ConvertedDocument.emf", saveOptions);
```

產生的檔案將包含轉換為 EMF 格式的 SVG 內容。

## 結論

本教學示範如何使用 Aspose.Words for .NET 將 SVG 影像轉換為 EMF 或 WMF 格式。請依照下列步驟操作，您可以增強 Word 文件的相容性和視覺保真度。無論您是要自動建立文件還是準備高品質的報告，此方法都能確保獲得流暢的結果。

## 常見問題解答

### 我可以使用此方法批次處理多個 SVG 嗎？
是的，您可以遍歷包含 SVG 的多個 HTML 文件，並在循環中應用相同的過程。

### EMF 和 WMF 有什麼不同？
EMF 是 WMF 的增強版本，為複雜圖形和更大的資料量提供更好的支援。

### Aspose.Words 與 .NET Core 相容嗎？
是的，Aspose.Words for .NET 支援 .NET Core 和 .NET 5/6，使其適用於現代跨平台應用程式。

### 我可以在輸出中保留原始 SVG 格式嗎？
不，此方法專門將 SVG 轉換為 EMF/WMF。但是，您可以直接將原始 SVG 嵌入到文件中，而無需轉換。

### 哪裡可以下載 Aspose.Words 的免費試用版？
您可以從 [Aspose 發佈頁面](https://releases。aspose.com/).