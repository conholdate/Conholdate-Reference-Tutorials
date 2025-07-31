---
"description": "了解如何创建和自定义原始 3D 模型（包括盒子和圆柱体），并轻松地将它们保存为 FBX 格式。"
"linktitle": "创建原始 3D 建模"
"second_title": "Aspose.3D .NET API"
"title": "创建原始 3D 建模"
"url": "/zh/3d/net/guide-to-3d-modeling/create-primitive-3d-modeling/"
"weight": 10
---

## 介绍

欢迎来到使用 Aspose.3D for .NET 的沉浸式 3D 建模世界！在本教程中，我们将逐步指导您完成创建原始 3D 模型的过程。无论您是经验丰富的开发人员，还是渴望学习的初学者，本指南都能帮助您为项目创建视觉震撼的 3D 元素。

## 先决条件

在深入 3D 建模之前，请确保您已满足以下先决条件：

- Aspose.3D for .NET：从下载并安装 Aspose.3D for .NET 库 [下载页面](https://releases。aspose.com/3d/net/).
  
- .NET开发环境：搭建与Aspose.3D兼容的环境，例如Visual Studio。

一切准备就绪后，让我们开始我们的 3D 建模冒险吧！

## 导入所需的命名空间

首先导入必要的命名空间以访问 Aspose.3D 功能：

```csharp
using System;
using System.IO;
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
```

这些命名空间将为您提供操作 3D 模型和保存您的创作所需的工具。

## 步骤1：初始化场景对象

创建一个新的场景对象作为 3D 模型的画布：

```csharp
// 初始化场景对象
Scene scene = new Scene();
```

该场景将包含您即将创建的原始形状。

## 步骤2：创建盒子模型

接下来，让我们向场景中添加一个盒子模型：

```csharp
// 创建一个 Box 模型
scene.RootNode.CreateChildNode("box", new Box());
```

您可以自定义盒子的尺寸和属性以适合您的创意。

## 步骤3：创建圆柱模型

现在，通过添加圆柱体来增强场景：

```csharp
// 创建圆柱体模型
scene.RootNode.CreateChildNode("cylinder", new Cylinder());
```

就像盒子一样，随意调整圆柱体的参数以实现您想要的外观。

## 步骤 4：以 FBX 格式保存场景

要保留您的 3D 模型，请将其保存为 FBX 格式：

```csharp
// 以 FBX 格式保存绘图
var output = Path.Combine("Your Output Directory", "test.fbx");
scene.Save(output, FileFormat.FBX7500ASCII);
```

确保为您的模型选择合适的输出目录和文件名。

## 步骤 5：显示成功消息

最后，通过显示一条消息来庆祝您的成功：

```csharp
// 显示成功消息
Console.WriteLine($"\nBuilding a scene from primitive 3D models was successful.\nFile saved at {output}");
```

由原始模型组成的 3D 场景现已完成并保存！

## 结论

恭喜您使用 Aspose.3D for .NET 创建了令人惊叹的 3D 模型！本教程涵盖了原始建模的基础知识，但其可能性无穷无尽。探索更多关于高级功能和技术的 [文档](https://reference。aspose.com/3d/net/).

## 常见问题解答

### 我可以将 Aspose.3D for .NET 与 .NET 以外的编程语言一起使用吗？

Aspose.3D 主要支持 .NET，但也有适用于 Java 和其他平台的版本。

### 可以免费试用吗？

是的，你可以尝试 Aspose.3D 的功能 [免费试用](https://releases。aspose.com/).

### 在哪里可以找到对 Aspose.3D for .NET 的支持？

如需社区支持，请访问 [Aspose.3D 论坛](https://forum。aspose.com/c/3d/18).

### 我如何获得临时执照？

您可以申请临时驾照 [这里](https://purchase。conholdate.com/temporary-license/).

### 还有其他教程吗？

是的！探索更多教程和示例 [文档](https://reference。aspose.com/3d/net/).