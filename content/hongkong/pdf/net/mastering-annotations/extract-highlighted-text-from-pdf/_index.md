---
"description": "學習如何使用 Aspose.PDF for .NET 提取高亮文本，釋放 PDF 文件的潛力。本指南將指導您從設定到實施的每個步驟。"
"linktitle": "使用 Aspose.PDF for .NET 從 PDF 中提取高亮文本"
"second_title": "Aspose.PDF for .NET API參考"
"title": "使用 Aspose.PDF for .NET 從 PDF 中提取高亮文本"
"url": "/zh-hant/pdf/net/mastering-annotations/extract-highlighted-text-from-pdf/"
"weight": 60
---

## 介紹

處理 PDF 檔案時，提取高亮文字對於資料分析、內容審查或整理筆記至關重要。如果您使用 Aspose.PDF for .NET，那麼您很幸運。本教學將提供清晰的逐步說明，幫助您有效率地從 PDF 文件中提取高亮文字。

## 先決條件

在開始之前，請確保已準備好以下事項：

- Aspose.PDF for .NET Library：從 [發布頁面](https://releases。aspose.com/pdf/net/).
- 開發環境：類似 Visual Studio 的工作環境。
- C# 基礎知識：必須熟悉 C# 和物件導向程式設計。
- Aspose 許可證：雖然您可以先免費試用，但 [臨時執照](https://purchase.aspose.com/temporary-license/) 或完整許可證 [這裡](https://purchase.aspose.com/buy) 將提供不受限制的訪問。

## 導入必要的命名空間

首先在 C# 專案中匯入所需的命名空間：

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些命名空間提供處理 PDF 文件和註釋所需的類別和方法的存取。

## 步驟 1：設定項目目錄

指定 PDF 檔案所在的目錄：

```csharp
// 文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

確保用 PDF 檔案的實際目錄替換路徑。

## 第 2 步：載入 PDF 文檔

使用以下程式碼載入PDF文件：

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

確保指定的檔案存在於給定的目錄中。

## 步驟 3：造訪頁面上的註釋

若要存取註釋，請循環遍歷所需頁面（在本例中為第一頁）上的註釋：

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
    if (annotation is TextMarkupAnnotation)
    {
        TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

此程式碼過濾 `TextMarkupAnnotation` 類型，代表亮點。

## 步驟 4：提取突出顯示的文本

現在，從突出顯示的註釋中提取並顯示文字：

```csharp
        TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
        foreach (TextFragment tf in collection)
        {
            Console.WriteLine(tf.Text);
        }
    }
}
```

這將檢索與突出顯示相關的所有標記文字片段並將其列印到控制台。

## 結論

使用 Aspose.PDF for .NET 從 PDF 中提取高亮文字非常簡單，並且可以顯著增強您的文件處理流程。按照上述步驟，您可以有效率地收集高亮文本，用於各種應用程序，例如報告準備或資料分析。

## 常見問題解答

### 我可以提取其他類型的註釋嗎？
是的，只需調整 `if` 條件包括不同的註釋類型，如 `TextAnnotation` 或者 `StampAnnotation`。

### 如何從所有 PDF 頁面中提取突出顯示的文字？
您可以使用以下方法循環遍歷所有頁面：
```csharp
for (int i = 1; i <= doc.Pages.Count; i++)
{
    foreach (Annotation annotation in doc.Pages[i].Annotations) { ... }
}
```

### Aspose.PDF for .NET 是否需要許可證？
可以免費試用，但請考慮 [臨時執照](https://purchase.aspose.com/temporary-license/) 或獲得完整存取權限的完整許可證。

### 我可以將提取的文字儲存到文件中嗎？
當然！您可以修改程式碼，將提取的文字寫入文字檔案。

### Aspose.PDF 是否支援其他平台？
是的，Aspose.PDF 也支援 Java 和其他平台，提供類似的功能。