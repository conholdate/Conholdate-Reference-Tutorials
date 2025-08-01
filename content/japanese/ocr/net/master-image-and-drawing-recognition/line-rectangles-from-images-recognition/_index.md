---
"description": "Aspose.OCRを使用して、.NETアプリケーションに光学式文字認識（OCR）を実装する方法を学びましょう。この包括的なガイドでは、認識された線から四角形を抽出するプロセスを詳しく説明します。"
"linktitle": "画像認識から直線四角形を抽出する"
"second_title": "Aspose.OCR .NET API"
"title": "画像認識から直線四角形を抽出する"
"url": "/ja/ocr/net/master-image-and-drawing-recognition/line-rectangles-from-images-recognition/"
"weight": 10
---

## 導入

Aspose.OCR for .NETの世界へようこそ。これは、光学式文字認識（OCR）を.NETアプリケーションに統合するために設計された優れたツールです。経験豊富な開発者の方にも、好奇心旺盛な初心者の方にも、このガイドでは、画像内の認識されたテキストから線を表す四角形を取得する手順を詳しく説明します。

## 前提条件

始める前に、以下のものが用意されていることを確認してください。

- C# および .NET 開発に関する基本的な知識。
- Visual Studio のような統合開発環境 (IDE)。
- Aspose.OCR for .NETライブラリがインストールされています。ダウンロードできます。 [ここ](https://releases。aspose.com/ocr/net/).
- 認識用のテキストを含むサンプル画像。

## 必要な名前空間

まず、プロジェクトに必要な名前空間を追加する必要があります。C#ファイルの先頭に以下の行を追加してください。

```csharp
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using Aspose.OCR;
```

OCR 画像内の線の四角形を取得するには、次の手順に従います。

## ステップ1: ドキュメントディレクトリを設定する

画像ファイルが保存されているディレクトリを指定します。

```csharp
// ドキュメントディレクトリへのパスを定義する
string dataDir = "Your Document Directory";
```

必ず交換してください `"Your Document Directory"` 実際のパスを使用します。

## ステップ2: Aspose.OCRを初期化する

インスタンスを作成する `AsposeOcr` 機能にアクセスするためのクラス:

```csharp
// Aspose.OCR API を初期化する
AsposeOcr api = new AsposeOcr();
```

## ステップ3: 画像パスを指定する

処理する画像ファイルへのフルパスを定義します。

```csharp
// 画像のフルパスを指定します
string fullPath = dataDir + "sample.png";
```

## ステップ4: 画像を認識し、線分の四角形を取得する

これで、 `GetRectangles` 認識されたテキスト行の四角形を抽出する方法:

```csharp
// 指定された画像内の線の矩形を取得します
List<Rectangle> lines = api.GetRectangles(fullPath, AreasType.LINES, false);
```

## ステップ5: 結果を出力する

最後に、検出された各線の四角形の座標をコンソールに出力します。

```csharp
// 検出された長方形の座標を表示する
Console.WriteLine("Areas coordinates:");
lines.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
```

## 結論

おめでとうございます！Aspose.OCR for .NET を使用して、OCR画像内の線分の矩形を取得できました。この技術は、アプリケーションにおけるテキスト抽出と処理に新たな可能性をもたらします。

## よくある質問

### Aspose.OCR for .NET はどんな種類の画像でも使用できますか?

はい、Aspose.OCR はさまざまな画像形式をサポートしており、OCR アプリケーションに柔軟性を提供します。

### OCR認識の精度はどのくらいですか？

Aspose.OCR は高度なアルゴリズムを使用して、さまざまなシナリオに適した高精度のテキスト認識を実現します。

### 試用版はありますか？

はい、Aspose.OCR for .NETの機能を試すには、以下のダウンロードを行ってください。 [無料トライアル](https://releases。aspose.com/).

### 詳細なドキュメントはどこで見つかりますか?

包括的なドキュメントは以下にあります [ここ](https://reference.aspose.com/ocr/net/)詳細な情報とガイドラインを提供します。

### さらにサポートが必要な場合や質問がある場合は、

ディスカッションに参加する [Aspose.OCR フォーラム](https://forum.aspose.com/c/ocr/16) コミュニティのサポートのため。