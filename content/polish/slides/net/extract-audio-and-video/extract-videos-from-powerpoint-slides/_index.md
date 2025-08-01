---
"description": "Dowiedz się, jak łatwo wyodrębniać osadzone pliki wideo z prezentacji PowerPoint za pomocą Aspose.Slides dla .NET. Ten kompleksowy przewodnik krok po kroku obejmuje wszystko, od konfiguracji środowiska po zapisywanie wyodrębnionych filmów."
"linktitle": "Wyodrębnij filmy ze slajdów programu PowerPoint"
"second_title": "Aspose.Slides .NET Interfejs API przetwarzania programu PowerPoint"
"title": "Wyodrębnianie filmów ze slajdów programu PowerPoint za pomocą Aspose.Slides"
"url": "/pl/slides/net/extract-audio-and-video/extract-videos-from-powerpoint-slides/"
"weight": 14
---

## Wstęp

Aspose.Slides for .NET to potężna biblioteka, która umożliwia programistom programistyczną interakcję z prezentacjami PowerPoint. W tym przewodniku przeprowadzimy Cię przez proces wyodrębniania filmów osadzonych w slajdach PowerPoint za pomocą Aspose.Slides for .NET. 

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę z [Strona internetowa Aspose](https://purchase.aspose.com/buy).
- Prezentacja PowerPoint: Przygotuj plik PowerPoint (np. `Video.pptx`) z filmem, który chcesz wyodrębnić.

## Niezbędne przestrzenie nazw

Aby korzystać z Aspose.Slides dla .NET, musisz zaimportować odpowiednie przestrzenie nazw. Umieść w kodzie następujące elementy:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

## Krok 1: Określ katalog dokumentów

Najpierw zdefiniuj ścieżkę do swojej prezentacji PowerPoint:

```csharp
string dataDir = "Your Document Directory";
```

Zastępować `"Your Document Directory"` z rzeczywistą ścieżką do katalogu zawierającego plik programu PowerPoint.

## Krok 2: Załaduj prezentację

Załaduj prezentację programu PowerPoint do `Presentation` obiekt:

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

To inicjuje `Presentation` obiekt ze wskazanym plikiem programu PowerPoint.

## Krok 3: Przejrzyj slajdy i kształty

Następnie przejrzyj każdy slajd prezentacji i sprawdź, czy zawiera klatki wideo:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in slide.Shapes)
    {
        if (shape is VideoFrame videoFrame)
        {
            // Przejdź do wyodrębnienia wideo
        }
    }
}
```

## Krok 4: Wyodrębnij dane wideo

Po znalezieniu klatki wideo wyodrębnij jej właściwości i dane binarne:

```csharp
IVideoFrame vf = (IVideoFrame)shape;  // Zapisz kształt jako klatkę wideo
string contentType = vf.EmbeddedVideo.ContentType;
Byte[] buffer = vf.EmbeddedVideo.BinaryData;

// Pobierz rozszerzenie pliku
string fileExtension = contentType.Substring(contentType.LastIndexOf('/') + 1);
```

## Krok 5: Zapisz wideo

Na koniec zapisz wyodrębnione dane wideo do pliku:

```csharp
using (FileStream stream = new FileStream(dataDir + "ExtractedVideo." + fileExtension, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Ten kod tworzy nowy plik w określonym katalogu i zapisuje do niego dane wideo.

## Wniosek

Dzięki Aspose.Slides dla .NET wyodrębnianie filmów ze slajdów programu PowerPoint to prosty proces. Postępując zgodnie z tym przewodnikiem, możesz łatwo zarządzać treściami multimedialnymi w aplikacjach .NET, wzbogacając ich funkcjonalność i komfort użytkowania.

## Najczęściej zadawane pytania

### Czym jest Aspose.Slides dla .NET?
Aspose.Slides for .NET to biblioteka przeznaczona do pracy z prezentacjami programu PowerPoint, umożliwiająca użytkownikom programowe tworzenie, edytowanie i modyfikowanie plików prezentacji.

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
Możesz uzyskać dostęp do pełnej dokumentacji [Tutaj](https://reference.aspose.com/slides/net/).

### Czy Aspose.Slides dla .NET jest dostępny w ramach bezpłatnego okresu próbnego?
Tak, możesz pobrać bezpłatną wersję próbną ze strony [ten link](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla .NET?
Można składać wnioski o licencje tymczasowe [Tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla .NET?
Wsparcie jest dostępne poprzez [Forum Aspose.Slides](https://forum.aspose.com/).