---
"description": "Узнайте, как эффективно извлекать, удалять и добавлять записи в zip-файлы программным способом, расширяя возможности манипулирования файлами."
"linktitle": "Изменить ZIP-файлы"
"second_title": "API Aspose.Zip .NET для сжатия и архивации файлов"
"title": "Изменение ZIP-файлов с помощью Aspose.Zip для .NET"
"url": "/ru/zip/net/file-compress/modify-zip-files/"
"weight": 15
---

## Введение

ZIP-файлы жизненно важны для организации и сжатия данных, но как программно изменить их содержимое? Решение кроется в Aspose.Zip для .NET — мощной библиотеке, упрощающей работу с ZIP-файлами на C#. В этом руководстве мы пошагово покажем вам, как извлекать, удалять и добавлять записи в ZIP-файлы.

## Предпосылки

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Aspose.Zip для библиотеки .NET: установите библиотеку в свой проект. Вы можете скачать её [здесь](https://releases.aspose.com/zip/net/).
   
2. Каталог документов: создайте каталог для хранения ZIP-файлов. Заменить `"Your Document Directory"` в коде укажите ваш реальный путь.

## Импорт необходимых пространств имен

Начните с импорта необходимых пространств имен:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Откройте внешний ZIP-файл

Начните с открытия вашего основного zip-файла (внешнего zip-архива):

```csharp
string dataDir = "Your Data Directory";
using (Archive outer = new Archive(dataDir + "outer.zip"))
{
    // Продолжайте идентифицировать внутренние почтовые индексы
}
```

## Шаг 2: Определите внутренние почтовые индексы

Далее определите и подготовьтесь к удалению всех внутренних zip-файлов:

```csharp
List<ArchiveEntry> entriesToDelete = new List<ArchiveEntry>();
List<string> namesToInsert = new List<string>();
List<MemoryStream> contentToInsert = new List<MemoryStream>();

foreach (ArchiveEntry entry in outer.Entries)
{
    if (entry.Name.EndsWith(".zip", StringComparison.InvariantCultureIgnoreCase))
    {
        entriesToDelete.Add(entry);
        
        using (MemoryStream innerCompressed = new MemoryStream())
        {
            entry.Open().CopyTo(innerCompressed);
            
            // Извлечь внутренние записи
            using (Archive inner = new Archive(innerCompressed))
            {
                foreach (ArchiveEntry ie in inner.Entries)
                {
                    namesToInsert.Add(ie.Name);
                    MemoryStream content = new MemoryStream();
                    ie.Open().CopyTo(content);
                    contentToInsert.Add(content);
                }
            }
        }
    }
}
```

## Шаг 3: Удалить записи внутреннего архива

После того как вы собрали необходимые записи, удалите внутренние записи zip-архива:

```csharp
foreach (ArchiveEntry e in entriesToDelete)
{
    outer.DeleteEntry(e);
}
```

## Шаг 4: Добавьте измененные записи во внешний почтовый индекс

Теперь вы можете добавить вновь извлеченные записи обратно во внешний zip-файл:

```csharp
for (int i = 0; i < namesToInsert.Count; i++)
{
    outer.CreateEntry(namesToInsert[i], contentToInsert[i]);
}
```

## Шаг 5: Сохраните измененный ZIP-файл

Наконец, сохраните изменения в новом zip-файле:

```csharp
outer.Save(dataDir + "flatten.zip");
```

## Заключение

Aspose.Zip для .NET предоставляет мощный и простой способ программного управления ZIP-файлами. В этом руководстве рассматриваются извлечение, удаление и добавление записей в ZIP-файл, что демонстрирует универсальность библиотеки. Изучите различные сценарии и улучшите свои навыки работы с файлами!

## Часто задаваемые вопросы

### Могу ли я использовать Aspose.Zip для .NET с другими языками программирования?
Aspose.Zip в первую очередь разработан для приложений .NET, но Aspose предлагает аналогичные библиотеки для различных языков программирования.

### Существует ли бесплатная пробная версия Aspose.Zip для .NET?
Да, бесплатная пробная версия доступна для загрузки. [здесь](https://releases.aspose.com/).

### Как получить поддержку Aspose.Zip для .NET?
Посетите [Форум Aspose.Zip](https://forum.aspose.com/c/zip/37) для поддержки и обсуждений.

### Могу ли я приобрести временную лицензию на Aspose.Zip для .NET?
Да, вы можете получить временную лицензию. [здесь](https://purchase.conholdate.com/temporary-license/).

### Где я могу найти документацию по Aspose.Zip для .NET?
Полная документация доступна [здесь](https://reference.aspose.com/zip/net/).