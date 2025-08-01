---
"description": "Aspose.CAD for .NET を使用して、CADレイアウトを様々なラスター画像形式に効率的に変換する方法を学びましょう。この包括的なガイドでは、分かりやすいコードでプロセスを詳しく説明します。"
"linktitle": "CADからラスターイメージへの変換エクスポート"
"second_title": "Aspose.CAD .NET - CAD および BIM ファイル形式"
"title": "Aspose.CAD for .NET を使用した CAD からラスター イメージへのエクスポート"
"url": "/ja/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## 導入

Aspose.CAD for .NET を使って、CAD レイアウトをラスター画像形式に簡単に変換したいとお考えですか？このステップバイステップガイドは、スムーズな操作性を実現する簡潔なコードスニペットを交えながら、プロセスを分かりやすく解説します。経験豊富な開発者の方にも、初心者の方にも、このチュートリアルはあらゆるスキルレベルの方々に役立つ情報を提供します。

## 前提条件

始める前に、次のものがあることを確認してください。

- Aspose.CAD for .NET ライブラリ: ライブラリを以下のサイトからダウンロードしてインストールします。 [Aspose.CAD ウェブサイト](https://releases。aspose.com/cad/net/).
- CAD図面ファイル: CAD図面ファイル（例： `conic_pyramid.dxf`）変換の準備が整いました。

## 必要な名前空間をインポートする

.NETプロジェクトでは、Aspose.CAD関数を利用するために必要な名前空間をインポートする必要があります。コードの先頭に以下のコードを追加してください。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## ステップ1：CAD図面を読み込む

まず、ディレクトリを指定して、CAD ファイルをイメージ インスタンスに読み込みます。

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// CAD図面を読み込む
using (var image = Image.Load(sourceFilePath))
{
    // 次のステップに進む
}
```

## ステップ2: ラスタライズオプションを作成する

次に、ラスタライズ オプションを設定し、出力画像の希望の寸法を定義します。

```csharp
// CadRasterizationOptions を初期化する
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## ステップ3: 変換するレイヤーを指定する

特定のレイヤーを変換する場合は、ラスタライズ オプションに追加します。

```csharp
// 変換するレイヤーを指定してください
rasterizationOptions.Layers = new [] { "LayerA" };
```

## ステップ4：JPEGエクスポートオプションを設定する

次に、エクスポートする画像形式 (この場合は JPEG) のオプションを作成します。

```csharp
// エクスポート用のJpegOptionsを作成する
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## ステップ5：JPEG形式でエクスポートする

最後に、変換した画像を保存します。

```csharp
// 出力ファイルのパスを定義して画像を保存する
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## 追加機能: すべてのレイヤーを変換

CAD 図面内のすべてのレイヤーを変換するには、次のようなメソッドを実装できます。

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // レイヤーを反復処理し、それぞれを個別の JPEG ファイルとして保存します。
    // 実装コードをここに記入
}
```

## 結論

おめでとうございます！Aspose.CAD for .NET を使用して、CADレイアウトをラスターイメージ形式に効率的に変換する方法を学習しました。このガイドでは、効率的なCAD変換を目指す開発者に適した、分かりやすいアプローチを紹介します。

## よくある質問

### 異なる画像形式でエクスポートできますか?

もちろんです！交換するだけです `JpegOptions` 他のフォーマットオプション、例えば `PngOptions` または `BmpOptions`ニーズに応じて異なります。

### 試用版はありますか？

はい、以下の手順に従って試用版をダウンロードし、機能を試してみることができます。 [リンク](https://releases。aspose.com/cad/net/).

### Aspose.CAD のサポートはどこで受けられますか?

コミュニティサポートについては、Aspose.CADをご覧ください。 [フォーラム](https://forum.aspose.com/c/cad/19)、またはより専門的なサポートを受けるためにライセンスの購入を検討してください。

### 一時ライセンスは可能ですか？

はい、一時ライセンスは利用可能です。申請してください。 [ここ](https://purchase。conholdate.com/temporary-license/).

### 詳細なドキュメントにはどこでアクセスできますか?

包括的なドキュメントをご覧ください [ここ](https://reference.aspose.com/cad/net/) 詳細についてはこちらをご覧ください。