---
"description": "Aspose.PDF for .NET을 사용하여 PDF 파일의 페이지 방향을 쉽게 조정하는 방법을 알아보세요. 이 단계별 가이드는 문서 로드, 회전 및 저장에 대한 명확한 지침을 제공합니다."
"linktitle": "PDF 페이지 방향 변경"
"second_title": ".NET API 참조용 Aspose.PDF"
"title": "PDF 페이지 방향 변경"
"url": "/ko/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## 소개

PDF 파일의 페이지 방향이 완전히 잘못된 것을 본 적이 있으신가요? 잘못 스캔된 문서든, 단순히 레이아웃을 바꿔야 하는 문서든, 방향을 조정하면 큰 변화를 가져올 수 있습니다. 다행히 Aspose.PDF for .NET은 페이지 방향 변경을 포함하여 PDF 파일을 조작할 수 있는 강력하고 사용자 친화적인 방법을 제공합니다. 이 가이드에서는 세로 모드에서 가로 모드로, 또는 가로 모드에서 세로 모드로 전환하는 과정을 단계별로 안내해 드립니다.

## 필수 조건

자세한 내용을 살펴보기 전에 다음 사항이 준비되었는지 확인하세요.

- .NET용 Aspose.PDF: Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 아직 설치하지 않았다면 다음을 수행하세요. [여기서 다운로드하세요](https://releases.aspose.com/pdf/net/).
- .NET 개발 환경: .NET 개발을 위해 Visual Studio, JetBrains Rider 또는 기타 선호하는 IDE를 사용할 수 있습니다.
- C#에 대한 기본 지식: C#에 익숙하면 더 쉽게 따라갈 수 있습니다.
- PDF 파일: 테스트용으로 샘플 PDF 파일을 준비해 두세요. 파일을 직접 만들거나 온라인에서 샘플을 다운로드할 수 있습니다.

방금 시작했다면 Aspose.PDF를 사용해 보세요. [무료 임시 면허](https://purchase.aspose.com/temporary-license/) 결정하기 전에 [정식 버전을 구매하세요](https://purchase.aspose.com/buy).

## 네임스페이스 가져오기

PDF 페이지를 조작하려면 먼저 C# 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 코드 파일 맨 위에 다음 줄을 추가하세요.

```csharp
using System.IO;
using Aspose.Pdf;
```

이제 모든 것을 설정했으니 시작해 볼까요!

## 1단계: PDF 문서 로드

첫 번째 단계는 수정하려는 PDF 파일을 로드하는 것입니다. `Document` Aspose.PDF 네임스페이스의 클래스:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

교체를 꼭 해주세요 `"YOUR DOCUMENT DIRECTORY"` PDF 파일의 실제 경로를 포함합니다.

## 2단계: 각 페이지 반복

다음으로, PDF 문서의 각 페이지를 순회합니다. 이렇게 하면 모든 페이지에 방향 변경을 적용할 수 있습니다.

```csharp
foreach (Page page in doc.Pages)
{
    // 각 페이지를 조작하세요
}
```

## 3단계: 페이지의 MediaBox에 액세스

각 PDF 페이지에는 `MediaBox` 경계를 정의하는 부분입니다. 현재 방향을 확인하고 조정하려면 여기에 접근해야 합니다.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

그만큼 `MediaBox` 너비와 높이를 포함한 페이지의 크기를 제공합니다.

## 4단계: 너비와 높이 바꾸기

페이지 방향을 변경하려면 너비와 높이 값을 서로 바꿔 보겠습니다. 이렇게 조정하면 페이지 크기가 변경됩니다.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

여기서 우리는 새로운 차원을 계산하고 왼쪽 아래 모서리를 다시 배치합니다.`LLY`) 따라서.

## 5단계: MediaBox 및 CropBox 업데이트

이제 새로운 차원이 있으므로 이러한 변경 사항을 적용하겠습니다. `MediaBox` 그리고 `CropBox` 페이지가 올바르게 표시되는지 확인하려면:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## 6단계: 페이지 회전

방향 변경을 마무리하기 위해 페이지를 회전해 보겠습니다. Aspose.PDF를 사용하면 매우 간단합니다.

```csharp
page.Rotate = Rotation.on90; // 90도 회전
```

이 줄은 페이지를 원하는 방향으로 효과적으로 뒤집습니다.

## 7단계: 출력 PDF 저장

모든 페이지의 방향을 수정한 후 업데이트된 문서를 새 파일에 저장합니다.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

원본 문서를 덮어쓰는 것을 방지하려면 반드시 새 파일 이름을 지정하세요.

## 결론

자, 이제 아시겠죠! Aspose.PDF for .NET을 사용하여 PDF 파일의 페이지 방향을 변경하는 것은 매우 간단한 과정입니다. 문서를 로드하고, 페이지를 순환 탐색하고, MediaBox를 업데이트하고, 파일을 저장하면 필요에 맞게 레이아웃을 쉽게 조정할 수 있습니다. 스캔이 제대로 되지 않은 문서를 수정하거나 프레젠테이션을 위해 페이지 서식을 지정하는 경우, 이 가이드가 작업을 효율적으로 수행하는 데 도움이 될 것입니다.

## 자주 묻는 질문

### PDF의 모든 페이지 대신 특정 페이지만 회전할 수 있나요?  
네, 모든 페이지를 반복하는 대신 특정 페이지의 인덱스를 기준으로 루프를 수정할 수 있습니다.

### 무엇입니까? `MediaBox`?  
그만큼 `MediaBox` PDF 파일에서 페이지의 크기와 모양을 정의하고 콘텐츠가 배치되는 위치를 결정합니다.

### .NET용 Aspose.PDF는 다른 파일 형식에서도 작동합니까?  
네, Aspose.PDF는 HTML, XML, XPS 등 다양한 파일 형식을 처리할 수 있습니다.

### .NET용 Aspose.PDF의 무료 버전이 있나요?  
네, 다음으로 시작할 수 있습니다. [무료 체험](https://releases.aspose.com/) 또는 요청 [임시 면허](https://purchase.aspose.com/temporary-license/).

### 변경 사항을 저장한 후 취소할 수 있나요?  
문서를 저장하면 변경 사항이 영구적으로 적용됩니다. 사본을 만들어 작업하거나 원본 파일을 백업해 두는 것이 좋습니다.