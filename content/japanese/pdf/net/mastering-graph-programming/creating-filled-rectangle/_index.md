---
"description": "このステップバイステップのチュートリアルで、Aspose.PDF for .NET を使った PDF 操作のパワーを解き放ちましょう。塗りつぶされた四角形を描画することで、視覚的に魅力的な PDF ドキュメントをプログラムで作成する方法を学びます。"
"linktitle": "塗りつぶされた長方形を作成する"
"second_title": "Aspose.PDF for .NET API リファレンス"
"title": "塗りつぶされた長方形を作成する"
"url": "/ja/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## 導入

視覚的に美しいPDFをプログラムで作成したいと思ったことはありませんか？もしそうなら、まさにうってつけのチュートリアルです！このチュートリアルでは、PDFドキュメントの操作を簡素化する強力なライブラリ、Aspose.PDF for .NETを紹介します。今回は、PDFファイル内に塗りつぶされた四角形を作成する方法に焦点を当てます。経験豊富な開発者の方にも、初心者の方にも、このガイドは分かりやすく、魅力的な方法で各ステップを解説します。さあ、コーディングの準備を始めましょう！

## 前提条件

コードに進む前に、次のものを用意してください。

1. Visual Studio: Visual Studio は .NET 開発に最適な IDE なので、お使いのマシンにインストールしてください。
2. Aspose.PDF for .NET: Aspose.PDFライブラリを以下のサイトからダウンロードしてインストールします。 [ここ](https://releases。aspose.com/pdf/net/).
3. C# の基礎知識: C# プログラミングに精通していると、コード スニペットをよりよく理解できるようになります。

## ステップ1: 新しいプロジェクトを作成する

1. Visual Studio を開き、新しいコンソール アプリケーション プロジェクトを作成します。
2. プロジェクトに適切な名前を付けます。

## ステップ2: Aspose.PDF参照を追加する

1. ソリューション エクスプローラーでプロジェクトを右クリックします。
2. NuGet パッケージの管理を選択します。
3. Aspose.PDF を検索し、最新バージョンをインストールします。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

すべての設定が完了したので、コードを見ていきましょう。

## ステップ3: ドキュメントディレクトリを設定する

PDF を保存するパスを指定します:

```csharp
// ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する `"YOUR DOCUMENT DIRECTORY"` PDF を保存するマシン上の実際のパスを入力します。

## ステップ4: ドキュメントインスタンスを作成する

新しい PDF ドキュメントを初期化します。

```csharp
// ドキュメントインスタンスを作成する
Document doc = new Document();
```

## ステップ5: ドキュメントにページを追加する

PDFには少なくとも1ページ必要です。1ページ追加してみましょう。

```csharp
// PDFファイルのページコレクションにページを追加する
Page page = doc.Pages.Add();
```

## ステップ6: グラフインスタンスを作成する

あ `Graph` インスタンスは図形を描画するためのキャンバスとして機能します。

```csharp
// グラフインスタンスを作成する
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## ステップ7: ページにグラフを追加する

グラフをページに添付します。

```csharp
// ページインスタンスの段落コレクションにグラフオブジェクトを追加する
page.Paragraphs.Add(graph);
```

## ステップ8: 長方形インスタンスを作成する

長方形の位置とサイズを定義します。

```csharp
// 長方形インスタンスを作成する
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## ステップ9: 塗りつぶしの色を指定する

長方形の色を選択します。この例では赤を使用します。

```csharp
// グラフオブジェクトの塗りつぶし色を指定する
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## ステップ10: グラフに長方形を追加する

グラフに四角形を追加します。

```csharp
// グラフオブジェクトの図形コレクションに長方形オブジェクトを追加します
graph.Shapes.Add(rect);
```

## ステップ11: PDFドキュメントを保存する

最後に、ドキュメントを指定されたディレクトリに保存します。

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDFファイルを保存する
doc.Save(dataDir);
```

## ステップ12: 確認メッセージ

成功を示す確認メッセージを出力します。

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！Aspose.PDF for .NET を使って、PDF ドキュメントに塗りつぶされた四角形を作成できました。この強力なライブラリは、PDF 操作の可能性を広げ、プログラムで魅力的なドキュメントを生成できるようになります。レポート、請求書、その他あらゆる形式の PDF を作成する場合でも、Aspose.PDF がすべてをカバーします。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者がプログラムによって PDF ドキュメントを作成、操作、変換できるようにするライブラリです。

### Aspose.PDF は無料で使用できますか?
はい、Asposeはライブラリの機能を試すために無料の試用版を提供しています。ダウンロードできます。 [ここ](https://releases。aspose.com/).

### Aspose.PDF のサポートを受ける方法はありますか?
もちろんです！Asposeフォーラムでサポートを受けることができます。 [ここ](https://forum。aspose.com/c/pdf/10).

### Aspose.PDF を購入するにはどうすればよいですか?
Aspose.PDFは購入ページから購入できます。 [ここ](https://purchase。aspose.com/buy).

### Aspose.PDF ではどのような種類の図形を作成できますか?
Aspose.PDF ライブラリを使用すると、長方形、円、線など、さまざまな図形を作成できます。