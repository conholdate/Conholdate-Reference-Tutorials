---
"description": "このステップバイステップのチュートリアルでは、Aspose.Email for .NET を使用して MHTML でカスタム情報の順序を定義する方法を学習します。"
"linktitle": "Aspose.Email を使用した MHTML の情報の順序のカスタマイズ"
"second_title": "Aspose.Email .NET メール処理 API"
"title": "Aspose.Email を使用した MHTML の情報の順序のカスタマイズ"
"url": "/ja/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## 導入

リッチなメールフォーマットを作成することで、特にMHTMLなどの異なるファイル形式にメールをエクスポートする場合、コミュニケーションが大幅に向上します。Aspose.Email for .NETは、メールを操作するための強力なツールキットを開発者に提供します。これには、MHTMLへのエクスポート時に情報の表示順序をカスタム定義することも含まれます。このガイドでは、これを実現するために必要な手順を詳しく説明します。経験豊富な開発者の方でも、初心者の方でも、簡単に理解できます。それでは、早速始めましょう！

## 前提条件

MHTML で情報のカスタム順序を定義する前に、いくつかの前提条件を確認する必要があります。

1. .NET開発環境：.NET開発環境がセットアップされていることを確認してください。Visual Studio、Visual Studio Code、またはその他の互換性のあるIDEを使用できます。

2. Aspose.Emailライブラリ：Aspose.Email for .NETライブラリがインストールされている必要があります。最新バージョンは以下からダウンロードできます。 [Aspose リリースページ](https://releases。aspose.com/email/net/).

3. C# の基本的な理解: C# プログラミングに精通していると、コードをより深く理解できるようになります。

4. サンプルメールファイル: サンプルが必要です `.eml` ファイル（例： `Attachments.eml`) をテスト目的で使用します。

これらの前提条件が満たされたら、チュートリアルを進める準備は完了です。

## パッケージのインポート

コードを開始するには、Aspose.Email ライブラリから必要な名前空間をインポートする必要があります。これは、メールファイルの操作に必要なすべてのクラスとメソッドにアクセスするために不可欠です。

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

これらをC#ファイルの先頭に記述してください。これでコーディングを始める準備が整いました！

すべての設定が完了したので、チュートリアルを管理しやすいステップに分解してみましょう。

## ステップ1: データディレクトリを設定する

まず最初に、メールファイルを保存するディレクトリを作成します。これはローカルマシン上の任意のパスで構いません。

```csharp
string dataDir = "Your Data Directory";
```

交換する `"Your Data Directory"` 実際のパスで `.eml` ファイルが配置されている場所。例えば、ファイルが `C:\Emails`次のように記述します。

```csharp
string dataDir = @"C:\Emails\";
```

## ステップ2: 電子メールメッセージを読み込む

次に、 `.eml` ファイルに `MailMessage` オブジェクト。これにより、メールの内容とメタデータを操作できます。

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

ファイル名が指定ディレクトリにあるファイル名と一致していることを確認してください。ファイル名が異なる場合は、それに応じてファイル名を更新してください。

## ステップ3: MHTML保存オプションを設定する

メールを読み込んだら、MHTML として保存する方法を指定します。デフォルトのオプションから始めても構いません。

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

この行は、MHTML 保存オプションを初期化し、後でヘッダーをカスタマイズするための準備を行います。

## ステップ4: デフォルトの順序でMHTMLを保存する

デフォルトの順序でメールをMHTML形式で保存してみましょう。これにより、カスタマイズ後と比較するための基準が得られます。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

この行を実行し、指定したディレクトリを確認してください。新しいMHTMLファイルが作成され、 `CustomOrderOfInformationInMHTML_1.mhtml`これを開くと、デフォルトで情報がどのように表示されるかを確認できます。

## ステップ5: ヘッダーの順序をカスタマイズする

いよいよ楽しい部分です！MHTML出力に含めるヘッダーとその順序を指定できます。まずは、一般的なヘッダーをいくつかご紹介します。

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

これらのヘッダーを追加することで、電子メールをどのように表示するかを Aspose に指示することになります。

## ステップ6: カスタム順序でMHTMLを保存する

ヘッダーをカスタマイズした後、新しい順序が出力にどのように影響するかを確認するために、電子メールを再度 MHTML として保存する必要があります。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

このコードを実行してから `CustomOrderOfInformationInMHTML_2.mhtml`最初のものと比較して、ヘッダーの順序に基づいて情報がどのように変化したかを確認します。

## ステップ7: ヘッダーの順序をクリアして追加する

まったく異なる順序にしたい場合はどうすればよいでしょうか? 既存のヘッダー設定をクリアすることで、最初からやり直すことができます。

```csharp
opt.RenderingHeaders.Clear();
```

次に、ヘッダーの新しい順序を定義します。例えば、添付ファイルを優先し、受信者にコピーしたい場合は、次のようにします。

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## ステップ8: 新しいカスタムオーダーでMHTMLを保存する

最後に、新しいヘッダー設定で電子メールをもう一度保存します。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

この行を実行した後、 `CustomOrderOfInformationInMHTML_3.mhtml` 新しいカスタマイズに基づいて情報がどのように表示されるかを確認します。

## 結論

以上が、Aspose.Email for .NET を使用して MHTML で情報の順序をカスタマイズするための分かりやすいガイドです。これらの手順に従うことで、MHTML 形式でのメールの表示方法を制御し、最も重要な情報をニーズに合わせて表示できるようになります。 

## よくある質問

### MHTML とは何ですか?
MHTML は「MIME HTML」の略で、HTML と画像などの他のリソースを組み合わせた Web ページ アーカイブ形式です。

### Aspose.Email を無料で使用できますか?
はい、Asposeは開発者向けに無料トライアル版を提供しています。こちらからお試しいただけます。 [ここ](https://releases。aspose.com/).

### Aspose.Email の使用中に問題が発生した場合はどうすればよいですか?
コミュニティからのサポートは、 [Asposeフォーラム](https://forum。aspose.com/c/email/12/).

### Aspose.Email には一時ライセンスがありますか?
はい、一時ライセンスを申請できます [ここ](https://purchase。aspose.com/temporary-license/).

### Aspose.Email はどこで購入できますか?
ライブラリはこちらから購入できます [リンク](https://purchase。aspose.com/buy).