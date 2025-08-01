---
"description": "このガイドでは、アーカイブ、印刷、またはスペース節約の目的で 1Bpp インデックス付き画像を効率的に作成するための手順とサンプル コードについて説明します。"
"linktitle": "1Bppインデックスを作成"
"second_title": "Aspose.Words ドキュメント処理 API"
"title": "1Bppインデックスを作成"
"url": "/ja/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## 導入

Word文書を白黒画像に変換したいと思ったことはありませんか？デジタルアーカイブ、印刷、あるいは単に容量を節約するためなど、文書を1Bppのインデックス付き画像に変換することは非常に便利です。このガイドでは、Aspose.Words for .NETを使って、この変換を簡単に実現する方法を解説します。さあ、始めましょう！

## 前提条件

コードに進む前に、次のものを用意してください。

- Aspose.Words for .NET: ライブラリをダウンロードしてインストールします。 [ここ](https://releases。aspose.com/words/net/).
- .NET 開発環境: Visual Studio が一般的な選択肢ですが、.NET をサポートする IDE であればどれでも動作します。
- 基本的な C# の知識: C# の知識があると役立ちますが、ここでは簡単に説明します。
- サンプル Word 文書: 変換する文書を準備します。

## ステップ1: 必要な名前空間をインポートする

Aspose.Words を使用するには、関連する名前空間をインポートする必要があります。これは、ドキュメント操作に必要なクラスやメソッドにアクセスするために不可欠です。

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ステップ2: ドキュメントディレクトリを設定する

Word 文書が保存されているディレクトリと、変換した画像を保存するディレクトリへのパスを指定します。

```csharp
// ドキュメントディレクトリへのパス
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## ステップ3: Word文書を読み込む

Word文書を `Aspose.Words.Document` オブジェクト。このオブジェクトを使用すると、プログラムでドキュメントを操作できます。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ4: 画像保存オプションを設定する

次に、 `ImageSaveOptions` ドキュメントを画像として保存する方法を定義します。ここでは、1BppインデックスカラーモードでPNG形式で保存するように設定します。

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // 最初のページのみ変換する
    ImageColorMode = ImageColorMode.BlackAndWhite, // 白黒に設定する
    PixelFormat = ImagePixelFormat.Format1bppIndexed // 1Bppインデックス形式を使用する
};
```

- SaveFormat.Png: 出力形式が PNG になることを指定します。
- PageSet(1): 文書の最初のページのみが変換されることを示します。
- ImageColorMode.BlackAndWhite: 画像が白黒であることを確認します。
- ImagePixelFormat.Format1bppIndexed: ピクセル形式を 1Bpp インデックスに設定し、スペースを最適化します。

## ステップ5: ドキュメントを画像として保存する

最後に、 `Save` の方法 `Document` 変換した画像を保存するオブジェクト。

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## 結論

おめでとうございます！Aspose.Words for .NET を使って、Word 文書を 1bpp のインデックス付き画像に変換できました。この方法は効率的であるだけでなく、様々なアプリケーションに適した高コントラスト画像の作成にも役立ちます。ぜひこの機能をプロジェクトに取り入れてみてください。コーディングを楽しんでください！

## よくある質問

### 1Bpp インデックス画像とは何ですか?
1Bpp (1 ビット/ピクセル) インデックス画像は、各ピクセルが 0 または 1 の 1 ビットで表された白黒画像形式です。この形式はスペース効率が非常に高いため、アーカイブに最適です。

### Word 文書の複数のページを一度に変換できますか?
はい！ `PageSet` の財産 `ImageSaveOptions` 複数のページを含めるか、ドキュメント全体を変換するように設定します。

### Aspose.Words for .NET を使用するにはライセンスが必要ですか?
はい、すべての機能を使用するにはライセンスが必要です。 [仮免許証はこちら](https://purchase。aspose.com/temporary-license/).

### Word 文書を他のどのような画像形式に変換できますか?
Aspose.WordsはJPEG、BMP、TIFFなど様々な形式をサポートしています。 `SaveFormat` の中で `ImageSaveOptions` 希望の形式に変換します。

### Aspose.Words for .NET に関する詳細なドキュメントはどこで入手できますか?
詳細なドキュメントについては、 [Aspose.Words for .NET ドキュメント ページ](https://reference。aspose.com/words/net/).