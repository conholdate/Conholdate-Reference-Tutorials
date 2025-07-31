---
"description": "ボックスや円柱などの基本的な 3D モデルを簡単に作成およびカスタマイズし、FBX 形式で保存する方法を学びます。"
"linktitle": "プリミティブ3Dモデリングを作成する"
"second_title": "Aspose.3D .NET API"
"title": "プリミティブ3Dモデリングを作成する"
"url": "/ja/3d/net/guide-to-3d-modeling/create-primitive-3d-modeling/"
"weight": 10
---

## 導入

Aspose.3D for .NET を使った没入型の 3D モデリングの世界へようこそ！この包括的なチュートリアルでは、プリミティブな 3D モデルの作成プロセスをステップごとに解説します。経験豊富な開発者の方でも、学習意欲の高い初心者の方でも、このガイドを活用すれば、プロジェクトで魅力的な 3D 要素を作成できるようになります。

## 前提条件

3D モデリングを始める前に、次の前提条件が満たされていることを確認してください。

- Aspose.3D for .NET: Aspose.3D for .NETライブラリを以下のサイトからダウンロードしてインストールします。 [ダウンロードページ](https://releases。aspose.com/3d/net/).
  
- .NET 開発環境: Visual Studio など、Aspose.3D と互換性のある環境をセットアップします。

準備が整ったら、3D モデリングの冒険に出かけましょう。

## 必要な名前空間のインポート

まず、Aspose.3D の機能にアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using System.IO;
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
```

これらの名前空間は、3D モデルを操作し、作成したモデルを保存するために必要なツールを提供します。

## ステップ1: シーンオブジェクトの初期化

3D モデルのキャンバスとして機能する新しいシーン オブジェクトを作成します。

```csharp
// シーンオブジェクトを初期化する
Scene scene = new Scene();
```

このシーンには、これから作成するプリミティブ シェイプが含まれます。

## ステップ2: ボックスモデルを作成する

次に、シーンにボックス モデルを追加してみましょう。

```csharp
// ボックスモデルを作成する
scene.RootNode.CreateChildNode("box", new Box());
```

クリエイティブなビジョンに合わせて、ボックスの寸法とプロパティをカスタマイズできます。

## ステップ3：円柱モデルを作成する

次に、円柱を追加してシーンを強化します。

```csharp
// 円柱モデルを作成する
scene.RootNode.CreateChildNode("cylinder", new Cylinder());
```

ボックスの場合と同様に、シリンダーのパラメータを自由に調整して、希望の外観を実現できます。

## ステップ4: シーンをFBX形式で保存する

3D モデルを保存するには、FBX 形式で保存します。

```csharp
// FBX形式で図面を保存する
var output = Path.Combine("Your Output Directory", "test.fbx");
scene.Save(output, FileFormat.FBX7500ASCII);
```

モデルに適切な出力ディレクトリとファイル名を選択してください。

## ステップ5: 成功メッセージを表示する

最後に、次のメッセージを表示して成功を祝います。

```csharp
// 成功メッセージを表示する
Console.WriteLine($"\nBuilding a scene from primitive 3D models was successful.\nFile saved at {output}");
```

プリミティブ モデルで構成された 3D シーンが完成し、保存されました。

## 結論

Aspose.3D for .NET を使って素晴らしい 3D モデルを作成できたことを嬉しく思います。このチュートリアルではプリミティブモデリングの基本を解説しましたが、その可能性は無限大です。より高度な機能やテクニックについては、次のチュートリアルをご覧ください。 [ドキュメント](https://reference。aspose.com/3d/net/).

## よくある質問

### Aspose.3D for .NET を .NET 以外のプログラミング言語で使用できますか?

Aspose.3D は主に .NET をサポートしていますが、Java や他のプラットフォーム用のバージョンも用意されています。

### 無料トライアルはありますか？

はい、Aspose.3Dの機能を試すことができます。 [無料トライアル](https://releases。aspose.com/).

### Aspose.3D for .NET のサポートはどこで受けられますか?

コミュニティサポートについては、 [Aspose.3D フォーラム](https://forum。aspose.com/c/3d/18).

### 一時ライセンスを取得するにはどうすればいいですか?

一時ライセンスを申請できます [ここ](https://purchase。conholdate.com/temporary-license/).

### 追加のチュートリアルはありますか?

はい！その他のチュートリアルと例については、 [ドキュメント](https://reference。aspose.com/3d/net/).