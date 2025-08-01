---
"description": "Dowiedz się, jak bezproblemowo dodawać podpis cyfrowy do dokumentów Word za pomocą Aspose.Words for .NET. Ten kompleksowy samouczek obejmuje wszystko, od konfiguracji środowiska i wstawiania wiersza podpisu, po zapisywanie i weryfikację podpisanych dokumentów."
"linktitle": "Utwórz i podpisz nową linię podpisu"
"second_title": "API przetwarzania dokumentów Aspose.Words"
"title": "Utwórz i podpisz nową linię podpisu"
"url": "/pl/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## Wstęp

Chcesz dodać podpis cyfrowy do dokumentu Word? Z Aspose.Words dla .NET jest to prostsze, niż myślisz! Ten samouczek przeprowadzi Cię przez kroki konfiguracji środowiska, dodawania wiersza podpisu i cyfrowego podpisywania dokumentu. Zaczynajmy!

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnij się, że masz następujące elementy:

1. Aspose.Words dla .NET - [Pobierz tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne .NET — Visual Studio jest idealnym rozwiązaniem do tego zadania.
3. Dokument do podpisania — możesz utworzyć nowy dokument Word lub użyć istniejącego.
4. Plik certyfikatu - A `.pfx` plik jest niezbędny do składania podpisów cyfrowych.
5. Obraz linii podpisu (opcjonalnie) — Możesz dołączyć plik obrazu podpisu.

## Importuj wymagane przestrzenie nazw

Aby korzystać z funkcjonalności Aspose.Words, należy zaimportować następujące przestrzenie nazw:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Krok 1: Konfigurowanie katalogu dokumentów

Zacznij od zdefiniowania ścieżki do katalogu z dokumentami. To tutaj będziesz zapisywać i pobierać dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Określ ścieżkę do katalogu dokumentów
```

## Krok 2: Tworzenie nowego dokumentu

Następnie utwórzmy nowy dokument Worda. Będzie on stanowił podstawę dla Twojego podpisu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstawianie linii podpisu

Teraz użyj `DocumentBuilder` klasa umożliwiająca wstawienie linii podpisu do dokumentu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Krok 4: Zapisywanie dokumentu

Po wstawieniu linii podpisu zapisz dokument. To kluczowy krok przed złożeniem podpisu.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Krok 5: Konfigurowanie opcji podpisywania

Skonfiguruj opcje procesu podpisywania. Obejmuje to określenie identyfikatora wiersza podpisu i opcjonalnego obrazu wyświetlanego z podpisem.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // Ścieżka do Twojego obrazu
};
```

## Krok 6: Ładowanie certyfikatu

Załaduj plik certyfikatu wymagany do podpisania dokumentu:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // Zmień nazwę pliku i hasło
```

## Krok 7: Podpisanie dokumentu

Na koniec podpisz dokument za pomocą `DigitalSignatureUtil` Klasa. Zapisz podpisany dokument pod nową nazwą, aby móc do niego wrócić w przyszłości.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## Wniosek

Gratulacje! Udało Ci się utworzyć dokument Word, dodać wiersz podpisu i podpisać go cyfrowo za pomocą Aspose.Words for .NET. To potężne narzędzie upraszcza automatyzację dokumentów, zapewniając bezpieczne podpisywanie i uwierzytelnianie umów i dokumentów formalnych.

## Najczęściej zadawane pytania

### Czy mogę użyć innych formatów obrazu w podpisie?

Tak, możesz używać różnych formatów obrazów, w tym PNG, JPG i BMP.

### Czy konieczne jest użycie `.pfx` złożyć wniosek o certyfikat?

Tak, a `.pfx` Plik jest standardowym formatem przechowywania certyfikatów i kluczy prywatnych do podpisów cyfrowych.

### Czy mogę dodać wiele wierszy podpisu w jednym dokumencie?

Oczywiście! Możesz wstawić wiele wierszy podpisu, powtarzając krok wstawiania w razie potrzeby.

### Co zrobić, jeśli nie mam certyfikatu cyfrowego?

Będziesz musiał uzyskać certyfikat cyfrowy od zaufanego urzędu certyfikacji lub wygenerować go przy użyciu narzędzi typu OpenSSL.

### Jak zweryfikować podpis cyfrowy w dokumencie?

Możesz zweryfikować podpis cyfrowy, otwierając podpisany dokument w programie Word i sprawdzając szczegóły podpisu, aby potwierdzić jego autentyczność i integralność.