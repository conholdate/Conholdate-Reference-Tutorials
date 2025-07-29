---
"description": "Aspose.Words for .NET を使用して、Word 文書内のコンテンツの表示/非表示を巧みに制御する方法をステップバイステップで解説します。"
"linktitle": "Word文書のブックマークの表示を管理する"
"second_title": "Aspose.Words ドキュメント処理 API"
"title": "Word文書のブックマークの表示を管理する"
"url": "/ja/words/net/mastering-bookmarks/manage-bookmark-visibility-word-document/"
"weight": 10
---

## 導入

Aspose.Words for .NET を使って、ドキュメント操作スキルを磨きませんか？ ドキュメント作成タスクの自動化に取り組んでいるベテラン開発者の方にも、Word ファイルのプログラム制御に興味をお持ちの方にも、このガイドはきっとお役に立ちます。本日は、Word 文書内のブックマークに基づいてコンテンツを表示または非表示にする方法について詳しく解説します。さあ、始めましょう！

## 前提条件

始める前に、次のものを用意してください。

1. Visual Studio: .NET と互換性のある任意のバージョン。
2. Aspose.Words for .NET: ダウンロード [ここ](https://releases。aspose.com/words/net/).
3. 基本的な C# の知識: 簡単な C# プログラムの作成に関する知識があれば十分です。
4. サンプル Word 文書: このチュートリアル用のブックマークを含む Word 文書 (例: 「Bookmarks.docx」) を準備します。

### 新しいプロジェクトを作成する

1. Visual Studioを開き、新しいコンソールアプリ（.NET Core）プロジェクトを作成します。「BookmarkVisibilityManager」のような名前を付けます。

### Aspose.Words for .NET をインストールする

NuGet パッケージ マネージャーを使用して Aspose.Words をプロジェクトに追加します。

1. [ツール] > [NuGet パッケージ マネージャー] > [ソリューションの NuGet パッケージの管理] に移動します。
2. 「Aspose.Words」を検索します。
3. パッケージをインストールします。

プロジェクトの設定が完了したら、ドキュメントの読み込みに進みます。

## 名前空間のインポート

まず、必須の名前空間をインポートします。これらは、Aspose.Words で Word 文書を操作するために必要なクラスとメソッドを提供します。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

## ステップ1: ドキュメントの読み込み

Word文書を操作するには、まず文書を読み込む必要があります。手順は以下のとおりです。

```csharp
// ドキュメント ディレクトリへのパスを定義します。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

このスニペットはドキュメントディレクトリへのパスを設定し、ドキュメントを `Document` 物体。

## ステップ2: ブックマークしたコンテンツを表示/非表示にする

さて、ブックマークに基づいてコンテンツの表示/非表示を切り替えるメソッドを作成しましょう。このメソッドを次のように呼びます。 `ShowHideBookmarkedContent`。

メソッドの実装は次のとおりです。

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    if (bm != null)
    {
        Node currentNode = bm.BookmarkStart;
        while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
        {
            if (currentNode.NodeType == NodeType.Run)
            {
                Run run = (Run)currentNode;
                run.Font.Hidden = isHidden;
            }
            currentNode = currentNode.NextSibling;
        }
    }
}
```

- ブックマークの取得: `Bookmark bm = doc.Range.Bookmarks[bookmarkName];` 指定されたブックマークを取得します。
- ノードトラバーサル: ブックマーク内のノードを反復処理します。
- 表示切り替え: それぞれ `Run` ノード（テキストのセグメントを表す）では、 `Hidden` に基づくプロパティ `isHidden` パラメータ。

## ステップ3：方法の適用

メソッドの準備ができたので、これを使用して特定のブックマーク内のコンテンツを表示または非表示にしてみましょう。

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true); // 「MyBookmark1」内のコンテンツを非表示にします
```

この行は、「MyBookmark1」という名前のブックマークに関連付けられたコンテンツを非表示にします。

## ステップ4: ドキュメントを保存する

変更を加えたら、変更したドキュメントを忘れずに保存してください。

```csharp
doc.Save(dataDir + "UpdatedBookmarks.docx");
```

これにより、更新された表示設定でドキュメントが保存されます。

## 結論

おめでとうございます！Aspose.Words for .NET を使って、Word 文書内のブックマークされたコンテンツを表示/非表示にする方法を習得しました。この強力なライブラリはドキュメント操作を簡素化し、レポートの自動化、テンプレートの作成、Word ファイルを使った実験などに最適です。コーディングを楽しみましょう！

## よくある質問

### 複数のブックマークを一度に切り替えることはできますか?
はい、電話してください `ShowHideBookmarkedContent` 切り替えるブックマークごとにメソッドを使用します。

### コンテンツを非表示にすると、ドキュメントの構造に影響しますか?
いいえ、コンテンツを非表示にすると、そのコンテンツの可視性のみに影響し、ドキュメント内のコンテンツはそのまま残ります。

### この方法は他の種類のコンテンツにも使用できますか?
このメソッドはテキストラン専用に設計されています。他のコンテンツタイプでは、ノードトラバーサルロジックを適宜調整する必要があります。

### Aspose.Words for .NET は無料ですか?
Aspose.Wordsは無料トライアルを提供しています [ここ](https://releases.aspose.com/)ただし、本番環境での使用にはフルライセンスが必要です。ご購入いただけます。 [ここ](https://purchase。aspose.com/buy).

### 問題が発生した場合、どうすればサポートを受けることができますか?
サポートについては、Aspose コミュニティフォーラムをご覧ください。 [ここ](https://forum。aspose.com/c/words/8).