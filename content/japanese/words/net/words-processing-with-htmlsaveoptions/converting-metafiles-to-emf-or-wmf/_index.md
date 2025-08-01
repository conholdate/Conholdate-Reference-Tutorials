---
"description": "Aspose.Words for .NET を使用して、Word 文書内の SVG 画像を EMF または WMF 形式にシームレスに変換する方法を学びます。正確で互換性のある結果を得るためのコード例を交えたステップバイステップのガイドです。"
"linktitle": "メタファイルをEMFまたはWMFに変換する"
"second_title": "Aspose.Words ドキュメント処理 API"
"title": "メタファイルをEMFまたはWMFに変換する"
"url": "/ja/words/net/words-processing-with-htmlsaveoptions/converting-metafiles-to-emf-or-wmf/"
"weight": 10
---

## 導入

画像形式の効率的な管理と変換は、プロフェッショナルなWord文書を作成する上で不可欠です。このガイドでは、Aspose.Words for .NETを使用してSVG画像をEMF（拡張メタファイル）またはWMF（Windowsメタファイル）形式に変換し、シームレスに統合する方法について詳しく説明します。このチュートリアルでは、開発者が変換を簡単に実装できるよう、分かりやすく段階的な手順を説明します。

## SVG を EMF または WMF に変換するための前提条件

スムーズな開発エクスペリエンスを確保するには、次の前提条件が満たされていることを確認してください。

- Aspose.Words for .NET: 最新バージョンを以下から入手してください。 [Aspose リリースページ](https://releases。aspose.com/words/net/).
- .NET Framework: .NET Framework (または環境に応じて .NET Core/5/6) のインストールを確認します。
- 開発環境: 堅牢な機能を備えた Visual Studio が推奨されます。
- C# の熟練度: C# プログラミングに関する基本的な知識が必須です。

## 必要な名前空間のインポート

プロジェクトで、Aspose.Words の機能にアクセスするために必要な名前空間をインポートします。

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ステップ1: ドキュメントディレクトリを定義する

Word文書を保存するディレクトリパスを設定します。これは出力ファイルを効率的に管理するために不可欠です。

```csharp
string dataDir = @"C:\MyDocuments\";
```

交換する `@"C:\MyDocuments\"` ご希望のパスで。

## ステップ2: SVGを含むHTML文字列を準備する

SVGコンテンツを埋め込んだHTML文字列を作成します。これにより、Aspose.WordsがSVGをレンダリングおよび処理できるようになります。

```csharp
string htmlContent = 
    @"<html>
        <body>
            <svg xmlns='http://www.w3.org/2000/svg' 幅='300' 高さ='100' ビューボックス='0 0 300 100'>
                <rect x='10' y='10' width='280' height='80' fill='blue' stroke='black' stroke-width='2'/>
                <text x='20' y='60' fill='white' font-size='20'>Aspose SVG Example</text>
            </svg>
        </body>
    </html>";
```

## ステップ3: HTML読み込みオプションを構成する

SVG変換を適切に処理するには、 `HtmlLoadOptions` と `ConvertSvgToEmf`。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions
{
    ConvertSvgToEmf = true
};
```

## ステップ4: HTMLをWord文書に読み込む

設定されたロードオプションを使用して、 `Document` HTML 文字列からオブジェクトを取得します。

```csharp
using (MemoryStream htmlStream = new MemoryStream(Encoding.UTF8.GetBytes(htmlContent)))
{
    Document document = new Document(htmlStream, loadOptions);
}
```

## ステップ5: EMF/WMFの保存オプションを設定する

保存オプションをカスタマイズして、希望するメタファイル形式を定義します。ここでは、 `HtmlMetafileFormat。Emf`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    MetafileFormat = HtmlMetafileFormat.Emf
};
```

## ステップ6: ドキュメントを保存する

指定された保存オプションを使用してドキュメントを保存します。

```csharp
document.Save(dataDir + "ConvertedDocument.emf", saveOptions);
```

結果のファイルには、EMF 形式に変換された SVG コンテンツが含まれます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してSVG画像をEMFまたはWMF形式に変換する方法を説明しました。これらの手順に従うことで、Word文書の互換性と視覚的な忠実性を向上させることができます。文書作成の自動化や高品質なレポートの作成など、どのような場合でも、この方法を使えばシームレスな結果が得られます。

## よくある質問

### この方法を使用して複数の SVG をバッチ処理できますか?
はい、SVG を含む複数の HTML ファイルを反復処理し、ループで同じプロセスを適用できます。

### EMF と WMF の違いは何ですか?
EMF は WMF の拡張バージョンであり、複雑なグラフィックや大きなデータ サイズをより適切にサポートします。

### Aspose.Words は .NET Core と互換性がありますか?
はい、Aspose.Words for .NET は .NET Core と .NET 5/6 をサポートしており、最新のクロスプラットフォーム アプリケーションに適しています。

### 出力で元の SVG 形式を保持できますか?
いいえ、この方法はSVGをEMF/WMFに変換するものです。ただし、元のSVGを変換せずにドキュメントに直接埋め込むことで、元のSVGを維持できます。

### Aspose.Words の無料試用版はどこからダウンロードできますか?
無料トライアルは以下からダウンロードできます。 [Aspose リリースページ](https://releases。aspose.com/).