---
"description": "Узнайте, как легко изменить ориентацию страниц PDF-файлов с помощью Aspose.PDF для .NET. Это пошаговое руководство содержит чёткие инструкции по загрузке, повороту и сохранению документов."
"linktitle": "Изменить ориентацию страницы PDF"
"second_title": "Справочник по API Aspose.PDF для .NET"
"title": "Изменить ориентацию страницы PDF"
"url": "/ru/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Введение

Вы когда-нибудь сталкивались с PDF-файлом, ориентация страниц которого совершенно неправильная? Независимо от того, был ли документ неправильно отсканирован или ему просто требуется изменить макет, изменение ориентации может иметь огромное значение. К счастью, Aspose.PDF для .NET предлагает мощный и удобный инструмент для работы с PDF-файлами, включая изменение ориентации страниц. В этом руководстве мы пошагово объясним вам, как изменить ориентацию с книжной на альбомную или наоборот.

## Предпосылки

Прежде чем углубляться в детали, убедитесь, что у вас есть следующее:

- Aspose.PDF для .NET: Убедитесь, что у вас установлена библиотека Aspose.PDF. Если вы ещё этого не сделали, вы можете [скачать здесь](https://releases.aspose.com/pdf/net/).
- Среда разработки .NET: вы можете использовать Visual Studio, JetBrains Rider или любую другую предпочитаемую вами IDE для разработки .NET.
- Базовые знания C#: знакомство с C# поможет вам легче понимать материал.
- PDF-файл: подготовьте образец PDF-файла для тестирования. Вы можете создать его самостоятельно или скачать онлайн.

Если вы только начинаете, попробуйте Aspose.PDF с [бесплатная временная лицензия](https://purchase.aspose.com/temporary-license/) прежде чем принять решение [купить полную версию](https://purchase.aspose.com/buy).

## Импорт пространств имен

Для работы со страницами PDF-файла необходимо импортировать необходимые пространства имён в ваш проект C#. Добавьте следующие строки в начало файла кода:

```csharp
using System.IO;
using Aspose.Pdf;
```

Теперь, когда все готово, давайте начнем!

## Шаг 1: Загрузите PDF-документ

Первый шаг — загрузить PDF-файл, который вы хотите изменить. Используйте `Document` класс из пространства имен Aspose.PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Обязательно замените `"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему PDF-файлу.

## Шаг 2: Просмотрите каждую страницу

Далее мы пройдёмся по каждой странице PDF-документа. Это позволит нам применить изменение ориентации ко всем страницам:

```csharp
foreach (Page page in doc.Pages)
{
    // Манипулируйте каждой страницей
}
```

## Шаг 3: Доступ к MediaBox страницы

Каждая страница PDF-файла имеет `MediaBox` определяющий его границы. Нам нужен доступ к нему, чтобы проверить текущую ориентацию и внести изменения:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

The `MediaBox` указывает размеры страницы, включая ширину и высоту.

## Шаг 4: Поменяйте местами ширину и высоту

Чтобы изменить ориентацию страницы, поменяем местами значения ширины и высоты. Это изменение изменит размеры страницы:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Здесь мы вычисляем новые размеры и изменяем положение нижнего левого угла (`LLY`) соответственно.

## Шаг 5: Обновите MediaBox и CropBox

Теперь, когда у нас есть новые измерения, мы применим эти изменения к `MediaBox` и `CropBox` чтобы обеспечить корректное отображение страницы:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Шаг 6: Поверните страницу

Чтобы завершить смену ориентации, мы повернем страницу. С Aspose.PDF это просто:

```csharp
page.Rotate = Rotation.on90; // Повернуть на 90 градусов
```

Эта линия фактически переворачивает страницу в нужную ориентацию.

## Шаг 7: Сохраните выходной PDF-файл

После изменения ориентации всех страниц сохраните обновленный документ в новый файл:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Обязательно укажите новое имя файла, чтобы избежать перезаписи исходного документа.

## Заключение

Вот и всё! Изменить ориентацию страницы PDF-файла с помощью Aspose.PDF для .NET очень просто. Загрузив документ, пролистав страницы, обновив MediaBox и сохранив файл, вы легко сможете настроить макет в соответствии со своими потребностями. Это руководство поможет вам эффективно справиться с любой задачей, будь то исправление плохо отсканированного документа или форматирование страниц для презентации.

## Часто задаваемые вопросы

### Можно ли повернуть определенные страницы, а не все страницы PDF-файла?  
Да, вы можете изменить цикл так, чтобы он охватывал определенные страницы по их индексу, а не перебирал все страницы.

### Что такое `MediaBox`?  
The `MediaBox` определяет размер и форму страницы в PDF-файле, определяя место размещения содержимого.

### Работает ли Aspose.PDF for .NET с другими форматами файлов?  
Да, Aspose.PDF может обрабатывать различные форматы файлов, включая HTML, XML, XPS и другие.

### Существует ли бесплатная версия Aspose.PDF для .NET?  
Да, вы можете начать с [бесплатная пробная версия](https://releases.aspose.com/) или запросить [временная лицензия](https://purchase.aspose.com/temporary-license/).

### Можно ли отменить изменения после сохранения?  
После сохранения документа изменения становятся постоянными. Рекомендуется работать с копией или сохранить резервную копию исходного файла.