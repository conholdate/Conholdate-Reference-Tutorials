---
"description": "Dowiedz się, jak zmieniać czcionki podczas konwersji MHT za pomocą Aspose.Email dla .NET. Skorzystaj z tego przewodnika krok po kroku, aby łatwo dostosować ustawienia."
"linktitle": "Zmiana personalizacji czcionki MHT za pomocą języka C#"
"second_title": "Aspose.Email .NET API przetwarzania wiadomości e-mail"
"title": "Zmiana personalizacji czcionki MHT za pomocą języka C#"
"url": "/pl/email/net/mastering-email-header-manipulation/changing-mht-font-customization/"
"weight": 11
---

## Wstęp

świecie komunikacji internetowej pliki MHT (MHTML) to poręczny sposób przechowywania i udostępniania treści internetowych, wraz z obrazami, linkami i stylami. Ale co się stanie, gdy trzeba udoskonalić te pliki MHT, zmieniając czcionki? Dzięki Aspose.Email dla .NET zadanie to staje się banalnie proste. W tym samouczku krok po kroku przeprowadzimy Cię przez proces zmiany czcionek podczas konwersji MHT. Niezależnie od tego, czy tworzysz aplikację obsługującą formatowanie wiadomości e-mail, czy po prostu chcesz dostosować dokumenty do potrzeb swojej firmy, ten przewodnik wyposaży Cię w niezbędną wiedzę.

## Wymagania wstępne

Zanim zagłębisz się w kod, powinieneś przygotować kilka podstawowych rzeczy:

1. Visual Studio: Do pracy nad projektem C# potrzebne będzie zintegrowane środowisko programistyczne (IDE).
2. Biblioteka Aspose.Email dla .NET: Upewnij się, że biblioteka jest zainstalowana. Możesz ją pobrać ze strony [połączyć](https://releases.aspose.com/email/net/).
3. .NET Framework: Twój projekt powinien być zgodny z platformą .NET Framework; zazwyczaj dobrze sprawdza się platforma .NET Core lub nowsze wersje.

Masz już wszystko w kolejce? Super! Zaczynajmy.

## Importowanie pakietów

Przede wszystkim upewnij się, że Twój projekt jest skonfigurowany do korzystania z niezbędnych przestrzeni nazw. Na początku pliku C# umieść następujący kod:

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Tools;
```

Pakiety te zapewnią Ci dostęp do funkcjonalności niezbędnych do pracy z plikami MHT i modyfikacji ich zawartości.

Przyjrzyjmy się teraz krokom związanym ze zmianą czcionek podczas konwersji MHT.

## Krok 1: Załaduj plik MHT

Pierwszą rzeczą, którą musisz zrobić, jest załadowanie pliku MHT do `MailMessage` obiekt. W tym miejscu możesz uzyskać dostęp do jego zawartości i nią manipulować.

```csharp
MailMessage message = MailMessage.Load("input.mht", new MhtmlLoadOptions());
```

Wyjaśnienie: Tutaj, `"input.mht"` to ścieżka do pliku MHT. `MhtmlLoadOptions()` umożliwia skonfigurowanie sposobu ładowania pliku, np. innego sposobu obsługi załączników lub zasobów połączonych.

## Krok 2: Przejrzyj widoki alternatywne

Pliki MHT często mają wiele alternatywnych widoków, zwłaszcza jeśli zawierają treść HTML. Należy przejrzeć te widoki, aby znaleźć ten, który chcesz zmodyfikować.

```csharp
foreach (var alternateView in message.AlternateViews)
{
    if (alternateView.ContentType.MediaType == "text/html")
    {
        var htmlView = (AlternateView)alternateView;
        var linkedResources = htmlView.LinkedResources;
```

Wyjaśnienie: Sprawdzasz każdy `AlternateView` aby sprawdzić, czy jest to typ HTML. Jeśli tak, możesz uzyskać dostęp `LinkedResources`, w którym zwykle przechowywane są wszystkie czcionki powiązane z kodem HTML.

## Krok 3: Zidentyfikuj i dostosuj czcionki

Mając teraz dostęp do powiązanych zasobów, możesz zidentyfikować, które zasoby są czcionkami i dostosować je według potrzeb.

```csharp
foreach (var linkedResource in linkedResources)
{
    if (linkedResource.ContentType.MediaType == "application/x-font-ttf")
    {
        linkedResource.ContentType.Name = "Arial";  // Zmień na żądaną czcionkę
        linkedResource.TransferEncoding = TransferEncoding.Base64;  // Upewnij się, że jest poprawnie zakodowany
    }
}
```

Wyjaśnienie: Ta pętla sprawdza, czy typem zawartości powiązanego zasobu jest czcionka TrueType. Jeśli pasuje, możesz zmienić nazwę czcionki na dowolną (np. „Arial” w tym przykładzie). `TransferEncoding` należy również ustawić tak, aby zapewnić prawidłowe kodowanie danych dotyczących czcionek podczas zapisywania dokumentu.

## Krok 4: Zapisz zaktualizowany plik MHT

Po dostosowaniu czcionek nadszedł czas na zapisanie zmodyfikowanego pliku MHT. Upewnij się, że używasz prawidłowych opcji zapisu, aby zachować integralność pliku.

```csharp
message.Save("output.mht", SaveOptions.DefaultMhtml);
```

Wyjaśnienie: W tym wierszu kodu, `"output.mht"` to nazwa pliku, w którym chcesz zapisać zaktualizowaną zawartość. Używając `SaveOptions.DefaultMhtml` zapewnia, że nowy plik zachowa format MHT.

## Wniosek

Zmiana czcionek w plikach MHT może znacząco poprawić wygląd dokumentów. Wykorzystując Aspose.Email dla .NET, możesz łatwo wczytywać pliki MHT, modyfikować ich zawartość i zapisywać zmiany za pomocą zaledwie kilku linijek kodu. Niezależnie od tego, czy pracujesz nad osobistym projektem, czy nad większą aplikacją, opanowanie tych umiejętności może poprawić sposób prezentacji informacji.

## Najczęściej zadawane pytania

### Czym jest format MHT?
MHT to format archiwum stron internetowych, który przechowuje dokumenty HTML, obrazy i inne zasoby w jednym pliku.

### Czy mogę zmienić inne aspekty plików MHT za pomocą Aspose?
Oczywiście! Aspose.Email pozwala modyfikować niemal każdy aspekt plików MHT, w tym załączniki, nagłówki i wiele innych.

### Czy Aspose.Email dla .NET jest darmowy?
Aspose oferuje darmowy okres próbny, ale pełna wersja wymaga licencji. Licencję tymczasową można uzyskać tutaj. [Tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Email?
Pełną dokumentację i przykłady znajdziesz tutaj [Strona dokumentacji Aspose Email](https://reference.aspose.com/email/net/).

### Co zrobić, jeśli podczas korzystania z Aspose napotkam problemy?
Jeśli napotkasz jakiekolwiek problemy, możesz skontaktować się z pomocą techniczną na [Forum wsparcia Aspose](https://forum.aspose.com/c/email/12/).