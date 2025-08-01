---
"description": "Dowiedz się, jak tworzyć i dostosowywać prymitywne modele 3D, w tym prostopadłościany i cylindry, a następnie bez trudu zapisywać je w formacie FBX."
"linktitle": "Twórz prymitywne modelowanie 3D"
"second_title": "Aspose.3D .NET API"
"title": "Twórz prymitywne modelowanie 3D"
"url": "/pl/3d/net/guide-to-3d-modeling/create-primitive-3d-modeling/"
"weight": 10
---

## Wstęp

Witamy w immersyjnym świecie modelowania 3D z wykorzystaniem Aspose.3D dla .NET! W tym kompleksowym samouczku krok po kroku przeprowadzimy Cię przez proces tworzenia prymitywnych modeli 3D. Niezależnie od tego, czy jesteś doświadczonym programistą, czy początkującym, który chce się czegoś nauczyć, ten przewodnik pomoże Ci tworzyć wizualnie oszałamiające elementy 3D do Twoich projektów.

## Wymagania wstępne

Zanim zaczniesz zajmować się modelowaniem 3D, upewnij się, że spełnione są następujące warunki wstępne:

- Aspose.3D dla .NET: Pobierz i zainstaluj bibliotekę Aspose.3D dla .NET z [strona pobierania](https://releases.aspose.com/3d/net/).
  
- Środowisko programistyczne .NET: skonfiguruj środowisko zgodne z Aspose.3D, np. Visual Studio.

Mając wszystko przygotowane, możemy rozpocząć naszą przygodę z modelowaniem 3D!

## Importowanie wymaganych przestrzeni nazw

Zacznij od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.3D:

```csharp
using System;
using System.IO;
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
```

Te przestrzenie nazw zapewnią Ci narzędzia niezbędne do manipulowania modelami 3D i zapisywania Twoich kreacji.

## Krok 1: Zainicjuj obiekt sceny

Utwórz nowy obiekt sceny, który będzie pełnił funkcję płótna dla Twoich modeli 3D:

```csharp
// Zainicjuj obiekt sceny
Scene scene = new Scene();
```

Ta scena będzie zawierać prymitywne kształty, które zamierzasz utworzyć.

## Krok 2: Utwórz model pudełkowy

Następnie dodajmy model pudełkowy do sceny:

```csharp
// Utwórz model pudełkowy
scene.RootNode.CreateChildNode("box", new Box());
```

Możesz dostosować wymiary i właściwości pudełka do swojej kreatywnej wizji.

## Krok 3: Utwórz model cylindra

Teraz ulepsz swoją scenę, dodając cylinder:

```csharp
// Utwórz model cylindra
scene.RootNode.CreateChildNode("cylinder", new Cylinder());
```

Podobnie jak w przypadku pudełka, możesz swobodnie dostosować parametry cylindra, aby uzyskać pożądany wygląd.

## Krok 4: Zapisz scenę w formacie FBX

Aby zachować model 3D, zapisz go w formacie FBX:

```csharp
// Zapisz rysunek w formacie FBX
var output = Path.Combine("Your Output Directory", "test.fbx");
scene.Save(output, FileFormat.FBX7500ASCII);
```

Upewnij się, że wybrałeś właściwy katalog wyjściowy i nazwę pliku dla swojego modelu.

## Krok 5: Wyświetl komunikat o powodzeniu

Na koniec uczcij swój sukces, wyświetlając wiadomość:

```csharp
// Wyświetl komunikat o powodzeniu
Console.WriteLine($"\nBuilding a scene from primitive 3D models was successful.\nFile saved at {output}");
```

Twoja scena 3D złożona z modeli pierwotnych jest teraz ukończona i zapisana!

## Wniosek

Gratulacje! Udało Ci się stworzyć zachwycające modele 3D z wykorzystaniem Aspose.3D dla .NET! W tym samouczku omówiono podstawy modelowania prymitywnego, ale możliwości są nieograniczone. Dowiedz się więcej o zaawansowanych funkcjach i technikach w… [dokumentacja](https://reference.aspose.com/3d/net/).

## Najczęściej zadawane pytania

### Czy mogę używać Aspose.3D dla .NET z innymi językami programowania niż .NET?

Aspose.3D obsługuje głównie platformę .NET, ale dostępne są wersje dla Javy i innych platform.

### Czy jest dostępna bezpłatna wersja próbna?

Tak, możesz wypróbować możliwości Aspose.3D za pomocą [bezpłatny okres próbny](https://releases.aspose.com/).

### Gdzie mogę znaleźć pomoc techniczną dotyczącą Aspose.3D dla .NET?

Aby uzyskać wsparcie społeczności, odwiedź stronę [Forum Aspose.3D](https://forum.aspose.com/c/3d/18).

### Jak mogę uzyskać tymczasową licencję?

Możesz poprosić o tymczasową licencję [Tutaj](https://purchase.conholdate.com/temporary-license/).

### Czy są dostępne dodatkowe samouczki?

Tak! Więcej samouczków i przykładów znajdziesz w [dokumentacja](https://reference.aspose.com/3d/net/).