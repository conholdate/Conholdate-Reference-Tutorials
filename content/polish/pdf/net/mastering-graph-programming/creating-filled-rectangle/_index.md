---
"description": "Odkryj możliwości edycji plików PDF dzięki Aspose.PDF dla .NET w tym samouczku krok po kroku. Dowiedz się, jak programowo tworzyć atrakcyjne wizualnie dokumenty PDF, rysując wypełnione prostokąty."
"linktitle": "Tworzenie wypełnionego prostokąta"
"second_title": "Aspose.PDF dla .NET API Reference"
"title": "Tworzenie wypełnionego prostokąta"
"url": "/pl/pdf/net/mastering-Graph-programming/creating-filled-rectangle/"
"weight": 50
---

## Wstęp

Czy kiedykolwiek chciałeś programowo tworzyć zachwycające wizualnie pliki PDF? Jeśli tak, to jesteś we właściwym miejscu! W tym samouczku poznamy Aspose.PDF dla platformy .NET, potężną bibliotekę, która upraszcza manipulację dokumentami PDF. Dzisiaj skupimy się na tworzeniu wypełnionego prostokąta w pliku PDF. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik przeprowadzi Cię przez każdy krok w przyjazny i angażujący sposób. Więc chwyć za kod i zaczynajmy!

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnij się, że masz następujące elementy:

1. Visual Studio: Zainstaluj na swoim komputerze program Visual Studio. Jest to doskonałe środowisko IDE do tworzenia aplikacji .NET.
2. Aspose.PDF dla .NET: Pobierz i zainstaluj bibliotekę Aspose.PDF z [Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa wiedza z zakresu języka C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć fragmenty kodu.

## Krok 1: Utwórz nowy projekt

1. Otwórz program Visual Studio i utwórz nowy projekt aplikacji konsolowej.
2. Nadaj swojemu projektowi odpowiednią nazwę.

## Krok 2: Dodaj odniesienie do Aspose.PDF

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań.
2. Wybierz opcję Zarządzaj pakietami NuGet.
3. Wyszukaj Aspose.PDF i zainstaluj najnowszą wersję.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Teraz, gdy wszystko mamy już skonfigurowane, możemy zagłębić się w kod!

## Krok 3: Skonfiguruj katalog dokumentów

Podaj ścieżkę, w której zostanie zapisany Twój plik PDF:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Zastępować `"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką na Twoim komputerze, gdzie chcesz zapisać plik PDF.

## Krok 4: Utwórz instancję dokumentu

Zainicjuj nowy dokument PDF:

```csharp
// Utwórz instancję dokumentu
Document doc = new Document();
```

## Krok 5: Dodaj stronę do dokumentu

Każdy plik PDF potrzebuje co najmniej jednej strony. Dodajmy jedną:

```csharp
// Dodaj stronę do zbioru stron pliku PDF
Page page = doc.Pages.Add();
```

## Krok 6: Utwórz instancję grafu

A `Graph` instancja działa jako płótno do rysowania kształtów:

```csharp
// Utwórz instancję grafu
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

## Krok 7: Dodaj wykres do strony

Dołącz wykres do strony:

```csharp
// Dodaj obiekt graficzny do zbioru akapitów instancji strony
page.Paragraphs.Add(graph);
```

## Krok 8: Utwórz instancję prostokąta

Zdefiniuj położenie i rozmiar prostokąta:

```csharp
// Utwórz instancję prostokąta
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

## Krok 9: Określ kolor wypełnienia

Wybierz kolor dla swojego prostokąta. W tym przykładzie użyjemy koloru czerwonego:

```csharp
// Określ kolor wypełnienia dla obiektu Graph
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Krok 10: Dodaj prostokąt do wykresu

Dodaj prostokąt do wykresu:

```csharp
// Dodaj obiekt prostokąta do kolekcji kształtów obiektu Graph
graph.Shapes.Add(rect);
```

## Krok 11: Zapisz dokument PDF

Na koniec zapisz dokument w podanym katalogu:

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
```

## Krok 12: Wiadomość potwierdzająca

Wydrukuj komunikat potwierdzający, aby poinformować o powodzeniu:

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Udało Ci się utworzyć wypełniony prostokąt w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET. Ta potężna biblioteka otwiera przed Tobą świat możliwości w zakresie edycji plików PDF, umożliwiając programowe generowanie zachwycających dokumentów. Niezależnie od tego, czy tworzysz raporty, faktury, czy jakikolwiek inny plik PDF, Aspose.PDF Ci w tym pomoże.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów PDF.

### Czy mogę używać pliku Aspose.PDF bezpłatnie?
Tak, Aspose oferuje bezpłatną wersję próbną, dzięki której możesz zapoznać się z funkcjami biblioteki. Możesz ją pobrać. [Tutaj](https://releases.aspose.com/).

### Czy istnieje sposób na uzyskanie wsparcia dla Aspose.PDF?
Oczywiście! Możesz uzyskać pomoc na forum Aspose. [Tutaj](https://forum.aspose.com/c/pdf/10).

### Jak mogę kupić Aspose.PDF?
Możesz kupić Aspose.PDF, odwiedzając stronę zakupu [Tutaj](https://purchase.aspose.com/buy).

### Jakie typy kształtów mogę utworzyć za pomocą Aspose.PDF?
Korzystając z biblioteki Aspose.PDF, możesz tworzyć różne kształty, w tym prostokąty, okręgi, linie i inne.