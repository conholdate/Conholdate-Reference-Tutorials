---
"description": "Dowiedz się, jak wykorzystać klasę w Aspose.Tasks dla platformy .NET do filtrowania zadań projektu na podstawie wielu warunków. Łącząc kryteria, takie jak zadania sumaryczne i atrybuty różne od null."
"linktitle": "Filtrowanie zadań i operacja w Aspose.Tasks"
"second_title": "Aspose.Tasks .NET API"
"title": "Filtrowanie zadań i operacja w Aspose.Tasks"
"url": "/pl/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Wstęp

W tym samouczku pokażemy, jak wykonywać zaawansowane filtrowanie zadań projektu w Aspose.Tasks dla .NET, wykorzystując `Util.And` Klasa. Ta potężna funkcja pozwala programistom efektywnie filtrować zadania na podstawie wielu kryteriów.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

1. Podstawowa znajomość programowania w języku C#.
2. Aspose.Tasks dla .NET jest zainstalowany. Jeśli jeszcze tego nie zrobiłeś, możesz go pobrać ze strony [ten link](https://releases.aspose.com/tasks/net/).
3. Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio, służące do pisania i uruchamiania kodu.

## Importowanie przestrzeni nazw

Aby rozpocząć, musisz zaimportować wymagane przestrzenie nazw do swojego projektu C#. Umożliwi to dostęp do funkcjonalności oferowanych przez Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Krok 1: Zainicjuj projekt i zbierz zadania

Najpierw zainicjuj projekt Aspose.Tasks i zbierz wszystkie zadania w nim zawarte. Dla celów demonstracyjnych załóżmy, że istnieje plik projektu o nazwie `Project2.mpp`.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Zbierz wszystkie zadania podrzędne
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Krok 2: Zdefiniuj warunki filtrowania

W tym kroku zdefiniujemy warunki filtrowania zadań. W naszym przykładzie utworzymy dwa warunki: jeden do filtrowania zadań sumarycznych i drugi, który zapewni, że zadania nie będą puste.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Krok 3: Połącz warunki za pomocą operacji AND

Następnym krokiem jest połączenie tych warunków za pomocą `Util.And` Klasa. Pozwala nam to stworzyć warunek złożony, który wymaga spełnienia obu kryteriów.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Krok 4: Zastosuj połączony warunek i zadania filtrowania

Teraz zastosujmy połączony warunek do zebranych zadań, aby odfiltrować konkretne zadania spełniające oba warunki.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Krok 5: Wyjście przefiltrowanych zadań

Na koniec przeanalizujemy odfiltrowane zadania i przedstawimy odpowiednie szczegóły. Pomoże nam to zrozumieć, które zadania spełniają nasze kryteria.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Wniosek

W tym samouczku pokazaliśmy, jak wykonywać zaawansowane operacje filtrowania w Aspose.Tasks dla .NET przy użyciu `Util.And` Klasa. Łącząc wiele warunków, możemy skutecznie filtrować zadania, zwiększając w ten sposób użyteczność naszych aplikacji do zarządzania projektami.

## Najczęściej zadawane pytania

### Czym jest Aspose.Tasks dla .NET?

Aspose.Tasks for .NET to wszechstronny interfejs API przeznaczony dla programistów, który umożliwia programistyczne manipulowanie plikami Microsoft Project w aplikacjach .NET.

### Czy mogę łączyć więcej niż dwa warunki za pomocą Util.And?

Tak! `Util.And` Klasa ta umożliwia łączenie wielu warunków, co pozwala na stosowanie złożonej logiki filtrowania dostosowanej do Twoich potrzeb.

### Czy jest dostępna bezpłatna wersja próbna Aspose.Tasks?

Tak, możesz pobrać bezpłatną wersję próbną ze strony [ten link](https://releases.aspose.com/).

### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks?

Szczegółowa dokumentacja jest dostępna [Tutaj](https://reference.aspose.com/tasks/net/).

### Jak mogę uzyskać pomoc dotyczącą Aspose.Tasks?

Pomoc jest dostępna za pośrednictwem forum społeczności Aspose.Tasks, do którego można uzyskać dostęp [Tutaj](https://forum.aspose.com/c/tasks/15).