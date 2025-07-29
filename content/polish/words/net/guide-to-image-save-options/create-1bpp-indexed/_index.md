---
"description": "tym przewodniku znajdziesz instrukcje krok po kroku i przykładowy kod, które pomogą Ci efektywnie tworzyć obrazy indeksowane 1 Bpp na potrzeby archiwizacji, drukowania lub w celu oszczędzania miejsca."
"linktitle": "Utwórz indeks 1Bpp"
"second_title": "API przetwarzania dokumentów Aspose.Words"
"title": "Utwórz indeks 1Bpp"
"url": "/pl/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## Wstęp

Czy kiedykolwiek potrzebowałeś przekonwertować dokument Worda na czarno-biały obraz? Niezależnie od tego, czy chodzi o archiwizację cyfrową, drukowanie, czy po prostu oszczędzanie miejsca, konwersja dokumentów do obrazu indeksowanego 1 Bpp może być niezwykle przydatna. W tym przewodniku pokażemy prostą metodę, jak to zrobić za pomocą Aspose.Words dla .NET. Zaczynajmy!

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnij się, że masz następujące elementy:

- Aspose.Words dla .NET: Pobierz i zainstaluj bibliotekę ze strony [Tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne .NET: Choć popularnym wyborem jest Visual Studio, sprawdzi się każde środowisko IDE obsługujące platformę .NET.
- Podstawowa wiedza o języku C#: Znajomość języka C# będzie pomocna, ale postaramy się przedstawić sprawę w prosty sposób.
- Przykładowy dokument Word: Przygotuj dokument do konwersji.

## Krok 1: Importuj niezbędne przestrzenie nazw

Aby korzystać z Aspose.Words, należy zaimportować odpowiednie przestrzenie nazw. Jest to niezbędne do uzyskania dostępu do klas i metod wymaganych do manipulacji dokumentami.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 2: Skonfiguruj katalog dokumentów

Podaj ścieżkę do katalogu, w którym znajduje się dokument Word i w którym chcesz zapisać przekonwertowany obraz.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Krok 3: Załaduj dokument Word

Załaduj dokument Word do `Aspose.Words.Document` Obiekt. Ten obiekt umożliwia programowe manipulowanie dokumentem.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 4: Skonfiguruj opcje zapisywania obrazu

Następnie skonfiguruj `ImageSaveOptions` Aby zdefiniować sposób zapisywania dokumentu jako obrazu, skonfigurujemy go do zapisu w formacie PNG z indeksowanym trybem kolorów 1 Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // Konwertuj tylko pierwszą stronę
    ImageColorMode = ImageColorMode.BlackAndWhite, // Ustaw na czarno-biały
    PixelFormat = ImagePixelFormat.Format1bppIndexed // Użyj formatu indeksowanego 1Bpp
};
```

- SaveFormat.Png: Określa, że formatem wyjściowym będzie PNG.
- PageSet(1): Oznacza, że zostanie przekonwertowana tylko pierwsza strona dokumentu.
- ImageColorMode.BlackAndWhite: Zapewnia, że obraz jest czarno-biały.
- ImagePixelFormat.Format1bppIndexed: Ustawia format pikseli na indeksowany 1Bpp, optymalizując przestrzeń.

## Krok 5: Zapisz dokument jako obraz

Na koniec użyj `Save` metoda `Document` obiekt służący do zapisania przekonwertowanego obrazu.

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## Wniosek

Gratulacje! Udało Ci się przekonwertować dokument Worda na obraz indeksowany 1 Bpp za pomocą Aspose.Words dla .NET. Ta metoda jest nie tylko wydajna, ale także pomaga tworzyć obrazy o wysokim kontraście, odpowiednie do różnych aplikacji. Możesz śmiało zintegrować tę funkcjonalność ze swoimi projektami. Powodzenia w kodowaniu!

## Najczęściej zadawane pytania

### Czym jest obraz indeksowany 1Bpp?
Obraz indeksowany 1Bpp (1 bit na piksel) to czarno-biały format obrazu, w którym każdy piksel jest reprezentowany przez pojedynczy bit, 0 lub 1. Format ten jest bardzo oszczędny pod względem zajmowanej przestrzeni, dzięki czemu idealnie nadaje się do archiwizacji.

### Czy mogę przekonwertować wiele stron dokumentu Word jednocześnie?
Tak! Po prostu zmodyfikuj `PageSet` nieruchomość w `ImageSaveOptions` aby uwzględnić wiele stron lub przekonwertować cały dokument.

### Czy potrzebuję licencji, aby używać Aspose.Words dla .NET?
Tak, do pełnej funkcjonalności wymagana jest licencja. Możesz ją uzyskać [tymczasowa licencja tutaj](https://purchase.aspose.com/temporary-license/).

### Do jakich innych formatów obrazów mogę przekonwertować mój dokument Word?
Aspose.Words obsługuje różne formaty, w tym JPEG, BMP i TIFF. Wystarczy zmienić `SaveFormat` w `ImageSaveOptions` do żądanego formatu.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words dla .NET?
Aby uzyskać pełną dokumentację, odwiedź stronę [Strona dokumentacji Aspose.Words dla .NET](https://reference.aspose.com/words/net/).