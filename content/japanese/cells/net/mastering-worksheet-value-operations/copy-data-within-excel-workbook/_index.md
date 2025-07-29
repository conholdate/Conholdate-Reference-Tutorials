---
"description": "Aspose.Cells for .NET を使用して、Excel ブック内のデータを効率的にコピーする方法を学びましょう。このステップバイステップガイドに従うことで、シートの複製、データの転送、Excel ファイルの管理が簡単になります。"
"linktitle": "Aspose.Cells for .NET を使用して Excel ブック内のデータをコピーする"
"second_title": "Aspose.Cells .NET Excel 処理 API"
"title": "Aspose.Cells for .NET を使用して Excel ブック内のデータをコピーする"
"url": "/ja/cells/net/mastering-worksheet-value-operations/copy-data-within-excel-workbook/"
"weight": 12
---

## 導入

この詳細なガイドでは、Aspose.Cells for .NET を使用して同じブック内でデータをコピーする方法を説明します。以下の手順に従って、シートの内容と書式を維持しながら、プログラムでシートを複製する方法を習得できます。

## Aspose.Cells を使用して Excel でデータをコピーするための前提条件

コーディングプロセスに進む前に、すべてが整っていることを確認しましょう。

1. Aspose.Cells for .NET ライブラリ: Aspose.Cells for .NET ライブラリがインストールされている必要があります。最新バージョンは以下からダウンロードできます。 [Aspose.Cells for .NET のダウンロード ページ](https://releases。aspose.com/cells/net/).
2. 開発環境: コードの記述と実行には、Visual Studio などの .NET 互換 IDE が必要です。
3. Asposeライセンス：無料トライアルまたは購入ライセンスをご利用いただけます。詳細については、こちらをご覧ください。 [ここ](https://purchase。aspose.com/temporary-license/).

前提条件が設定されると、ライブラリの使用を開始する準備が整います。

## 必要なパッケージのインポート

まず、Aspose.Cellsから関連する名前空間をインポートする必要があります。これにより、Aspose.Cellsが提供するクラスとメソッドを使用してExcelファイルを操作できるようになります。

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

これらの名前空間は、 `Workbook` クラス（Excelファイルを操作する）と `WorksheetCollection` (ワークブック内の複数のシートにアクセスするため)。

## ステップ1: ワークブックのファイルパスを初期化する

コードを整理するには、ワークブックが配置されているファイルパスと、変更したファイルを保存する場所を定義することが不可欠です。パスの指定方法は次のとおりです。

```csharp
// Excel ファイルが配置されているディレクトリ パスを定義します。
string dataDir = "Your Directory Path";

// 入力ワークブックへの完全なパスを定義します。
string inputPath = dataDir + "book1.xls";
```

交換する `"Your Directory Path"` ワークブックを含むディレクトリへの実際のパスを指定します。これにより、コードの柔軟性が向上し、パスを効率的に管理できるようになります。

## ステップ2: ワークブックを開いてデータにアクセスする

ファイルパスが設定されたら、次のステップはExcelブックを `Workbook` オブジェクト。これにより、その内容にアクセスして操作できるようになります。

```csharp
// Excel ファイルを Workbook オブジェクトに読み込みます。
Workbook wb = new Workbook(inputPath);
```

この行で、正常にロードされました `book1.xls` に `wb` オブジェクトを作成し、そのデータにアクセスできるようにします。

## ステップ3: ワークシートコレクションにアクセスする

ワークブックが読み込まれると、そこに含まれるシートにアクセスできるようになります。Aspose.Cellsは `Worksheets` コレクション。これにより、ワークブック内の各ワークシートを操作できるようになります。

```csharp
// ワークブックからワークシート コレクションを取得します。
WorksheetCollection sheets = wb.Worksheets;
```

その `sheets` オブジェクトは、その中のすべてのワークシートにアクセスできるようになりました `book1.xls`また、あるシートから別のシートにデータをコピーするなど、さまざまな操作を実行できます。

## ステップ4: あるシートから別のシートにデータをコピーする

同じワークブック内の1つのワークシートから別のワークシートにデータをコピーするには、Aspose.Cellsは、 `AddCopy`このメソッドは、指定されたワークシートの複製を作成し、それをブックに追加します。

```csharp
// 「Sheet1」からワークブック内の新しいシートにデータをコピーします。
sheets.AddCopy("Sheet1");
```

この例では、「Sheet1」から新しいシートにデータをコピーしています。 `AddCopy` この方法は、数式、書式、値など、シートの内容をすべて保持しながらシート全体を複製します。

## ステップ5: 変更したワークブックを保存する

データをコピーした後、変更したワークブックを新しい名前または場所で保存できます。これは、 `Save` 方法 `Workbook` 物体。

```csharp
// 変更したブックを新しい名前で保存します。
wb.Save(dataDir + "book1_copy.xls");
```

これにより、コピーされたシートを含むワークブックが次のように保存されます。 `book1_copy.xls` 指定されたディレクトリに保存されます。ファイル名とパスは必要に応じて変更できます。

## 結論

Aspose.Cells for .NET を使って Excel ブック内のデータをコピーするのは簡単です。このガイドでは、効率的に行うための手順を説明します。シート全体を複製する場合でも、特定のデータ範囲を複製する場合でも、Aspose.Cells は堅牢で柔軟な API を提供し、Excel の自動化をシンプルかつ効果的に実現します。

## よくある質問

### 一度に複数のシートをコピーできますか?

Aspose.Cellsは、1回の呼び出しで複数のシートをコピーすることはできません。ただし、コピーしたいシートをループ処理して個別にコピーすることは可能です。

### コピーしたシートの名前を変更するにはどうすればよいですか?

シートをコピーした後、次のように名前を変更できます。

```csharp
sheets[sheets.Count - 1].Name = "NewSheetName";
```

### Aspose.Cells は .NET Core と互換性がありますか?

はい、Aspose.Cells は .NET Framework と .NET Core の両方の環境と完全に互換性があります。

### Aspose.Cells はコピー中に書式をどのように処理しますか?

その `AddCopy` この方法では、シートをコピーするときにすべてのコンテンツと書式が保持され、コピーされたデータが元のデータと同一であることが保証されます。

### シートを別のブックにコピーできますか?

はい、シートを別のブックにコピーするには、 `Copy` 対象のブックへの参照を持つメソッド。

```csharp
sheets.Add().Copy(wb.Worksheets["Sheet1"]);
```