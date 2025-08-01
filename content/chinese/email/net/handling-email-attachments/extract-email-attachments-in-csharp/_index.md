---
"description": "学习如何使用 Aspose.Email for .NET 在 C# 中提取电子邮件附件。分步指南，包含 PDF、图像等示例。"
"linktitle": "使用 C# 提取电子邮件附件 - Aspose.Email 教程"
"second_title": "Aspose.Email .NET 电子邮件处理 API"
"title": "使用 C# 提取电子邮件附件 - Aspose.Email 教程"
"url": "/zh/email/net/handling-email-attachments/extract-email-attachments-in-csharp/"
"weight": 14
---

## 介绍

您是否曾经手动逐个下载电子邮件附件？这不仅耗时，而且容易出错。幸运的是，Aspose.Email for .NET 提供了一种强大而高效的自动化方法。无论您处理的是 PDF、图像还是任何其他文件类型，您都可以使用 C# 轻松提取附件。

在本指南中，我们将带您完成一个完整的教程，从先决条件到完整的示例。准备好节省数小时的手动工作了吗？让我们开始吧！

## 先决条件

在开始编码之前，请确保您已具备以下条件：

- 您的机器上安装了 Visual Studio。
- Aspose.Email for .NET 库。您可以 [点击此处下载](https://releases.aspose.com/email/net/) 或通过 NuGet 安装。
- 有效的电子邮件帐户（支持 IMAP/POP3）。
- 对 C# 编程有基本的了解。

如果您是 Aspose.Email 新手，请考虑申请 [免费试用](https://releases.aspose.com/) 或 [临时执照](https://purchase.aspose.com/temporary-license/) 解锁全部功能。

## 导入包

在深入代码之前，请确保已导入必要的命名空间。在 C# 文件的顶部添加以下内容：

```csharp
using Aspose.Email;
using Aspose.Email.Clients.Imap;
using Aspose.Email.Clients.Pop3;
```

让我们将整个流程分解成易于理解的步骤。仔细遵循每个步骤，确保顺利执行。


## 步骤1：设置您的IMAP客户端

第一步是使用 IMAP 协议连接到您的电子邮件服务器。IMAP 允许我们从服务器访问和检索电子邮件。

```csharp
ImapClient client = new ImapClient("imap.example.com", "username", "password");
client.SelectFolder(ImapFolderInfo.InBox);
```

- 代替 `imap.example.com` 使用您的电子邮件提供商的 IMAP 服务器地址（例如， `imap.gmail.com` （适用于 Gmail）。
- 使用您的实际电子邮件 `username` 和 `password`。
- `SelectFolder(ImapFolderInfo.InBox)` 指定我们要使用收件箱。


## 第 2 步：从收件箱中检索电子邮件

连接后，您需要从收件箱中获取电子邮件。Aspose.Email 提供了一种简单的方法来列出所有邮件。

```csharp
ImapMessageInfoCollection messages = client.ListMessages();
```

- `ListMessages()` 检索收件箱中所有电子邮件的元数据。
- 这 `ImapMessageInfoCollection` 对象包含发件人、主题和唯一 ID 等详细信息。


## 步骤 3：获取每封电子邮件

要访问内容和附件，您需要使用其唯一 ID 获取每封电子邮件。


```csharp
foreach (ImapMessageInfo messageInfo in messages)
{
    MailMessage message = client.FetchMessage(messageInfo.UniqueId);
}
```

- 这 `foreach` 循环遍历所有消息。
- `FetchMessage()` 检索给定消息 ID 的实际电子邮件内容。


## 步骤 4：循环遍历附件

现在您已经有了电子邮件内容，是时候提取附件了。每个 `MailMessage` 对象包含附件集合。

```csharp
foreach (Attachment attachment in message.Attachments)
{
    Console.WriteLine($"Attachment Name: {attachment.Name}");
}
```

- 这 `Attachments` 属性列出了电子邮件中的所有附件。
- 使用 `attachment.Name` 获取文件名。


## 步骤 5：将附件保存到磁盘

最后，将附件保存到本地计算机。您可以按类型、大小或其他条件筛选文件。

```csharp
foreach (Attachment attachment in message.Attachments)
{
    string filePath = Path.Combine("C:\\Attachments", attachment.Name);
    using (var stream = new FileStream(filePath, FileMode.Create))
    {
        attachment.Save(stream);
    }
}
```

- 代替 `"C:\\Attachments"` 使用您想要的文件夹路径。
- 这 `attachment.Save()` 方法将文件写入磁盘。


## 步骤 6：按类型处理附件

如果您需要根据附件类型（例如 PDF 与 JPEG）以不同方式处理附件，Aspose.Email 可以轻松实现。

```csharp
if (attachment.ContentType.MediaType == "application/pdf")
{
    Console.WriteLine("Processing PDF...");
}
else if (attachment.ContentType.MediaType == "image/jpeg")
{
    Console.WriteLine("Processing JPEG...");
}
```

- `ContentType.MediaType` 识别文件类型（例如， `application/pdf` 对于 PDF， `image/jpeg` 用于图像）。
- 根据需要为不同文件类型添加自定义逻辑。


## 结论

就是这样！从电子邮件中提取附件不再是一项繁琐的任务。使用 Aspose.Email for .NET，您只需几行代码即可自动完成此过程。从设置 IMAP 客户端到本地保存附件，本指南涵盖了您入门所需的一切。 

那么，为什么还要等待呢？ [下载 Aspose.Email](https://releases.aspose.com/email/net/) 立即开始简化您的电子邮件工作流程！


## 常见问题解答

### 我可以将此代码用于 Gmail 或 Outlook 吗？
是的！更换 `imap.example.com` 使用 Gmail 的 (`imap.gmail.com`) 或 Outlook 的 (`outlook.office365.com`) IMAP 服务器地址。

### Aspose.Email 可以免费使用吗？
Aspose.Email 需要许可证才能使用全部功能。您可以申请 [免费试用](https://releases.aspose.com/) 或 [临时执照](https://purchase。aspose.com/temporary-license/).

### 我该如何处理密码安全？
考虑使用环境变量或安全凭证存储而不是硬编码密码。

### 我可以从已发送邮件中提取附件吗？
是的，只需使用 `SelectFolder(ImapFolderInfo.Sent)` 而不是收件箱。

### Aspose.Email 支持 POP3 吗？
当然！除了 IMAP，它还支持 POP3 和 SMTP。