---
"description": "Aspose.PDF for .NET を使って、PDF ファイルのページの向きを簡単に調整する方法をご紹介します。このステップバイステップガイドでは、ドキュメントの読み込み、回転、保存の手順をわかりやすく説明します。"
"linktitle": "PDFページの向きを変更する"
"second_title": "Aspose.PDF for .NET API リファレンス"
"title": "PDFページの向きを変更する"
"url": "/ja/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## 導入

ページの向きが全く狂っているPDFファイルに遭遇したことはありませんか？スキャンが間違っていた文書でも、単にレイアウトを変えたいだけの文書でも、向きを調整するだけで状況は大きく変わります。Aspose.PDF for .NETは、ページの向きの変更を含め、PDFファイルを操作するための強力で使いやすいツールを提供します。このガイドでは、縦向きから横向きへ、あるいはその逆へ切り替える手順をステップバイステップで解説します。

## 前提条件

詳細に入る前に、次のものを用意しておいてください。

- Aspose.PDF for .NET: Aspose.PDFライブラリがインストールされていることを確認してください。まだインストールされていない場合は、 [ここからダウンロード](https://releases。aspose.com/pdf/net/).
- .NET 開発環境: .NET 開発には、Visual Studio、JetBrains Rider、またはその他の任意の IDE を使用できます。
- C# の基本知識: C# に精通していると、より簡単に理解できるようになります。
- PDFファイル：テスト用にサンプルのPDFファイルを用意してください。自分で作成するか、オンラインでサンプルをダウンロードすることもできます。

初めての方は、Aspose.PDFを試してみることを検討してください。 [無料の一時ライセンス](https://purchase.aspose.com/temporary-license/) 決める前に [フルバージョンを購入する](https://purchase。aspose.com/buy).

## 名前空間のインポート

PDFページを操作するには、まずC#プロジェクトに必要な名前空間をインポートする必要があります。コードファイルの先頭に次の行を追加してください。

```csharp
using System.IO;
using Aspose.Pdf;
```

すべての準備ができたので、始めましょう!

## ステップ1: PDFドキュメントを読み込む

最初のステップは、変更したいPDFファイルを読み込むことです。 `Document` Aspose.PDF 名前空間からのクラス:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

必ず交換してください `"YOUR DOCUMENT DIRECTORY"` PDF ファイルへの実際のパスを入力します。

## ステップ2: 各ページをループする

次に、PDFドキュメントの各ページをループ処理します。これにより、すべてのページに向きの変更を適用できます。

```csharp
foreach (Page page in doc.Pages)
{
    // 各ページを操作する
}
```

## ステップ3: ページのメディアボックスにアクセスする

各PDFページには `MediaBox` 境界を定義する要素です。現在の向きを確認し、調整するには、この要素にアクセスする必要があります。

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

その `MediaBox` 幅や高さなど、ページの寸法を指定します。

## ステップ4：幅と高さを入れ替える

ページの向きを変更するには、幅と高さの値を入れ替えます。この調整により、ページのサイズが変更されます。

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

ここで、新しい寸法を計算し、左下隅の位置を変更します（`LLY`） それに応じて。

## ステップ5: MediaBoxとCropBoxを更新する

新しいディメンションができたので、これらの変更を `MediaBox` そして `CropBox` ページが正しく表示されるようにするには:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## ステップ6: ページを回転する

向きの変更を完了するには、ページを回転させます。Aspose.PDFを使えば簡単です。

```csharp
page.Rotate = Rotation.on90; // 90度回転
```

この行は、ページを目的の方向に効果的に反転します。

## ステップ7: 出力PDFを保存する

すべてのページの向きを変更したら、更新されたドキュメントを新しいファイルに保存します。

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

元のドキュメントが上書きされないように、必ず新しいファイル名を指定してください。

## 結論

これで完了です！Aspose.PDF for .NET を使えば、PDF ファイルのページの向きを簡単に変更できます。ドキュメントを読み込み、ページをループ処理し、MediaBox を更新してファイルを保存するだけで、ニーズに合わせてレイアウトを簡単に調整できます。スキャンの粗いドキュメントを修正する場合でも、プレゼンテーション用にページをフォーマットする場合でも、このガイドは作業を効率的に行うのに役立ちます。

## よくある質問

### PDF 内のすべてのページではなく、特定のページを回転できますか?  
はい、すべてのページを反復処理するのではなく、インデックスによって特定のページをターゲットにするようにループを変更できます。

### 何ですか `MediaBox`？  
その `MediaBox` PDF ファイル内のページのサイズと形状を定義し、コンテンツが配置される場所を決定します。

### Aspose.PDF for .NET は他のファイル形式でも動作しますか?  
はい、Aspose.PDF は HTML、XML、XPS など、さまざまなファイル形式を処理できます。

### Aspose.PDF for .NET の無料版はありますか?  
はい、まずは [無料トライアル](https://releases.aspose.com/) またはリクエスト [一時ライセンス](https://purchase。aspose.com/temporary-license/).

### 一度保存した変更を元に戻すことはできますか?  
ドキュメントを保存すると、変更は永続的に保存されます。元のファイルのコピーで作業するか、バックアップを保存しておくことをお勧めします。