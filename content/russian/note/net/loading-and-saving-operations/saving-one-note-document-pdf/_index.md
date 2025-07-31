---
"description": "Узнайте, как эффективно сохранять документы Microsoft OneNote в формате PDF с помощью Aspose.Note для .NET. Это руководство содержит необходимые предварительные требования и полезные ответы на часто задаваемые вопросы."
"linktitle": "Сохранение документов OneNote в формате PDF"
"second_title": "API Aspose.Note .NET"
"title": "Сохранение документов OneNote в формате PDF с помощью Aspose.Note для .NET"
"url": "/ru/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Введение

В этом руководстве мы рассмотрим, как сохранять документы в формате PDF с помощью Aspose.Note для .NET. Aspose.Note — это мощная библиотека, позволяющая разработчикам программно работать с файлами Microsoft OneNote. Мы рассмотрим необходимые условия, импорт пространств имён и предоставим пошаговые инструкции по сохранению документов в формате PDF с различными макетами страниц.

## Предпосылки
1. Visual Studio: убедитесь, что он установлен.
2. Aspose.Note для .NET: загрузите и установите библиотеку.
3. Знание C#: требуется базовое понимание языка.

## Импорт необходимых пространств имен
Прежде чем продолжить, импортируйте в свой код следующие пространства имен:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Шаг 1: Сохраните в формате PDF с настройками страницы письма
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Обновить этот путь
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Загружает документ OneNote и сохраняет его как PDF-файл, используя параметры размера страницы Letter.

## Шаг 2: Сохраните в формате PDF с параметрами страницы A4 (без ограничений по высоте)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Обновить этот путь
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Аналогично шагу 1, но использует параметры страницы формата А4 без ограничений по высоте.

## Заключение
В этом руководстве успешно демонстрируется конвертация файлов OneNote в формат PDF с помощью Aspose.Note. Использование различных настроек страницы обеспечивает разработчикам гибкость в управлении документами.

## Часто задаваемые вопросы
### Может ли Aspose.Note обрабатывать сложные файлы OneNote?
Да, он эффективно обрабатывает различные функции сложных файлов OneNote.

### Подходит ли Aspose.Note для коммерческих проектов?
Да, вы можете использовать его в коммерческих целях после приобретения лицензии.

### Предлагает ли Aspose.Note бесплатную пробную версию?
Да, для ознакомления доступна бесплатная пробная версия.

### Где я могу найти документацию по Aspose.Note?
Подробная документация доступна на справочном сайте Aspose.

### Нужна дополнительная помощь?
По вопросам и для получения поддержки обращайтесь на форум Aspose.Note.