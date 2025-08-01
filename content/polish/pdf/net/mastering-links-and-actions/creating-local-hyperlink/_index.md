---
"description": "Dowiedz się, jak usprawnić nawigację w dokumentach PDF, tworząc lokalne hiperłącza za pomocą Aspose.PDF dla platformy .NET. Ten samouczek krok po kroku przeprowadzi Cię przez cały proces."
"linktitle": "Tworzenie lokalnego hiperłącza w pliku PDF"
"second_title": "Aspose.PDF dla .NET API Reference"
"title": "Tworzenie lokalnego hiperłącza w pliku PDF"
"url": "/pl/pdf/net/mastering-links-and-actions/creating-local-hyperlink/"
"weight": 40
---

## Wstęp

W tym przewodniku przeprowadzimy Cię przez proces tworzenia lokalnych hiperłączy w pliku PDF za pomocą Aspose.PDF dla platformy .NET. Każdy krok zostanie dokładnie opisany, dzięki czemu nawet osoby początkujące w pracy z plikami PDF bez problemu sobie z nim poradzą.

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnij się, że masz następujące elementy:

1. Visual Studio: Pobierz ze strony [Witryna internetowa Visual Studio](https://visualstudio.microsoft.com/).
2. Aspose.PDF dla .NET: Pobierz bibliotekę za pomocą [Strona internetowa Aspose](https://releases.aspose.com/pdf/net/)Ta biblioteka udostępnia bogaty zestaw funkcji do manipulowania plikami PDF.
3. Podstawowa znajomość języka C#: Znajomość programowania w języku C# będzie pomocna, ale nie martw się – wyjaśnimy kod linijka po linijce.
4. .NET Framework: Upewnij się, że na Twoim komputerze jest zainstalowany .NET Framework. Sprawdź wymagania w pliku Aspose.PDF. [dokumentacja](https://reference.aspose.com/pdf/net/).

Mając te wymagania wstępne, możesz się nauczyć, jak tworzyć lokalne hiperłącza w dokumentach PDF!

## Importowanie wymaganych pakietów

Teraz, gdy wszystko jest już skonfigurowane, czas zaimportować niezbędne pakiety do projektu C#.

### Otwórz swój projekt

Otwórz istniejący projekt .NET lub utwórz nowy w programie Visual Studio. Jeśli zaczynasz od nowa, wybierz opcję „Utwórz nowy projekt” na ekranie startowym.

### Dodaj odniesienie do Aspose.PDF

Kliknij prawym przyciskiem myszy „Zależności” w folderze projektu w Eksploratorze rozwiązań. Wybierz „Zarządzaj pakietami NuGet” i wyszukaj `Aspose.PDF`i zainstaluj najnowszą dostępną wersję. Dzięki temu uzyskasz dostęp do wszystkich narzędzi potrzebnych do tworzenia i edycji plików PDF.

### Importuj przestrzenie nazw

Na górze pliku .cs dodaj następujące dyrektywy using:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Dyrektywy te umożliwiają bezproblemowy dostęp do funkcji biblioteki.

Omówmy proces tworzenia lokalnych hiperłączy w prostych krokach.

## Krok 1: Skonfiguruj instancję dokumentu

Utwórz nową instancję `Document` klasa reprezentująca plik PDF, z którym będziesz pracować.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ustaw katalog dokumentów
Document doc = new Document(); // Utwórz instancję dokumentu
```

Zastępować `"YOUR_DOCUMENT_DIRECTORY"` z rzeczywistą ścieżką w systemie, w której zostanie zapisany plik PDF.

## Krok 2: Dodaj stronę do dokumentu

Następnie dodaj stronę do dokumentu PDF.

```csharp
Page page = doc.Pages.Add(); // Dodaj nową stronę
```

Ten wiersz dodaje do dokumentu nową stronę, na której będzie umieszczona cała Twoja treść.

## Krok 3: Utwórz fragment tekstu

Teraz utwórzmy fragment tekstu, który będzie działał jako klikalny link.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7"); // Utwórz fragment tekstu
```

Ten `TextFragment` wyświetli tekst, w który użytkownicy mogą kliknąć.

## Krok 4: Utwórz lokalne hiperłącze

Teraz utwórz lokalny hiperłącze kierujące do strony 7.

```csharp
LocalHyperlink link = new LocalHyperlink(); // Utwórz lokalne hiperłącze
link.TargetPageNumber = 7; // Ustaw stronę docelową dla linku
text.Hyperlink = link; // Ustaw hiperłącze dla fragmentu tekstu
```

Ten `LocalHyperlink` Klasa ta umożliwia określenie numeru strony docelowej dla hiperłącza.

## Krok 5: Dodaj fragment tekstu do strony

Dodaj klikalny tekst do utworzonej strony.

```csharp
page.Paragraphs.Add(text); // Dodaj fragment tekstu do strony
```

Ten wiersz dodaje Twój tekst do zbioru akapitów na stronie.

## Krok 6: Utwórz kolejny fragment tekstu (opcjonalnie)

Dodajmy kolejny hiperłącze, aby powrócić do strony 1.

```csharp
TextFragment textBack = new TextFragment("Link to page 1"); // Utwórz nowy fragment tekstu
textBack.IsInNewPage = true; // Wskaż, że powinno to znaleźć się na nowej stronie
```

## Krok 7: Skonfiguruj drugi lokalny hiperłącze

Utwórz kolejny lokalny hiperłącze dla strony 1.

```csharp
Aspose.Pdf.LocalHyperlink linkBack = new Aspose.Pdf.LocalHyperlink(); // Utwórz kolejny lokalny hiperłącze
linkBack.TargetPageNumber = 1; // Ustaw stronę docelową dla drugiego hiperłącza
textBack.Hyperlink = linkBack; // Ustaw hiperłącze dla drugiego fragmentu tekstu
```

## Krok 8: Dodaj drugi fragment tekstu do nowej strony

Dodaj drugi fragment tekstu do odpowiedniej strony.

```csharp
Page newPage = doc.Pages.Add(); // Dodaj nową stronę dla drugiego linku
newPage.Paragraphs.Add(textBack); // Dodaj fragment tekstu do nowej strony
```

## Krok 9: Zapisz dokument

Na koniec zapisz dokument.

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Podaj nazwę pliku wyjściowego
doc.Save(dataDir); // Zapisz zaktualizowany dokument
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```

Ten wiersz łączy ścieżkę do katalogu z nazwą pliku i `Save()` Metoda zapisuje Twój dokument.

## Wniosek

Tworzenie lokalnych hiperłączy w plikach PDF za pomocą Aspose.PDF dla platformy .NET to praktyczna funkcja, która usprawnia nawigację i komfort użytkowania. Dzięki temu posiadasz wiedzę, która pozwoli Ci bezpośrednio kierować czytelników do potrzebnych informacji, czyniąc Twoje pliki PDF bardziej interaktywnymi i przyjaznymi dla użytkownika.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom tworzenie, modyfikowanie i konwertowanie dokumentów PDF programowo przy użyciu środowiska .NET.

### Czy mogę tworzyć hiperłącza do zewnętrznych stron internetowych?
Tak, Aspose.PDF oprócz lokalnych hiperłączy w pliku PDF obsługuje również tworzenie hiperłączy do zewnętrznych adresów URL.

### Czy istnieje bezpłatna wersja próbna Aspose.PDF?
Oczywiście! Możesz uzyskać dostęp do bezpłatnej wersji próbnej z [Strona internetowa Aspose](https://releases.aspose.com/).

### Jakie języki programowania obsługuje Aspose?
Aspose oferuje biblioteki dla różnych języków programowania, w tym m.in. Java, C++ i Python.

### Jak uzyskać pomoc techniczną dotyczącą produktów Aspose?
Możesz szukać wsparcia poprzez [Forum Aspose](https://forum.aspose.com/c/pdf/10).