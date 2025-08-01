---
"description": "Aspose.Note for .NET を使用して、Microsoft OneNote ドキュメントを PDF ファイルとして効率的に保存する方法を学びましょう。このガイドでは、必要な前提条件を詳しく説明し、役立つ FAQ も提供しています。"
"linktitle": "OneNote ドキュメントを PDF で保存する"
"second_title": "Aspose.Note .NET API"
"title": "Aspose.Note for .NET を使用して OneNote ドキュメントを PDF 形式で保存する"
"url": "/ja/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## 導入

このチュートリアルでは、Aspose.Note for .NET を使用してドキュメントを PDF 形式で保存する方法を説明します。Aspose.Note は、開発者が Microsoft OneNote ファイルをプログラムで操作できるようにする強力なライブラリです。前提条件、名前空間のインポート、そして様々なページレイアウトでドキュメントを PDF 形式で保存するためのステップバイステップガイドを紹介します。

## 前提条件
1. Visual Studio: インストールされていることを確認します。
2. Aspose.Note for .NET: ライブラリをダウンロードしてインストールします。
3. C# の知識: 言語の基本的な理解が必要です。

## 必要な名前空間のインポート
続行する前に、コードに次の名前空間をインポートします。

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## ステップ1：レターページ設定でPDFに保存する
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // このパスを更新
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
OneNote ドキュメントを読み込み、レター サイズのページ設定を使用して PDF として保存します。

## ステップ2: A4ページ設定でPDFに保存（高さ制限なし）
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // このパスを更新
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
ステップ 1 と似ていますが、高さの制限のない A4 ページ設定を使用します。

## 結論
このチュートリアルでは、Aspose.Note を使用して OneNote ファイルを PDF 形式に変換する方法を説明します。さまざまなページ設定を活用することで、開発者はドキュメント管理の柔軟性を高めることができます。

## よくある質問
### Aspose.Note は複雑な OneNote ファイルを処理できますか?
はい、複雑な OneNote ファイルのさまざまな機能を効果的に処理します。

### Aspose.Note は商用プロジェクトに適していますか?
はい、ライセンスを購入すれば商用アプリケーションに使用できます。

### Aspose.Note には無料トライアルがありますか?
はい、無料でお試しいただけます。

### Aspose.Note のドキュメントはどこにありますか?
詳細なドキュメントは Aspose リファレンス サイトで入手できます。

### さらにサポートが必要ですか?
質問やサポートについては、Aspose.Note フォーラムを参照してください。