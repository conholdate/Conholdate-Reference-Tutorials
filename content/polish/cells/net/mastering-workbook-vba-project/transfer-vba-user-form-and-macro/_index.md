---
"description": "Odkryj potencjał automatyzacji w programie Excel dzięki temu kompleksowemu przewodnikowi dotyczącemu przenoszenia formularzy użytkownika i makr VBA między skoroszytami za pomocą Aspose.Cells dla platformy .NET. Idealny zarówno dla początkujących, jak i doświadczonych programistów."
"linktitle": "Przenoszenie formularzy użytkownika i makr VBA między skoroszytami programu Excel"
"second_title": "Aspose.Cells .NET API przetwarzania programu Excel"
"title": "Przenoszenie formularzy użytkownika i makr VBA między skoroszytami programu Excel"
"url": "/pl/cells/net/mastering-workbook-vba-project/transfer-vba-user-form-and-macro/"
"weight": 11
---

## Wstęp

Witamy w kompleksowym przewodniku po udoskonalaniu pracy z programem Excel za pomocą makr VBA i formularzy użytkownika! W tym samouczku pokażemy, jak przenieść projektanta makr VBA UserForm z jednego skoroszytu do drugiego za pomocą potężnej biblioteki Aspose.Cells dla platformy .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku wyposaży Cię w wiedzę niezbędną do programistycznego zarządzania plikami Excela. Gotowy do działania? Zaczynajmy!

## Wymagania wstępne
Zanim przejdziemy do kodowania, upewnijmy się, że masz wszystko, czego potrzebujesz:

1. Środowisko programistyczne C#: środowisko pracy do programowania w języku C#, w którym zdecydowanie zaleca się korzystanie z programu Visual Studio.
2. Biblioteka Aspose.Cells dla .NET: Pamiętaj o zintegrowaniu biblioteki Aspose.Cells ze swoim projektem. Możesz to łatwo zrobić. [pobierz tutaj](https://releases.aspose.com/cells/net/).
3. Podstawowa wiedza na temat języka VBA i makr programu Excel: Znajomość języka VBA i sposobu działania makr programu Excel pomoże Ci lepiej zrozumieć ten samouczek.
4. Plik programu Excel z formularzem użytkownika: Utwórz lub uzyskaj skoroszyt programu Excel zawierający formularz użytkownika (najlepiej z włączonymi makrami, np. `.xlsm` akta).

## Importowanie wymaganych pakietów
Aby wykorzystać funkcjonalności udostępniane przez Aspose.Cells, należy dodać następujące przestrzenie nazw na początku pliku C#:

```csharp
using System;
using Aspose.Cells;
using Aspose.Cells.Vba;
```

Te przestrzenie nazw zapewnią Ci dostęp do potężnych narzędzi osadzonych w bibliotece Aspose.Cells.

## Krok 1: Zdefiniuj katalogi źródłowe i wyjściowe
Najpierw ustal lokalizację swoich plików:

```csharp
// Zdefiniuj katalogi źródłowe i wyjściowe
string sourceDir = @"Your\Source\Directory\";
string outputDir = @"Your\Output\Directory\";
```

Zastąp ścieżki zastępcze rzeczywistymi katalogami, w których przechowywane są Twoje pliki.

## Krok 2: Utwórz pusty skoroszyt docelowy
Następnie utwórz nowy skoroszyt, do którego skopiujesz formularz użytkownika i makra:

```csharp
// Utwórz pusty skoroszyt docelowy
Workbook target = new Workbook();
```

Spowoduje to utworzenie pustego skoroszytu, który będzie stanowił płótno dla przyszłego transferu danych.

## Krok 3: Załaduj skoroszyt szablonu
Załaduj skoroszyt zawierający formularz użytkownika i makra:

```csharp
// Załaduj plik Excel zawierający formularz użytkownika VBA-Macro Designer
Workbook templateFile = new Workbook(sourceDir + "sampleDesignerForm.xlsm");
```

Regulować `"sampleDesignerForm.xlsm"` do nazwy twojego rzeczywistego pliku.

## Krok 4: Kopiowanie arkuszy do skoroszytu docelowego
Teraz skopiujmy arkusze z szablonu do skoroszytu docelowego:

```csharp
// Skopiuj wszystkie arkusze szablonowe do skoroszytu docelowego
foreach (Worksheet ws in templateFile.Worksheets)
{
    if (ws.Type == SheetType.Worksheet)
    {
        Worksheet s = target.Worksheets.Add(ws.Name);
        s.Copy(ws);
        // Dodaj wiadomość w komórce A2 arkusza docelowego
        s.Cells["A2"].PutValue("VBA Macro and User Form copied from template to target.");
    }
}
```

Ten kod przechodzi przez każdy arkusz w szablonie i kopiuje go do skoroszytu docelowego, zapewniając bezproblemowe przesłanie wszystkich danych.

## Krok 5: Kopiowanie makr VBA z szablonu
Następnie skopiujemy makra VBA, w tym moduły UserForm Designer, do nowego skoroszytu:

```csharp
// Kopiuj formularz użytkownika VBA-Macro Designer z szablonu do celu
foreach (VbaModule vbaItem in templateFile.VbaProject.Modules)
{
    if (vbaItem.Name == "ThisWorkbook")
    {
        // Skopiuj kod modułu ThisWorkbook
        target.VbaProject.Modules["ThisWorkbook"].Codes = vbaItem.Codes;
    }
    else
    {
        // Kopiuj kod i dane innych modułów
        int vbaMod = target.VbaProject.Modules.Add(vbaItem.Type, vbaItem.Name);
        target.VbaProject.Modules[vbaMod].Codes = vbaItem.Codes;

        if (vbaItem.Type == VbaModuleType.Designer)
        {
            // Pobierz magazyn projektanta formularzy użytkownika
            byte[] designerStorage = templateFile.VbaProject.Modules.GetDesignerStorage(vbaItem.Name);
            // Dodaj magazyn projektanta do docelowego projektu VBA
            target.VbaProject.Modules.AddDesignerStorage(vbaItem.Name, designerStorage);
        }
    }
}
```

Ten kod zapewnia, że nie tylko kod, ale także projekt formularza użytkownika zostanie skopiowany, dzięki czemu funkcjonalność makr zostanie zachowana.

## Krok 6: Zapisz skoroszyt docelowy
Po zakończeniu kopiowania zapisz nowy skoroszyt:

```csharp
// Zapisz skoroszyt docelowy
target.Save(outputDir + "outputDesignerForm.xlsm", SaveFormat.Xlsm);
```

W razie potrzeby zmodyfikuj nazwę pliku wyjściowego. Ten krok tworzy spersonalizowany skoroszyt wypełniony makrami i formularzami użytkownika.

## Krok 7: Potwierdź powodzenie
Na koniec wyświetl na konsoli komunikat o powodzeniu operacji:

```csharp
Console.WriteLine("CopyVBAMacroUserFormDesignerStorageToWorkbook executed successfully.\r\n");
```

Ta prosta linijka daje ci pewność, że cały proces przebiegł bez zakłóceń — jest to niepodważalne potwierdzenie twojej ciężkiej pracy!

## Wniosek
Gratulacje! Udało Ci się z powodzeniem nauczyć kopiowania makra VBA User Form Designer z jednego skoroszytu do drugiego za pomocą Aspose.Cells dla .NET. Choć na początku może się to wydawać przytłaczające, praktyka pozwoli Ci biegle posługiwać się skoroszytami. Pamiętaj, że kodowanie to przede wszystkim eksperymentowanie, więc nie wahaj się odkrywać różnych funkcji w swoich plikach Excel. Jeśli masz jakiekolwiek pytania lub potrzebujesz pomocy, fora i dokumentacja Aspose to doskonałe źródła wsparcia.

## Najczęściej zadawane pytania

### Jakie wersje programu Excel obsługuje Aspose.Cells?
Aspose.Cells obsługuje różne formaty plików Excel, w tym XLSX, XLSM, CSV i inne.

### Czy mogę używać Aspose.Cells za darmo?
Tak! Możesz zacząć od bezpłatnego okresu próbnego, aby przetestować bibliotekę: [Bezpłatny okres próbny](https://releases.aspose.com/).

### Czy do uruchomienia tego kodu potrzebuję programu Visual Studio?
Chociaż zaleca się korzystanie z programu Visual Studio ze względu na jego przyjazne dla użytkownika funkcje, wystarczy dowolne środowisko IDE C# obsługujące programowanie .NET.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji?
Możesz odkryć [Dokumentacja Aspose.Cells](https://reference.aspose.com/cells/net/) aby zobaczyć więcej przykładów i szczegółowych wyjaśnień.

### Jak rozwiązywać problemy podczas korzystania z Aspose.Cells?
Powinieneś odwiedzić [Forum wsparcia Aspose](https://forum.aspose.com/c/cells/9) Aby uzyskać pomoc od społeczności i personelu pomocniczego Aspose.