---
"description": "Dowiedz się, jak skutecznie konwertować układy CAD do różnych formatów obrazów rastrowych za pomocą Aspose.CAD dla .NET. Ten kompleksowy przewodnik przeprowadzi Cię przez ten proces za pomocą przejrzystego kodu."
"linktitle": "Eksportuj CAD do konwersji obrazu rastrowego"
"second_title": "Aspose.CAD .NET — format pliku CAD i BIM"
"title": "Eksportowanie konwersji CAD do obrazu rastrowego za pomocą Aspose.CAD dla .NET"
"url": "/pl/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## Wstęp

Chcesz bezproblemowo konwertować układy CAD do formatów rastrowych za pomocą Aspose.CAD dla .NET? Ten przewodnik krok po kroku pomoże Ci w tym procesie, a zwięzłe fragmenty kodu ułatwią Ci pracę. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek dostarczy Ci cennych wskazówek na każdym poziomie zaawansowania.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Biblioteka Aspose.CAD dla platformy .NET: Pobierz i zainstaluj bibliotekę ze strony [Strona internetowa Aspose.CAD](https://releases.aspose.com/cad/net/).
- Plik rysunku CAD: Przygotuj plik rysunku CAD (np. `conic_pyramid.dxf`) gotowe do konwersji.

## Importuj wymagane przestrzenie nazw

W swoim projekcie .NET musisz zaimportować niezbędne przestrzenie nazw, aby korzystać z funkcji Aspose.CAD. Dodaj poniższy kod na początku kodu:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Krok 1: Załaduj swój rysunek CAD

Najpierw określ katalog i załaduj plik CAD do instancji obrazu:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// Załaduj rysunek CAD
using (var image = Image.Load(sourceFilePath))
{
    // Przejdź do następnych kroków
}
```

## Krok 2: Utwórz opcje rasteryzacji

Następnie należy skonfigurować opcje rasteryzacji, definiując żądane wymiary obrazu wyjściowego:

```csharp
// Zainicjuj opcje rastrowania CadRasterizationOptions
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## Krok 3: Określ warstwy do konwersji

Jeśli chcesz przekonwertować konkretne warstwy, dodaj je do opcji rasteryzacji:

```csharp
// Określ warstwę do konwersji
rasterizationOptions.Layers = new [] { "LayerA" };
```

## Krok 4: Skonfiguruj opcje eksportu JPEG

Teraz utwórz opcje formatu obrazu, do którego chcesz eksportować (w tym przypadku JPEG):

```csharp
// Utwórz opcje Jpeg do eksportowania
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Krok 5: Eksport do formatu JPEG

Na koniec zapisz przekonwertowany obraz:

```csharp
// Zdefiniuj ścieżkę do pliku wyjściowego i zapisz obraz
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## Dodatkowa funkcja: Konwertuj wszystkie warstwy

Aby przekonwertować wszystkie warstwy na rysunku CAD, możesz zastosować następującą metodę:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // Przechodź przez warstwy i zapisuj każdą z nich jako osobny plik JPEG
    // Twój kod implementacji tutaj
}
```

## Wniosek

Gratulacje! Nauczyłeś się, jak skutecznie konwertować układy CAD do formatów rastrowych za pomocą Aspose.CAD dla .NET. Ten przewodnik oferuje proste podejście, odpowiednie dla programistów dążących do wydajnej konwersji CAD.

## Najczęściej zadawane pytania

### Czy mogę eksportować do innych formatów obrazów?

Oczywiście! Po prostu zamień `JpegOptions` z innymi opcjami formatu, takimi jak `PngOptions` Lub `BmpOptions`, w zależności od Twoich potrzeb.

### Czy jest dostępna wersja próbna?

Tak, możesz pobrać wersję próbną, aby zapoznać się z funkcjonalnością, postępując zgodnie z tą instrukcją [połączyć](https://releases.aspose.com/cad/net/).

### Gdzie mogę znaleźć pomoc dotyczącą Aspose.CAD?

Aby uzyskać wsparcie społeczności, sprawdź Aspose.CAD [forum](https://forum.aspose.com/c/cad/19)lub rozważ zakup licencji, aby uzyskać bardziej dedykowaną pomoc.

### Czy możliwe są licencje tymczasowe?

Tak, dostępne są licencje tymczasowe. Możesz o nie poprosić [Tutaj](https://purchase.conholdate.com/temporary-license/).

### Gdzie mogę uzyskać dostęp do szczegółowej dokumentacji?

Odwiedź kompleksową dokumentację [Tutaj](https://reference.aspose.com/cad/net/) Aby uzyskać więcej informacji.