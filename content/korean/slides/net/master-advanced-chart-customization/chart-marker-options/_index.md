---
"description": "Aspose.Slides for .NET을 사용하여 사용자 지정 마커 옵션으로 PowerPoint 차트를 개선하는 방법을 알아보세요. 이 단계별 가이드에서는 사전 요구 사항, 차트 생성, 데이터 요소 서식 지정 등에 대해 설명합니다."
"linktitle": "Aspose.Slides .NET의 데이터 포인트에 대한 차트 마커 옵션"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides .NET의 데이터 포인트에 대한 차트 마커 옵션"
"url": "/ko/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## 소개

효과적인 커뮤니케이션을 위해서는 프레젠테이션에 시각 자료를 통합하는 것이 필수적입니다. Aspose.Slides for .NET은 차트를 만들고 사용자 정의할 수 있는 강력한 도구를 제공하여 개발자가 데이터 프레젠테이션을 개선할 수 있도록 지원합니다. 특히 눈에 띄는 기능 중 하나는 데이터 포인트에 차트 마커 옵션을 적용하여 전문적인 차트를 정교하게 사용자 정의할 수 있다는 것입니다. 이 글에서는 이러한 기능을 구현하는 데 필요한 모든 단계를 안내합니다.

## 필수 조건

계속하기 전에 다음 사항을 확인하세요.

- .NET용 Aspose.Slides 설치: 여기에서 다운로드하세요. [여기](https://releases.aspose.com/slides/net/).
- 기본 설정: 작업 디렉토리에 "Test.pptx"와 같은 프레젠테이션 파일이 있습니다.
- 개발 환경: Visual Studio 또는 이와 동등한 환경, .NET용으로 구성됨.

## 필수 네임스페이스 가져오기

원활한 개발을 위해 프로젝트에 필요한 네임스페이스를 추가하세요.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## 1단계: 프레젠테이션에서 차트 만들기

프레젠테이션의 첫 번째 슬라이드에 기본 차트를 만들어 보세요.

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

이것은 다음을 추가합니다. `LineWithMarkers` 지정된 치수로 슬라이드에 차트를 추가합니다.

## 2단계: 차트 데이터 워크시트 인덱스 검색

기본 차트 데이터 워크시트 인덱스는 추가 사용자 정의에 필수적입니다.

```csharp
int defaultWorksheetIndex = 0;
```

## 3단계: 차트 데이터 통합 문서에 액세스

차트 데이터를 조작하려면 연관된 통합 문서를 검색하세요.

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## 4단계: 차트 시리즈 구성 및 데이터 포인트 추가

기본 시리즈를 지우고 시리즈에 새로운 데이터 포인트를 추가하세요.

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// 시리즈에 데이터 포인트 추가
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## 5단계: 데이터 포인트 마커에 그림 채우기 적용

사용자 정의 이미지를 사용하면 데이터 마커를 시각적으로 매력적으로 만들 수 있습니다.

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// 마커에 대한 사용자 정의 이미지 설정
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## 6단계: 마커 크기 사용자 지정

가시성을 높이기 위해 마커 크기를 수정하세요.

```csharp
series.Marker.Size = 20;
```

## 7단계: 업데이트된 프레젠테이션 저장

사용자 정의된 프레젠테이션을 원하는 위치에 저장하세요.

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## 결론

Aspose.Slides for .NET은 개발자에게 풍부한 사용자 지정 옵션을 갖춘 전문적인 차트를 제작할 수 있는 도구를 제공합니다. 차트 마커 옵션을 활용하여 프레젠테이션의 시각적 매력과 명확성을 크게 향상시킬 수 있습니다. 이 단계별 가이드를 통해 복잡한 사용자 지정도 간편하게 구현할 수 있습니다.

## 자주 묻는 질문

### 마커를 사용자 정의하는 데 모든 이미지 형식을 사용할 수 있나요?
네, Aspose.Slides는 마커 사용자 정의를 위해 JPEG, PNG, BMP 등 다양한 이미지 형식을 지원합니다.

### 차트를 만든 후에 차트 유형을 어떻게 변경합니까?
차트 유형을 변경하려면 `chart.Type` 속성을 지정하고 다른 것을 할당합니다 `ChartType`.

### Aspose.Slides for .NET은 이전 버전의 PowerPoint와 호환됩니까?
네, 이전 PowerPoint 형식과의 하위 호환성을 지원하여 다양한 용도로 사용할 수 있습니다.

### 차트 데이터를 동적으로 업데이트할 수 있나요?
물론입니다. 사용하세요 `IChartDataWorkbook` 차트 데이터를 프로그래밍 방식으로 업데이트합니다.

### 더 많은 자료는 어디에서 찾을 수 있나요?
탐색하다 [Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 또는 가입하세요 [커뮤니티 포럼](https://forum.aspose.com/) 지원을 위해.