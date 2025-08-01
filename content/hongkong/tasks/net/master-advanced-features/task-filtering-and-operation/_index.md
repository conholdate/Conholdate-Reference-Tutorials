---
"description": "了解如何利用 Aspose.Tasks for .NET 中的類別根據多種條件過濾專案任務。透過結合摘要任務和非空屬性等標準。"
"linktitle": "Aspose.Tasks 中的任務過濾與操作"
"second_title": "Aspose.Tasks .NET API"
"title": "Aspose.Tasks 中的任務過濾與操作"
"url": "/zh-hant/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## 介紹

在本教程中，我們將探索如何在 Aspose.Tasks for .NET 中利用 `Util.And` 班級。這項強大的功能可讓開發人員根據多種標準有效地過濾任務。

## 先決條件

在開始之前，請確保您具備以下條件：

1. C# 程式設計的基本知識。
2. 已安裝 Aspose.Tasks for .NET。如果你還沒有這樣做，你可以從 [此連結](https://releases。aspose.com/tasks/net/).
3. 像 Visual Studio 這樣的整合開發環境 (IDE) 用於編寫和運行程式碼。

## 導入命名空間

首先，您需要將所需的命名空間匯入到您的 C# 專案中。這將允許您存取 Aspose.Tasks 提供的功能。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## 步驟1：初始化項目並收集任務

首先，初始化一個 Aspose.Tasks 專案並收集其中的所有任務。為了演示目的，我們假設有一個名為 `Project2。mpp`.

```csharp
// 文檔目錄的路徑
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// 收集所有子任務
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## 步驟2：定義篩選條件

在此步驟中，我們將定義過濾任務的條件。在我們的範例中，我們將建立兩個條件：一個用於過濾摘要任務，另一個用於確保任務不為空。

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## 步驟 3：使用 AND 運算組合條件

下一步是利用 `Util.And` 班級。這使我們能夠創建一個同時滿足這兩個標準的複合條件。

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## 步驟 4：應用組合條件和過濾任務

現在，讓我們將組合條件應用到收集到的任務上，以篩選出同時滿足兩個條件的特定任務。

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## 步驟5：輸出過濾後的任務

最後，我們將遍歷過濾後的任務並輸出相關詳細資訊。這將幫助我們了解符合我們標準的任務。

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## 結論

在本教程中，我們示範如何使用 `Util.And` 班級。透過組合多個條件，我們可以有效地過濾任務，從而增強我們的專案管理應用程式的實用性。

## 常見問題解答

### Aspose.Tasks for .NET 是什麼？

Aspose.Tasks for .NET 是一個全面的 API，專為開發人員在 .NET 應用程式中以程式設計方式操作 Microsoft Project 檔案而設計。

### 我可以使用 Util.And 組合兩個以上的條件嗎？

是的！這 `Util.And` 類別允許您組合多個條件，從而實現根據您的需求自訂的複雜過濾邏輯。

### Aspose.Tasks 有免費試用版嗎？

是的，您可以從下載免費試用版 [此連結](https://releases。aspose.com/).

### 在哪裡可以找到 Aspose.Tasks 的詳細文件？

提供詳細文檔 [這裡](https://reference。aspose.com/tasks/net/).

### 我如何尋求對 Aspose.Tasks 的支援？

可以透過 Aspose.Tasks 社區論壇獲得支持，可以訪問 [這裡](https://forum。aspose.com/c/tasks/15).