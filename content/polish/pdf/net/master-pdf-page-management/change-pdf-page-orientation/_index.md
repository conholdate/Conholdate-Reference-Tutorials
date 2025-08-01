---
"description": "Dowiedz się, jak łatwo dostosować orientację stron plików PDF za pomocą Aspose.PDF dla platformy .NET. Ten przewodnik krok po kroku zawiera jasne instrukcje dotyczące ładowania, obracania i zapisywania dokumentów."
"linktitle": "Zmień orientację strony PDF"
"second_title": "Aspose.PDF dla .NET API Reference"
"title": "Zmień orientację strony PDF"
"url": "/pl/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Wstęp

Czy zdarzyło Ci się kiedyś natrafić na plik PDF, w którym orientacja strony była zupełnie nieprawidłowa? Niezależnie od tego, czy dokument został nieprawidłowo zeskanowany, czy po prostu wymaga innego układu, dostosowanie orientacji może zdziałać cuda. Na szczęście Aspose.PDF dla platformy .NET oferuje potężny i łatwy w obsłudze sposób manipulowania plikami PDF, w tym zmiany orientacji stron. W tym przewodniku przeprowadzimy Cię krok po kroku przez ten proces, niezależnie od tego, czy chcesz zmienić orientację z pionowej na poziomą, czy odwrotnie.

## Wymagania wstępne

Zanim przejdziemy do szczegółów, upewnij się, że masz zapewnione następujące rzeczy:

- Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF. Jeśli jeszcze tego nie zrobiłeś, możesz [pobierz tutaj](https://releases.aspose.com/pdf/net/).
- Środowisko programistyczne .NET: Możesz użyć Visual Studio, JetBrains Rider lub dowolnego innego preferowanego środowiska IDE do programowania w technologii .NET.
- Podstawowa znajomość języka C#: Znajomość języka C# ułatwi Ci zrozumienie tekstu.
- Plik PDF: Przygotuj przykładowy plik PDF do przetestowania. Możesz go utworzyć lub pobrać próbkę online.

Jeśli dopiero zaczynasz, rozważ wypróbowanie Aspose.PDF z [bezpłatna licencja tymczasowa](https://purchase.aspose.com/temporary-license/) zanim zdecydujesz się [kup pełną wersję](https://purchase.aspose.com/buy).

## Importuj przestrzenie nazw

Aby manipulować stronami PDF, musisz najpierw zaimportować niezbędne przestrzenie nazw do swojego projektu C#. Dodaj następujące wiersze na początku pliku kodu:

```csharp
using System.IO;
using Aspose.Pdf;
```

Teraz, gdy wszystko już skonfigurowaliśmy, możemy zaczynać!

## Krok 1: Załaduj dokument PDF

Pierwszym krokiem jest załadowanie pliku PDF, który chcesz zmodyfikować. Użyj `Document` klasa z przestrzeni nazw Aspose.PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Pamiętaj o wymianie `"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do pliku PDF.

## Krok 2: Przejdź przez każdą stronę

Następnie przejdziemy przez każdą stronę dokumentu PDF. Dzięki temu możemy zastosować zmianę orientacji do wszystkich stron:

```csharp
foreach (Page page in doc.Pages)
{
    // Manipuluj każdą stroną
}
```

## Krok 3: Uzyskaj dostęp do MediaBox strony

Każda strona PDF ma `MediaBox` który definiuje jego granice. Musimy uzyskać do niego dostęp, aby sprawdzić aktualną orientację i wprowadzić zmiany:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

Ten `MediaBox` podaje wymiary strony, włączając szerokość i wysokość.

## Krok 4: Zamień szerokość i wysokość

Aby zmienić orientację strony, zamienimy wartości szerokości i wysokości. Ta zmiana spowoduje zmianę wymiarów strony:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Tutaj obliczamy nowe wymiary i zmieniamy położenie lewego dolnego rogu (`LLY`) odpowiednio.

## Krok 5: Zaktualizuj MediaBox i CropBox

Teraz, gdy mamy nowe wymiary, zastosujemy te zmiany do `MediaBox` I `CropBox` aby mieć pewność, że strona wyświetla się prawidłowo:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Krok 6: Obróć stronę

Aby sfinalizować zmianę orientacji, obrócimy stronę. Jest to proste dzięki Aspose.PDF:

```csharp
page.Rotate = Rotation.on90; // Obróć o 90 stopni
```

Ten wiersz skutecznie odwraca stronę do pożądanej orientacji.

## Krok 7: Zapisz plik wyjściowy PDF

Po zmianie orientacji wszystkich stron zapisz zaktualizowany dokument w nowym pliku:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Pamiętaj o podaniu nowej nazwy pliku, aby uniknąć nadpisania oryginalnego dokumentu.

## Wniosek

I gotowe! Zmiana orientacji strony w pliku PDF za pomocą Aspose.PDF dla platformy .NET to prosty proces. Ładując dokument, przewijając strony, aktualizując MediaBox i zapisując plik, możesz łatwo dostosować układ do swoich potrzeb. Niezależnie od tego, czy poprawiasz źle zeskanowany dokument, czy formatujesz strony do prezentacji, ten przewodnik pomoże Ci sprawnie wykonać zadanie.

## Najczęściej zadawane pytania

### Czy w pliku PDF mogę obracać konkretne strony zamiast wszystkich?  
Tak, możesz zmodyfikować pętlę, aby kierować ją na konkretne strony według ich indeksu, zamiast powtarzać ją po wszystkich stronach.

### Co to jest `MediaBox`?  
Ten `MediaBox` definiuje rozmiar i kształt strony w pliku PDF, decydując o miejscu umieszczenia treści.

### Czy Aspose.PDF dla .NET działa z innymi formatami plików?  
Tak, Aspose.PDF obsługuje różne formaty plików, w tym HTML, XML, XPS i inne.

### Czy istnieje bezpłatna wersja Aspose.PDF dla .NET?  
Tak, możesz zacząć od [bezpłatny okres próbny](https://releases.aspose.com/) lub poproś o [tymczasowa licencja](https://purchase.aspose.com/temporary-license/).

### Czy mogę cofnąć zapisane zmiany?  
Po zapisaniu dokumentu zmiany są trwałe. Zaleca się pracę na kopii lub zachowanie kopii zapasowej oryginalnego pliku.