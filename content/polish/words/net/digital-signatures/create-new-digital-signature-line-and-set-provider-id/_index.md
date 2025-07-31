---
"description": "Dowiedz się, jak programowo dodawać linie podpisu do dokumentów Word za pomocą Aspose.Words dla platformy .NET. Ten kompleksowy przewodnik obejmuje wszystko, od konfiguracji środowiska programistycznego po wstawianie linii podpisu i bezpieczne podpisywanie dokumentów."
"linktitle": "Utwórz nową linię podpisu cyfrowego i ustaw identyfikator dostawcy"
"second_title": "API przetwarzania dokumentów Aspose.Words"
"title": "Utwórz nową linię podpisu cyfrowego i ustaw identyfikator dostawcy"
"url": "/pl/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Wstęp

Witajcie, entuzjaści technologii! Czy chcieliście kiedyś zautomatyzować dodawanie linii podpisu do dokumentów Word? Dziś pokażemy, jak to zrobić za pomocą Aspose.Words dla .NET. Ten przewodnik krok po kroku przeprowadzi Was przez proces tworzenia linii podpisu i ustawiania identyfikatora dostawcy, dzięki czemu przetwarzanie dokumentów będzie bardziej wydajne i usprawnione.

## Wymagania wstępne

Zanim przejdziemy dalej, upewnijmy się, że wszystko jest skonfigurowane:

1. Aspose.Words dla .NET: Jeśli jeszcze go nie zainstalowałeś, pobierz go [Tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Użyj programu Visual Studio lub dowolnego środowiska programistycznego C#.
3. .NET Framework: Upewnij się, że na Twoim komputerze jest zainstalowany .NET Framework.
4. Certyfikat PFX: Do podpisywania dokumentów potrzebny jest certyfikat PFX, który można uzyskać od zaufanego urzędu certyfikacji.

## Importowanie niezbędnych przestrzeni nazw

Aby rozpocząć, zaimportuj wymagane przestrzenie nazw do swojego projektu C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Przyjrzyjmy się teraz szczegółom tworzenia nowego wiersza podpisu i ustawiania identyfikatora dostawcy.

## Krok 1: Utwórz nowy dokument

Najpierw musimy utworzyć nowy dokument Word, który będzie stanowił podstawę naszego podpisu:

```csharp
// Podaj ścieżkę do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Tutaj inicjujemy nowy `Document` i `DocumentBuilder`, co pozwala nam na łatwe dodawanie elementów.

## Krok 2: Zdefiniuj opcje linii podpisu

Następnie zdefiniujemy opcje dla naszego podpisu, obejmujące imię i nazwisko osoby podpisującej, jej stanowisko, adres e-mail i inne istotne szczegóły:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Opcje te pomagają spersonalizować linię podpisu, czyniąc ją czytelną i profesjonalną.

## Krok 3: Wstaw linię podpisu

Mając już przygotowane opcje, możemy wstawić linię podpisu do dokumentu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Ten `InsertSignatureLine` Metoda dodaje linię podpisu i przypisujemy jej unikalny identyfikator dostawcy.

## Krok 4: Zapisz dokument

Po wstawieniu wiersza podpisu zapiszmy dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Dokument zostanie zapisany z nowo dodaną linią podpisu.

## Krok 5: Skonfiguruj opcje podpisywania

Teraz skonfigurujemy opcje podpisywania, w tym identyfikator wiersza podpisu, identyfikator dostawcy, komentarze i czas podpisu:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Ustawienia te zapewniają, że dokument zostanie podpisany przy użyciu prawidłowych danych.

## Krok 6: Utwórz posiadacza certyfikatu

Aby podpisać dokument, musimy utworzyć posiadacza certyfikatu, korzystając z certyfikatu PFX:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Zastępować `"morzal.pfx"` z rzeczywistą nazwą pliku certyfikatu i `"aw"` z hasłem certyfikatu.

## Krok 7: Podpisz dokument

Na koniec podpiszemy dokument za pomocą narzędzia podpisu cyfrowego:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Ten proces powoduje podpisanie dokumentu i zapisanie go jako nowego pliku.

## Wniosek

Gratulacje! Udało Ci się utworzyć linię podpisu i ustawić identyfikator dostawcy w dokumencie Word za pomocą Aspose.Words dla .NET. Ta potężna biblioteka upraszcza zadania związane z przetwarzaniem dokumentów, usprawniając Twój przepływ pracy. Wypróbuj ją i przekonaj się, jak może usprawnić Twoje projekty!

## Najczęściej zadawane pytania

### Czy mogę dostosować wygląd linii podpisu?
Oczywiście! Możesz dostosować różne opcje w `SignatureLineOptions` aby dopasować się do Twojego stylu i wymagań.

### Co zrobić, jeśli nie mam certyfikatu PFX?
Aby móc cyfrowo podpisywać dokumenty, musisz uzyskać certyfikat od zaufanego urzędu certyfikacji.

### Czy mogę dodać do dokumentu wiele wierszy podpisu?
Tak, możesz dodać wiele wierszy podpisu, powtarzając proces wstawiania z różnymi opcjami.

### Czy Aspose.Words dla .NET jest zgodny z .NET Core?
Tak, Aspose.Words for .NET obsługuje .NET Core, co czyni go wszechstronnym rozwiązaniem dla różnych środowisk programistycznych.

### Jak bezpieczne są podpisy cyfrowe?
Podpisy cyfrowe tworzone za pomocą Aspose.Words są bardzo bezpieczne, pod warunkiem, że używasz ważnego i zaufanego certyfikatu.