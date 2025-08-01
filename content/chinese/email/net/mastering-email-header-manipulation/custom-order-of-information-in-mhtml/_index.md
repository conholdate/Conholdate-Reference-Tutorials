---
"description": "在本分步教程中了解如何使用 Aspose.Email for .NET 在 MHTML 中定义自定义信息顺序。"
"linktitle": "使用 Aspose.Email 在 MHTML 中自定义信息顺序"
"second_title": "Aspose.Email .NET 电子邮件处理 API"
"title": "使用 Aspose.Email 在 MHTML 中自定义信息顺序"
"url": "/zh/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## 介绍

创建丰富的电子邮件格式可以极大地增强沟通体验，尤其是在将电子邮件导出为 MHTML 等不同文件格式时。Aspose.Email for .NET 为开发人员提供了强大的电子邮件处理工具包，其中包括自定义导出为 MHTML 时信息的显示顺序。在本指南中，我们将分解实现此目的所需的步骤，无论您是经验丰富的开发人员还是刚刚入门，都能轻松上手。那么，让我们开始吧！

## 先决条件

在深入定义 MHTML 中的自定义信息顺序之前，您需要检查列表中的一些先决条件：

1. .NET 开发环境：确保您已设置好 .NET 开发环境。您可以使用 Visual Studio、Visual Studio Code 或任何其他兼容的 IDE。

2. Aspose.Email 库：您需要安装 Aspose.Email for .NET 库。您可以从 [Aspose 发布页面](https://releases。aspose.com/email/net/).

3. 对 C# 的基本了解：熟悉 C# 编程将帮助您更好地理解代码。

4. 示例电子邮件文件：您需要一个示例 `.eml` 文件（例如， `Attachments.eml`）用于测试目的。

一旦满足了这些先决条件，您就可以继续学习本教程了！

## 导入包

要开始编写代码，您需要从 Aspose.Email 库导入必要的命名空间。这对于访问操作电子邮件文件所需的所有类和方法至关重要。

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

将这些代码添加到你的 C# 文件顶部。现在你就可以开始编写代码了！

现在您已完成所有设置，让我们将教程分解为易于管理的步骤。

## 步骤 1：设置数据目录

首先要做的是创建一个用于存储电子邮件文件的目录。该目录可以是本地计算机上的任何路径。

```csharp
string dataDir = "Your Data Directory";
```

代替 `"Your Data Directory"` 实际路径 `.eml` 文件所在位置。例如，如果您的文件位于 `C:\Emails`，你会写：

```csharp
string dataDir = @"C:\Emails\";
```

## 第 2 步：加载电子邮件消息

接下来，您需要加载 `.eml` 文件放入 `MailMessage` 对象。这允许您操作电子邮件的内容和元数据。

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

确保文件名与指定目录中的文件名匹配。如果文件名不同，请相应地更新文件名。

## 步骤 3：设置 MHTML 保存选项

电子邮件加载完成后，接下来需要定义如何将其保存为 MHTML。您可以从默认选项开始。

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

此行初始化 MHTML 保存选项，为稍后自定义标题做好准备。

## 步骤 4：使用默认顺序保存 MHTML

让我们使用默认顺序将电子邮件保存为 MHTML。这样，您就可以在自定义后进行比较。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

运行此行，并检查指定的目录。现在您应该会看到一个名为“MHTML”的新文件 `CustomOrderOfInformationInMHTML_1.mhtml`。打开看看信息默认是如何显示的。

## 步骤 5：自定义标题顺序

现在到了最有趣的部分！您可以指定在 MHTML 输出中包含哪些标题以及包含的顺序。我们先从一些常见的标题开始。

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

通过添加这些标题，您可以告诉 Aspose 您希望如何显示电子邮件。

## 步骤 6：按自定义顺序保存 MHTML

自定义标题后，您需要将电子邮件再次保存为 MHTML，以查看新顺序如何影响输出。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

运行此代码，然后打开 `CustomOrderOfInformationInMHTML_2.mhtml`。将其与第一个进行比较，看看信息如何根据标题顺序发生变化。

## 步骤 7：清除并添加新的标题顺序

如果您想要完全不同的订单怎么办？您可以清除现有的标题设置，重新开始。

```csharp
opt.RenderingHeaders.Clear();
```

现在是时候为标题定义新的顺序了。例如，如果您要按优先级排列附件和抄送收件人：

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## 步骤 8：使用新的自定义顺序保存 MHTML

最后，使用新的标题设置最后一次保存电子邮件。

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

运行此行后，打开 `CustomOrderOfInformationInMHTML_3.mhtml` 并检查它如何根据您的新定制呈现信息。

## 结论

以上就是使用 Aspose.Email for .NET 在 MHTML 中自定义信息顺序的简单指南。按照以下步骤，您可以控制电子邮件在 MHTML 格式中的呈现方式，确保以符合您需求的方式呈现最重要的信息。 

## 常见问题解答

### 什么是 MHTML？
MHTML 代表“MIME HTML”，这是一种结合了 HTML 和图像等其他资源的网页存档格式。

### 我可以免费使用 Aspose.Email 吗？
是的，Aspose 提供免费试用版供开发者探索。您可以找到 [这里](https://releases。aspose.com/).

### 如果使用 Aspose.Email 时遇到问题怎么办？
您可以通过以下方式获得社区支持 [Aspose 论坛](https://forum。aspose.com/c/email/12/).

### Aspose.Email 有临时许可证吗？
是的，你可以申请临时驾照 [这里](https://purchase。aspose.com/temporary-license/).

### 在哪里可以购买 Aspose.Email？
您可以在此处购买图书馆 [关联](https://purchase。aspose.com/buy).