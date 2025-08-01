---
"description": "Aspose.Words for .NET을 사용하여 Word 문서에 디지털 서명을 원활하게 추가하는 방법을 알아보세요. 이 포괄적인 튜토리얼에서는 환경 설정 및 서명란 삽입부터 서명된 문서 저장 및 확인까지 모든 것을 다룹니다."
"linktitle": "새 서명란 만들기 및 서명"
"second_title": "Aspose.Words 문서 처리 API"
"title": "새 서명란 만들기 및 서명"
"url": "/ko/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## 소개

Word 문서에 디지털 서명을 추가하고 싶으신가요? Aspose.Words for .NET을 사용하면 생각보다 훨씬 쉽습니다! 이 튜토리얼에서는 환경 설정, 서명란 추가, 그리고 문서에 디지털 서명하는 단계를 안내합니다. 시작해 볼까요!

## 필수 조건

코드를 살펴보기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.Words - [여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
2. .NET 개발 환경 - Visual Studio는 이 작업에 이상적입니다.
3. 서명할 문서 - 새 Word 문서를 만들거나 기존 문서를 사용할 수 있습니다.
4. 인증서 파일 - A `.pfx` 디지털 서명에는 파일이 필요합니다.
5. 서명란 이미지(선택 사항) - 서명에 대한 이미지 파일을 포함할 수 있습니다.

## 필수 네임스페이스 가져오기

Aspose.Words의 기능을 사용하려면 다음 네임스페이스를 가져와야 합니다.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## 1단계: 문서 디렉터리 설정

먼저 문서 디렉터리 경로를 정의하세요. 이 경로에 문서를 저장하고 불러오게 됩니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // 문서 디렉토리 경로를 지정하세요
```

## 2단계: 새 문서 만들기

다음으로, 새 Word 문서를 만들어 보겠습니다. 이 문서는 서명란의 캔버스 역할을 할 것입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 서명란 삽입

이제 사용하세요 `DocumentBuilder` 문서에 서명줄을 삽입하는 클래스:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 4단계: 문서 저장

서명란을 삽입한 후 문서를 저장하세요. 서명하기 전에 꼭 해야 하는 중요한 단계입니다.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## 5단계: 서명 옵션 구성

서명 프로세스 옵션을 설정합니다. 여기에는 서명란 ID와 서명과 함께 표시할 이미지(선택 사항) 지정이 포함됩니다.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // 이미지로 가는 경로
};
```

## 6단계: 인증서 로드

문서 서명에 필요한 인증서 파일을 로드합니다.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // 파일 이름과 비밀번호 조정
```

## 7단계: 문서 서명

마지막으로 다음을 사용하여 문서에 서명합니다. `DigitalSignatureUtil` 클래스. 나중에 참조할 수 있도록 서명된 문서를 새 이름으로 저장하세요.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## 결론

축하합니다! Aspose.Words for .NET을 사용하여 Word 문서를 만들고, 서명란을 추가하고, 디지털 서명을 완료했습니다. 이 강력한 도구는 문서 자동화를 간소화하여 계약서와 공식 문서의 안전한 서명 및 인증을 보장합니다.

## 자주 묻는 질문

### 서명란에 다른 이미지 형식을 사용할 수 있나요?

네, PNG, JPG, BMP 등 다양한 이미지 형식을 사용할 수 있습니다.

### 를 사용해야 합니까? `.pfx` 인증서 파일?

네, 하나 `.pfx` 파일은 디지털 서명을 위한 인증서와 개인 키를 저장하는 표준 형식입니다.

### 하나의 문서에 여러 개의 서명줄을 추가할 수 있나요?

물론입니다! 필요에 따라 삽입 단계를 반복하여 여러 개의 서명 줄을 삽입할 수 있습니다.

### 디지털 인증서가 없으면 어떻게 하나요?

신뢰할 수 있는 인증 기관에서 디지털 인증서를 얻거나 OpenSSL과 같은 도구를 사용하여 인증서를 생성해야 합니다.

### 문서의 디지털 서명을 어떻게 검증합니까?

Word에서 서명된 문서를 열고 서명 세부 정보를 확인하여 진위성과 무결성을 확인하면 디지털 서명을 확인할 수 있습니다.