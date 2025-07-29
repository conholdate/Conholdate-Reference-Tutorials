---
"description": "Dowiedz się, jak efektywnie kopiować dane w skoroszycie programu Excel za pomocą Aspose.Cells dla platformy .NET. Skorzystaj z tego przewodnika krok po kroku, aby łatwo duplikować arkusze, przesyłać dane i zarządzać plikami programu Excel."
"linktitle": "Kopiowanie danych w skoroszycie programu Excel za pomocą Aspose.Cells dla platformy .NET"
"second_title": "Aspose.Cells .NET API przetwarzania programu Excel"
"title": "Kopiowanie danych w skoroszycie programu Excel za pomocą Aspose.Cells dla platformy .NET"
"url": "/pl/cells/net/mastering-worksheet-value-operations/copy-data-within-excel-workbook/"
"weight": 12
---

## Wstęp

W tym szczegółowym przewodniku pokażemy, jak kopiować dane w obrębie tego samego skoroszytu za pomocą Aspose.Cells dla platformy .NET. Postępując zgodnie z poniższymi instrukcjami krok po kroku, dowiesz się, jak programowo duplikować arkusze, zachowując ich zawartość i formatowanie.

## Wymagania wstępne dotyczące kopiowania danych w programie Excel za pomocą Aspose.Cells

Zanim rozpoczniesz kodowanie, upewnij się, że wszystko masz przygotowane:

1. Biblioteka Aspose.Cells dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.Cells dla .NET. Najnowszą wersję możesz pobrać ze strony [Strona pobierania Aspose.Cells dla .NET](https://releases.aspose.com/cells/net/).
2. Środowisko programistyczne: Do pisania i uruchamiania kodu potrzebne jest środowisko IDE zgodne z platformą .NET, np. Visual Studio.
3. Licencja Aspose: Możesz skorzystać z bezpłatnej wersji próbnej lub wykupić licencję. Aby uzyskać więcej informacji, odwiedź stronę [Tutaj](https://purchase.aspose.com/temporary-license/).

Gdy wymagania wstępne zostaną spełnione, będziesz gotowy rozpocząć pracę z biblioteką.

## Importowanie wymaganych pakietów

Na początek musisz zaimportować odpowiednie przestrzenie nazw z Aspose.Cells. Umożliwi to pracę z plikami Excela z wykorzystaniem klas i metod udostępnianych przez Aspose.Cells.

```csharp
using System.IO;
using Aspose.Cells;
using System;
```

Te przestrzenie nazw zapewnią Ci dostęp do `Workbook` klasa (do pracy z plikami Excel) i `WorksheetCollection` (do dostępu do wielu arkuszy w skoroszycie).

## Krok 1: Zainicjuj ścieżki plików dla skoroszytu

Aby zachować porządek w kodzie, konieczne jest zdefiniowanie ścieżek do plików, w których znajduje się skoroszyt i w których chcesz zapisać zmodyfikowany plik. Oto jak możesz określić ścieżki:

```csharp
// Zdefiniuj ścieżkę katalogu, w którym znajduje się plik Excel.
string dataDir = "Your Directory Path";

// Zdefiniuj pełną ścieżkę do skoroszytu wejściowego.
string inputPath = dataDir + "book1.xls";
```

Zastępować `"Your Directory Path"` rzeczywistą ścieżką do katalogu zawierającego skoroszyt. Pomaga to zapewnić elastyczność kodu i efektywne zarządzanie ścieżkami.

## Krok 2: Otwórz skoroszyt, aby uzyskać dostęp do danych

Teraz, gdy ścieżki plików są ustawione, następnym krokiem jest załadowanie skoroszytu programu Excel do `Workbook` obiekt. Dzięki temu możesz uzyskać dostęp do jego zawartości i manipulować nią.

```csharp
// Załaduj plik Excela do obiektu Skoroszyt.
Workbook wb = new Workbook(inputPath);
```

Dzięki temu wierszowi udało Ci się pomyślnie załadować `book1.xls` do `wb` obiekt, udostępniając jego dane.

## Krok 3: Uzyskaj dostęp do kolekcji arkuszy roboczych

Po załadowaniu skoroszytu można uzyskać dostęp do zawartych w nim arkuszy. Aspose.Cells zapewnia `Worksheets` kolekcja umożliwiająca interakcję z każdym arkuszem w skoroszycie.

```csharp
// Pobierz kolekcję arkuszy roboczych ze skoroszytu.
WorksheetCollection sheets = wb.Worksheets;
```

Ten `sheets` obiekt zapewnia teraz dostęp do wszystkich arkuszy roboczych w nim zawartych `book1.xls`i można na nich wykonywać różne operacje, m.in. kopiować dane z jednego arkusza do drugiego.

## Krok 4: Kopiowanie danych z jednego arkusza do drugiego

Aby skopiować dane z jednego arkusza kalkulacyjnego do drugiego w ramach tego samego skoroszytu, Aspose.Cells oferuje łatwą w użyciu metodę o nazwie `AddCopy`Ta metoda tworzy duplikat określonego arkusza kalkulacyjnego i dołącza go do skoroszytu.

```csharp
// Skopiuj dane z „Arkusza1” do nowego arkusza w skoroszycie.
sheets.AddCopy("Sheet1");
```

W tym przykładzie kopiujemy dane z „Arkusza1” do nowego arkusza. `AddCopy` Metoda ta zduplikuje cały arkusz, zachowując całą jego zawartość, łącznie z formułami, formatowaniem i wartościami.

## Krok 5: Zapisz zmodyfikowany skoroszyt

Po skopiowaniu danych możesz zapisać zmodyfikowany skoroszyt pod nową nazwą lub w nowej lokalizacji. Można to zrobić, wywołując `Save` metoda na `Workbook` obiekt.

```csharp
// Zapisz zmodyfikowany skoroszyt pod nową nazwą.
wb.Save(dataDir + "book1_copy.xls");
```

Spowoduje to zapisanie skoroszytu ze skopiowanym arkuszem jako `book1_copy.xls` w określonym katalogu. Możesz zmienić nazwę pliku i ścieżkę dostępu według własnych potrzeb.

## Wniosek

Kopiowanie danych w skoroszycie programu Excel za pomocą Aspose.Cells dla platformy .NET to proste zadanie, a ten przewodnik zawiera instrukcje niezbędne do jego efektywnego wykonania. Niezależnie od tego, czy duplikujesz całe arkusze, czy konkretne zakresy danych, Aspose.Cells oferuje solidne i elastyczne API, które sprawia, że automatyzacja w programie Excel jest prosta i efektywna.

## Najczęściej zadawane pytania

### Czy mogę kopiować wiele arkuszy jednocześnie?

Aspose.Cells nie obsługuje kopiowania wielu arkuszy w jednym wywołaniu. Możesz jednak przejść przez arkusze, które chcesz skopiować, i skopiować je pojedynczo.

### Jak mogę zmienić nazwę skopiowanego arkusza?

Po skopiowaniu arkusza możesz zmienić jego nazwę w następujący sposób:

```csharp
sheets[sheets.Count - 1].Name = "NewSheetName";
```

### Czy Aspose.Cells jest kompatybilny z .NET Core?

Tak, Aspose.Cells jest w pełni kompatybilny ze środowiskami .NET Framework i .NET Core.

### W jaki sposób Aspose.Cells obsługuje formatowanie podczas kopiowania?

Ten `AddCopy` Metoda ta zachowuje całą zawartość i formatowanie podczas kopiowania arkuszy, zapewniając, że skopiowane dane wyglądają identycznie jak oryginał.

### Czy mogę skopiować arkusz do innego skoroszytu?

Tak, możesz skopiować arkusz do innego skoroszytu, używając `Copy` metoda z odwołaniem do skoroszytu docelowego.

```csharp
sheets.Add().Copy(wb.Worksheets["Sheet1"]);
```