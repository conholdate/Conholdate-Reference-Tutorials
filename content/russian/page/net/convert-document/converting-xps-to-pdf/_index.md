---
"description": "Узнайте, как легко преобразовать документы XPS (XML Paper Specification) в PDF (Portable Document Format) с помощью мощной библиотеки Aspose.Page для .NET."
"linktitle": "Преобразование XPS в PDF"
"second_title": "API Aspose.Page .NET"
"title": "Преобразование XPS в PDF с помощью Aspose.Page для .NET"
"url": "/ru/page/net/convert-document/converting-xps-to-pdf/"
"weight": 11
---

## Введение

В этом руководстве мы рассмотрим, как преобразовать документы XPS (XML Paper Specification) в PDF (Portable Document Format) с помощью универсальной библиотеки Aspose.Page для .NET. Эта мощная библиотека упрощает преобразование документов и предлагает различные возможности настройки, что делает её отличным выбором для разработчиков.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Библиотека Aspose.Page for .NET: загрузите и установите библиотеку Aspose.Page for .NET с сайта [Документация Aspose.Page](https://reference.aspose.com/page/net/).
  
- Среда разработки: настройте среду разработки .NET с помощью Visual Studio или другой совместимой IDE.

- Документ XPS: Подготовьте файл XPS, который вы хотите преобразовать, и сохраните его в указанном каталоге.

## Шаг 1: Импорт необходимых пространств имен

Начните с импорта необходимого пространства имен для доступа к функциям Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

## Шаг 2: Инициализация каталога документов

Определите путь к каталогу, где хранятся ваши документы:

```csharp
string dataDir = "Your Document Directory";
```

Обязательно замените `"Your Document Directory"` с фактическим путем к каталогу, содержащему ваш XPS-документ.

### Шаг 3: Откройте потоки PDF и XPS

Затем инициализируйте потоки для входного XPS-файла и выходного PDF-файла:

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Убедитесь, что вы указали правильный путь для своих файлов.

### Шаг 4: Загрузите XPS-документ

Теперь загрузите ваш XPS-документ с помощью библиотеки Aspose.Page:

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Шаг 5: Настройте параметры сохранения PDF-файла

Настройте параметры сохранения вашего PDF-файла, включая качество изображения и параметры сжатия:

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100, // Установите уровень качества JPEG
    ImageCompression = PdfImageCompression.Jpeg, // Использовать сжатие JPEG для изображений
    TextCompression = PdfTextCompression.Flate, // Применить сжатие Flate к тексту
    PageNumbers = new int[] { 1, 2, 6 } // Укажите номера страниц, которые нужно включить
};
```

Вы можете свободно изменять эти параметры в соответствии с вашими требованиями.

### Шаг 6: Создайте устройство визуализации PDF-файлов

Создайте устройство рендеринга для формата PDF:

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Шаг 7: Сохраните документ как PDF

Наконец, сохраните документ XPS в PDF, используя указанное устройство и параметры:

```csharp
document.Save(device, options);
```

## Заключение

Поздравляем! Вы успешно преобразовали XPS-документ в PDF с помощью Aspose.Page for .NET. Эта библиотека не только упрощает преобразование документов, но и предлагает широкие возможности для работы с различными форматами.

## Часто задаваемые вопросы

### Можно ли конвертировать несколько файлов XPS в один PDF?

Конечно! Вы можете обработать несколько XPS-файлов и объединить их в один PDF-документ, выполнив те же шаги конвертации.

### Какие еще форматы вывода поддерживает Aspose.Page for .NET?

Помимо PDF, Aspose.Page for .NET поддерживает ряд форматов, включая TIFF, JPEG и PNG.

### Как настроить внешний вид преобразованного PDF-файла?

Вы можете настроить параметры в `PdfSaveOptions` объекта, например, качество JPEG и параметры сжатия, чтобы добиться желаемого вида.

### Доступна ли пробная версия Aspose.Page для .NET?

Да, вы можете попробовать Aspose.Page for .NET с бесплатной пробной версией. [здесь](https://releases.aspose.com/).

### Где я могу найти поддержку сообщества для Aspose.Page for .NET?

Для обсуждения в сообществе и получения поддержки посетите [Форум Aspose.Page](https://forum.aspose.com/c/page/39).