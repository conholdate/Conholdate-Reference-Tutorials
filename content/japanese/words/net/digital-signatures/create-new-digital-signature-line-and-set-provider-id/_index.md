---
"description": "Aspose.Words for .NET を使用して、Word 文書にプログラムで署名欄を追加する方法を学びましょう。この包括的なガイドでは、開発環境の設定から署名欄の挿入、そして文書への安全な署名まで、あらゆる手順を網羅しています。"
"linktitle": "新しいデジタル署名行を作成し、プロバイダー ID を設定する"
"second_title": "Aspose.Words ドキュメント処理 API"
"title": "新しいデジタル署名行を作成し、プロバイダー ID を設定する"
"url": "/ja/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## 導入

テクノロジーに詳しい皆様、こんにちは！Word文書への署名欄の挿入を自動化したいと思ったことはありませんか？本日は、Aspose.Words for .NET を使って署名欄を追加する方法について詳しくご紹介します。このステップバイステップガイドでは、署名欄の作成とプロバイダーIDの設定方法をご案内し、文書処理タスクの効率化と合理化を実現します。

## 前提条件

始める前に、すべてがセットアップされていることを確認しましょう。

1. Aspose.Words for .NET: まだインストールしていない場合はダウンロードしてください [ここ](https://releases。aspose.com/words/net/).
2. 開発環境: Visual Studio または任意の C# 開発セットアップを使用します。
3. .NET Framework: マシンに .NET Framework がインストールされていることを確認します。
4. PFX 証明書: ドキュメントに署名するには、信頼できる証明機関から取得できる PFX 証明書が必要です。

## 必要な名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートします。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

それでは、新しい署名行を作成し、プロバイダー ID を設定する詳細を見ていきましょう。

## ステップ1：新しいドキュメントを作成する

まず、署名欄のキャンバスとなる新しい Word 文書を作成する必要があります。

```csharp
// ドキュメント ディレクトリへのパスを指定します。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

ここで、新しい `Document` そして `DocumentBuilder`これにより、要素を簡単に追加できるようになります。

## ステップ2: 署名行のオプションを定義する

次に、署名者の名前、役職、電子メール、その他の関連詳細を含む署名行のオプションを定義します。

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

これらのオプションは、署名行をパーソナライズして明確かつプロフェッショナルなものにするのに役立ちます。

## ステップ3: 署名欄を挿入する

オプションの準備ができたら、文書に署名行を挿入できます。

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

その `InsertSignatureLine` メソッドは署名行を追加し、それに一意のプロバイダー ID を割り当てます。

## ステップ4: ドキュメントを保存する

署名行を挿入したら、ドキュメントを保存します。

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

これにより、新しく追加された署名行を含むドキュメントが保存されます。

## ステップ5: 署名オプションを設定する

ここで、署名行 ID、プロバイダー ID、コメント、署名時間などの署名オプションを構成します。

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

これらの設定により、ドキュメントが正しい詳細で署名されることが保証されます。

## ステップ6: 証明書所有者を作成する

ドキュメントに署名するには、PFX 証明書を使用して証明書ホルダーを作成する必要があります。

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

交換する `"morzal.pfx"` 実際の証明書ファイル名と `"aw"` 証明書のパスワードを入力します。

## ステップ7：文書に署名する

最後に、デジタル署名ユーティリティを使用してドキュメントに署名します。

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

このプロセスでは、ドキュメントに署名し、新しいファイルとして保存します。

## 結論

おめでとうございます！Aspose.Words for .NET を使用して、Word 文書に署名欄を作成し、プロバイダー ID を設定することができました。この強力なライブラリは、ドキュメント処理タスクを簡素化し、ワークフローの効率化を実現します。ぜひお試しいただき、プロジェクトの改善にご活用ください。

## よくある質問

### 署名行の外観をカスタマイズできますか?
もちろんです！様々なオプションを調整できます `SignatureLineOptions` あなたのスタイルと要件に合わせて。

### PFX 証明書を持っていない場合はどうなりますか?
証明書はドキュメントのデジタル署名に不可欠なので、信頼できる証明機関から取得する必要があります。

### 文書に複数の署名行を追加できますか?
はい、異なるオプションで挿入プロセスを繰り返すことで、複数の署名行を追加できます。

### Aspose.Words for .NET は .NET Core と互換性がありますか?
はい、Aspose.Words for .NET は .NET Core をサポートしており、さまざまな開発環境に柔軟に対応できます。

### デジタル署名はどの程度安全ですか?
有効で信頼できる証明書を使用している限り、Aspose.Words で作成されたデジタル署名は非常に安全です。