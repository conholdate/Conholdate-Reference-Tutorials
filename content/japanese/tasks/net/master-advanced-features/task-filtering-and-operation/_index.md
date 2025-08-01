---
"description": "Aspose.Tasks for .NET のクラスを活用して、複数の条件に基づいてプロジェクトタスクをフィルタリングする方法を学びます。サマリータスクや非 null 属性などの条件を組み合わせることで、フィルタリングが可能になります。"
"linktitle": "Aspose.Tasks でのタスクフィルタリング AND 操作"
"second_title": "Aspose.Tasks .NET API"
"title": "Aspose.Tasks でのタスクフィルタリング AND 操作"
"url": "/ja/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## 導入

このチュートリアルでは、Aspose.Tasks for .NETでプロジェクトタスクの高度なフィルタリングを実行する方法を説明します。 `Util.And` クラス。この強力な機能により、開発者は複数の基準に基づいてタスクを効率的にフィルタリングできます。

## 前提条件

始める前に、以下のものを用意してください。

1. C# プログラミングの基礎知識。
2. Aspose.Tasks for .NET がインストールされている必要があります。まだインストールされていない場合は、こちらからダウンロードできます。 [このリンク](https://releases。aspose.com/tasks/net/).
3. コードを記述して実行するための Visual Studio などの統合開発環境 (IDE)。

## 名前空間のインポート

まず、必要な名前空間をC#プロジェクトにインポートする必要があります。これにより、Aspose.Tasksが提供する機能にアクセスできるようになります。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## ステップ1: プロジェクトを初期化し、タスクを収集する

まず、Aspose.Tasksプロジェクトを初期化し、その中のすべてのタスクを収集します。デモのために、プロジェクトファイルの名前が `Project2。mpp`.

```csharp
// ドキュメントディレクトリへのパス
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// すべての子タスクを収集する
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## ステップ2: フィルター条件を定義する

このステップでは、タスクをフィルタリングするための条件を定義します。この例では、サマリータスクをフィルタリングするための条件と、タスクがnullでないことを確認するための条件の2つを作成します。

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## ステップ3: AND演算で条件を組み合わせる

次のステップは、これらの条件を `Util.And` クラス。これにより、両方の基準を必須とする複合条件を作成できます。

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## ステップ4: 複合条件とフィルタータスクを適用する

ここで、収集されたタスクに結合条件を適用して、両方の条件を満たす特定のタスクをフィルター処理してみましょう。

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## ステップ5: フィルタリングされたタスクを出力する

最後に、フィルタリングされたタスクを反復処理し、関連する詳細情報を出力します。これにより、基準を満たすタスクを把握しやすくなります。

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NETで高度なフィルタリング操作を実行する方法を説明しました。 `Util.And` クラス。複数の条件を組み合わせることで、タスクを効果的にフィルタリングし、プロジェクト管理アプリケーションの有用性を高めることができます。

## よくある質問

### Aspose.Tasks for .NET とは何ですか?

Aspose.Tasks for .NET は、開発者が .NET アプリケーション内でプログラムによって Microsoft Project ファイルを操作できるように設計された包括的な API です。

### Util.And を使用して 2 つ以上の条件を組み合わせることはできますか?

はい！ `Util.And` クラスを使用すると、複数の条件を組み合わせて、ニーズに合わせた複雑なフィルタリング ロジックを作成できます。

### Aspose.Tasks の無料試用版はありますか?

はい、無料試用版は以下からダウンロードできます。 [このリンク](https://releases。aspose.com/).

### Aspose.Tasks の詳細なドキュメントはどこで入手できますか?

詳細なドキュメントが利用可能です [ここ](https://reference。aspose.com/tasks/net/).

### Aspose.Tasks のサポートを受けるにはどうすればよいですか?

サポートはAspose.Tasksコミュニティフォーラムを通じて受けられます。 [ここ](https://forum。aspose.com/c/tasks/15).