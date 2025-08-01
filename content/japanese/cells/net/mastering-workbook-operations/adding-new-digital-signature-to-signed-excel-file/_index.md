---
"description": "Aspose.Cells for .NET を使用して、既存の署名済みExcelファイルに新しいデジタル署名を追加する方法を学びましょう。この包括的なガイドでは、すべての前提条件、ステップバイステップの手順、そしてコード例を網羅しています。"
"linktitle": "署名された Excel ファイルに新しいデジタル署名を追加する"
"second_title": "Aspose.Cells .NET Excel 処理 API"
"title": "署名された Excel ファイルに新しいデジタル署名を追加する"
"url": "/ja/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## 導入

今日のデジタル環境において、ドキュメントの真正性と整合性の確保はこれまで以上に重要になっています。デジタル署名は、ドキュメントが改ざんされていないこと、そして正当なソースから発行されたことを確実に検証する手段を提供します。.NETでExcelファイルを操作していて、既に署名済みのファイルに新しいデジタル署名を追加する必要がある場合は、このガイドが最適です。Aspose.Cells for .NETを使用して、既存の署名済みExcelファイルにデジタル署名を追加する手順を詳しく説明します。

## 前提条件

実装に進む前に、次のものを用意してください。

1. Aspose.Cells for .NET: Aspose.Cellsを以下のサイトからダウンロードしてインストールします。 [リリースページ](https://releases。aspose.com/cells/net/).
2. .NET Framework: マシンに .NET Framework がセットアップされていること、および基本的な .NET プログラミング概念を理解していることを確認します。
3. デジタル証明書：.pfx形式の有効なデジタル証明書を取得します。テスト用に自己署名証明書を作成することもできます。
4. 開発環境: Visual Studio などの IDE を使用して C# コードを記述および実行します。
5. サンプル Excel ファイル: すでにデジタル署名されている既存の Excel ファイルがあり、これが新しい署名を追加する対象になります。

これらの前提条件が整ったら、コードに取り掛かりましょう。

## 必要なパッケージをインポートする

必要なクラスとメソッドにアクセスするために、C# ファイルの先頭に次の名前空間を含めます。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## ステップ1: ディレクトリを定義する

ソース ファイルのディレクトリと出力ファイルを保存する場所を指定します。

```csharp
// ソースディレクトリ
string sourceDir = "Your Document Directory"; // 実際のディレクトリに置き換えてください
// 出力ディレクトリ
string outputDir = "Your Document Directory"; // 実際のディレクトリに置き換えてください
```

## ステップ2: 既存の署名済みワークブックを読み込む

すでに署名されている Excel ブックを読み込みます。

```csharp
// すでにデジタル署名されているワークブックをロードします
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## ステップ3: デジタル署名コレクションを作成する

デジタル署名を管理するためのコレクションを作成します。

```csharp
// デジタル署名コレクションを作成する
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## ステップ4: 証明書を読み込む

新しい署名の作成に使用するデジタル証明書をロードします。

```csharp
// 証明書ファイルとそのパスワード
string certFileName = sourceDir + "AsposeDemo.pfx"; // 証明書ファイル
string password = "aspose"; // 証明書のパスワード

// 新しい証明書を作成する
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## ステップ5: 新しいデジタル署名を作成する

次に、新しいデジタル署名を作成し、コレクションに追加します。

```csharp
// 新しいデジタル署名を作成し、コレクションに追加する
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## ステップ6: 署名コレクションをワークブックに追加する

デジタル署名コレクションをワークブックに追加します。

```csharp
// ワークブックにデジタル署名コレクションを追加する
workbook.AddDigitalSignature(dsCollection);
```

## ステップ7: ワークブックを保存する

新しいデジタル署名が含まれたワークブックを保存します。

```csharp
// ワークブックを保存する
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## ステップ8: 成功を確認する

実行が成功したらフィードバックを提供します。

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## 結論

おめでとうございます！Aspose.Cells for .NET を使用して、既に署名済みの Excel ファイルに新しいデジタル署名を追加することができました。このプロセスにより、ドキュメントのセキュリティが強化され、信頼性と整合性が確保されます。

## よくある質問

### デジタル署名とは何ですか?

デジタル署名は、デジタル メッセージまたはドキュメントの信頼性と整合性を検証し、変更されていないことを確認して署名者の ID を確認する数学的なスキームです。

### デジタル署名を作成するには特別な証明書が必要ですか?

はい、有効なデジタル署名を作成するには、信頼できる証明機関 (CA) によって発行されたデジタル証明書が必要です。

### テストに自己署名証明書を使用できますか?

もちろんです！開発やテストの目的では自己署名証明書を使用できますが、本番環境では信頼できる CA からの証明書を使用することをお勧めします。

### 署名されていない文書に署名を追加しようとするとどうなりますか?

まだ署名されていない文書にデジタル署名を追加しようとすると、問題なく機能しますが、元の署名は存在しなくなります。

### Aspose.Cells の詳細情報はどこで入手できますか?

詳細なガイドとAPIリファレンスについては、 [Aspose.Cells ドキュメント](https://reference。aspose.com/cells/net/).