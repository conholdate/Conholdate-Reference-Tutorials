---
"description": "Dowiedz się, jak tworzyć pięknie numerowane listy w dokumentach PDF za pomocą Aspose.PDF dla platformy .NET. Ten przewodnik przeprowadzi Cię przez proces stosowania różnych stylów numeracji, takich jak cyfry rzymskie."
"linktitle": "Stylowe listy numerowane przy użyciu Aspose.PDF dla .NET"
"second_title": "Aspose.PDF dla .NET API Reference"
"title": "Stylowe listy numerowane przy użyciu Aspose.PDF dla .NET"
"url": "/pl/net/programming-with-headings/stylish-numbered-lists/"
"weight": 10
---

## Wstęp

Czy kiedykolwiek potrzebowałeś utworzyć uporządkowane, numerowane listy w dokumentach PDF? Niezależnie od tego, czy chodzi o dokumenty prawne, raporty, czy prezentacje, skuteczne style numeracji są kluczowe dla uporządkowania treści. Dzięki Aspose.PDF dla .NET możesz łatwo stosować różne style numeracji do nagłówków w plikach PDF, co pozwala uzyskać dopracowane i profesjonalne dokumenty.

## Wymagania wstępne

Zanim przejdziemy do kodowania, upewnij się, że masz przygotowane następujące rzeczy:

1. Aspose.PDF dla .NET: Pobierz najnowszą wersję ze strony [Tutaj](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne: Będziesz potrzebować programu Visual Studio lub dowolnego środowiska IDE zgodnego z platformą .NET.
3. .NET Framework: Upewnij się, że masz zainstalowany .NET Framework 4.0 lub nowszy.
4. Licencja: Możesz użyć tymczasowej licencji z [Tutaj](https://purchase.aspose.com/temporary-license/) lub odkryj [bezpłatny okres próbny](https://releases.aspose.com/) opcje.

## Importowanie wymaganych pakietów

Zacznij od zaimportowania niezbędnych przestrzeni nazw do swojego projektu:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 1: Konfigurowanie dokumentu

Zacznijmy od utworzenia nowego dokumentu PDF i skonfigurowania jego układu, w tym rozmiaru strony i marginesów.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Ustaw wymiary i marginesy strony
pdfDoc.PageInfo.Width = 612.0; // 8,5 cala
pdfDoc.PageInfo.Height = 792.0; // 11 cali
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo(72, 72, 72, 72); // 1-calowe marginesy
```

Taka konfiguracja pozwala na uzyskanie dokumentu o standardowym rozmiarze Letter z jednocalowymi marginesami z każdej strony.

## Krok 2: Dodawanie strony do pliku PDF

Następnie dodamy pustą stronę do dokumentu PDF, na której później zastosujemy style numeracji.

```csharp
// Dodaj nową stronę do dokumentu PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo = pdfDoc.PageInfo; // Użyj tych samych ustawień co w dokumencie
```

## Krok 3: Tworzenie pola pływającego

FloatingBox pozwala na pozycjonowanie treści niezależnie od układu strony, zapewniając większą kontrolę nad jej układem.

```csharp
// Utwórz FloatingBox dla treści strukturalnej
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox
{
    Margin = pdfPage.PageInfo.Margin
};
pdfPage.Paragraphs.Add(floatBox);
```

## Krok 4: Dodawanie nagłówków z cyframi rzymskimi

Teraz dodajmy nasz pierwszy nagłówek, zapisując go małymi literami rzymskimi.

```csharp
// Utwórz pierwszy nagłówek za pomocą cyfr rzymskich
Aspose.Pdf.Heading heading1 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 1,
    Text = "List 1",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading1);
```

## Krok 5: Dodawanie drugiego nagłówka z niestandardowym numerem początkowym

Następnie dodamy drugi nagłówek, zaczynając od cyfry rzymskiej 13.

```csharp
// Utwórz drugi nagłówek zaczynający się od cyfry rzymskiej 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1)
{
    IsInList = true,
    StartNumber = 13,
    Text = "List 2",
    Style = NumberingStyle.NumeralsRomanLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading2);
```

## Krok 6: Dodawanie nagłówka z numeracją alfabetyczną

Dla urozmaicenia dodajmy trzeci nagłówek, wykorzystując numerację alfabetyczną małymi literami.

```csharp
// Utwórz nagłówek z numeracją alfabetyczną
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2)
{
    IsInList = true,
    StartNumber = 1,
    Text = "The value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed",
    Style = NumberingStyle.LettersLowercase,
    IsAutoSequence = true
};
floatBox.Paragraphs.Add(heading3);
```

## Krok 7: Zapisywanie pliku PDF

Na koniec zapisz plik PDF w wybranym katalogu.

```csharp
// Zapisz dokument PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine($"\nNumber style applied successfully in headings.\nFile saved at {dataDir}");
```

## Wniosek

Gratulacje! Udało Ci się zastosować różne style numeracji – cyfry rzymskie i alfabetyczne – do nagłówków w pliku PDF za pomocą Aspose.PDF dla platformy .NET. Elastyczność Aspose.PDF pozwala kontrolować układ strony, style numeracji i pozycjonowanie treści, umożliwiając tworzenie uporządkowanych i profesjonalnych dokumentów PDF.

## Najczęściej zadawane pytania

### Czy mogę zastosować różne style numeracji w tym samym dokumencie PDF?  
Tak, w tym samym dokumencie można mieszać różne style numeracji, takie jak cyfry rzymskie, cyfry arabskie i numeracja alfabetyczna.

### Jak mogę dostosować numer początkowy nagłówków?  
Możesz ustawić numer początkowy dla dowolnego nagłówka za pomocą `StartNumber` nieruchomość.

### Czy istnieje sposób na zresetowanie kolejności numeracji?  
Tak, możesz zresetować numerację, dostosowując `StartNumber` właściwość dla każdego nagłówka.

### Czy oprócz numerowania mogę zastosować pogrubienie lub kursywę w nagłówkach?  
Oczywiście! Możesz dostosować style nagłówków, modyfikując właściwości takie jak czcionka, rozmiar, pogrubienie i kursywa za pomocą `TextState` obiekt.

### Jak uzyskać tymczasową licencję na Aspose.PDF?  
Możesz uzyskać tymczasową licencję od [Tutaj](https://purchase.aspose.com/temporary-license/) aby przetestować Aspose.PDF bez ograniczeń.