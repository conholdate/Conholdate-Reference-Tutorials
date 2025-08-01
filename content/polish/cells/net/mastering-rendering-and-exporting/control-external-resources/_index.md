---
"description": "Uwolnij pełen potencjał konwersji plików Excel do PDF dzięki Aspose.Cells dla platformy .NET. W tym kompleksowym przewodniku dowiesz się, jak zarządzać zasobami zewnętrznymi, takimi jak obrazy, aby Twoje pliki PDF dokładnie odzwierciedlały Twoje wymagania dotyczące formatowania."
"linktitle": "Kontroluj zasoby zewnętrzne za pomocą Aspose.Cells dla .NET"
"second_title": "Aspose.Cells .NET API przetwarzania programu Excel"
"title": "Kontroluj zasoby zewnętrzne za pomocą Aspose.Cells dla .NET"
"url": "/pl/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## Wstęp

dzisiejszym cyfrowym świecie konwersja arkuszy kalkulacyjnych Excela do dokumentów PDF jest powszechnym i niezbędnym zadaniem. Niezależnie od tego, czy przygotowujesz raporty, dane finansowe, czy materiały prezentacyjne, kluczowe jest zapewnienie, że pliki PDF odzwierciedlają zamierzony format. Aspose.Cells for .NET oferuje potężną bibliotekę, która pozwala szczegółowo kontrolować proces konwersji, szczególnie w przypadku zasobów zewnętrznych, takich jak obrazy. W tym przewodniku dowiesz się, jak skutecznie zarządzać zasobami zewnętrznymi podczas konwersji Excela do PDF za pomocą Aspose.Cells. Zaczynajmy!

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz przygotowane następujące rzeczy:

1. Visual Studio lub dowolne środowisko IDE zgodne ze standardem .NET: To będzie Twoje środowisko programistyczne.
2. Aspose.Cells dla .NET: Jeśli jeszcze go nie zainstalowałeś, odwiedź stronę [Pobieranie Aspose](https://releases.aspose.com/cells/net/) stronę, aby pobrać najnowszą wersję.
3. Podstawowa znajomość języka C#: Znajomość języka C# będzie przydatna. Jeśli potrzebujesz wyjaśnień dotyczących jakichkolwiek pojęć, możesz je sprawdzić.
4. Przykładowy plik Excela: Przygotuj plik Excela, taki jak „samplePdfSaveOptions_StreamProvider.xlsx”, zawierający zasoby zewnętrzne, które chcesz przekonwertować.
5. Plik obrazu do testowania: Podczas konwersji użyj pliku obrazu, takiego jak „newPdfSaveOptions_StreamProvider.png”, jako zasobu zewnętrznego.

## Importuj niezbędne pakiety

Na początek musisz zaimportować wymagane przestrzenie nazw z biblioteki Aspose.Cells. Dodaj następujące dyrektywy using na początku pliku C#:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

Te przestrzenie nazw zapewniają podstawowe klasy i metody dla Twoich zadań.

## Krok 1: Utwórz klasę dostawcy strumienia

Najpierw utwórz klasę dostawcy strumienia, która implementuje `IStreamProvider` Interfejs. Ta klasa umożliwi Ci kontrolowanie sposobu ładowania zasobów zewnętrznych.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // Załaduj obraz do strumienia pamięci
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: Ta metoda jest wywoływana, gdy strumień jest zamykany; obecnie rejestrowany jest komunikat debugowania.
- InitStream: Ta metoda odczytuje zewnętrzny plik obrazu jako tablicę bajtów, konwertuje go na strumień pamięci i przypisuje do `options.Stream` nieruchomość.

## Krok 2: Skonfiguruj katalogi źródłowe i wyjściowe

Następnie zdefiniuj katalogi dla pliku Excel i wyjściowego pliku PDF.

```csharp
// Katalog źródłowy
string sourceDir = "Your Document Directory";
// Katalog wyjściowy
string outputDir = "Your Document Directory";
```

Zastępować `"Your Document Directory"` z rzeczywistą ścieżką w systemie, gdzie znajdują się Twoje pliki.

## Krok 3: Załaduj plik Excel

Teraz załaduj plik Excela, z którego chcesz utworzyć plik PDF.

```csharp
// Załaduj plik źródłowy Excel zawierający obrazy zewnętrzne
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

Ten `Workbook` Klasa Aspose.Cells reprezentuje plik Excel, który może zawierać różne zasoby zewnętrzne, np. obrazy.

## Krok 4: Ustaw opcje zapisywania pliku PDF

Przed zapisaniem skoroszytu w formacie PDF określ żądane opcje zapisu.

```csharp
// Określ opcje zapisu PDF – Dostawca strumienia
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // Zapisz każdy arkusz na nowej stronie
};
```

Tworzy to instancję `PdfSaveOptions`, co pozwala na dostosowanie formatu PDF. `OnePagePerSheet` opcja ta zapewnia, że każdy arkusz programu Excel będzie wyświetlany na osobnej stronie w końcowym pliku PDF.

## Krok 5: Przypisz swojego dostawcę strumieniowania

Połącz swoje `Workbook` instancja z `MyStreamProvider` klasa, którą utworzyłeś wcześniej.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

Ten wiersz zapewnia, że kiedykolwiek podczas konwersji napotkane zostaną zasoby zewnętrzne, Twój dostawca usług będzie nimi odpowiednio zarządzał.

## Krok 6: Zapisz skoroszyt jako plik PDF

Teraz zapisz skoroszyt programu Excel w formacie PDF.

```csharp
// Zapisz skoroszyt w formacie PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

Dzwoniąc do `Save` Metoda ta jest stosowana w obiekcie skoroszytu i przekazuje katalog wyjściowy wraz z opcjami PDF, umożliwiając konwersję pliku Excel do poprawnie sformatowanego pliku PDF.

## Krok 7: Potwierdź pomyślne wykonanie

Na koniec warto sprawdzić, czy proces zakończył się pomyślnie.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

Wiadomość ta poinformuje Cię o stanie Twojej operacji i zapewni Ci przydatne informacje zwrotne.

## Wniosek

Opanowałeś już proces kontrolowania zasobów zewnętrznych podczas konwersji plików Excel do PDF za pomocą Aspose.Cells! Postępując zgodnie z tymi krokami, możesz mieć pewność, że Twoje dokumenty będą zawierać dokładne obrazy i inne elementy zewnętrzne, co za każdym razem zapewni dopracowany produkt końcowy.

## Najczęściej zadawane pytania

### Czym jest Aspose.Cells?
Aspose.Cells to zaawansowana biblioteka dla programistów .NET umożliwiająca tworzenie, przetwarzanie, konwersję i renderowanie plików Excel w różnych formatach.

### Jak pobrać Aspose.Cells?
Najnowszą wersję można pobrać ze strony [Link do pobrania](https://releases.aspose.com/cells/net/).

### Czy mogę wypróbować Aspose.Cells za darmo?
Tak! Możesz uzyskać dostęp do bezpłatnego okresu próbnego, odwiedzając stronę [Bezpłatna strona próbna](https://releases.aspose.com/).

### Gdzie mogę znaleźć pomoc dotyczącą Aspose.Cells?
W przypadku pytań dotyczących pomocy technicznej odwiedź stronę [Forum wsparcia Aspose](https://forum.aspose.com/c/cells/9).

### Jak mogę uzyskać tymczasową licencję na Aspose.Cells?
Możesz ubiegać się o tymczasową licencję [Tutaj](https://purchase.aspose.com/temporary-license/).