---
"description": "Aprenda a mejorar sus gráficos de PowerPoint con opciones de marcadores personalizados usando Aspose.Slides para .NET. Esta guía paso a paso cubre los prerrequisitos, la creación de gráficos, el formato de puntos de datos y más."
"linktitle": "Opciones de marcador de gráfico en puntos de datos en Aspose.Slides .NET"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Opciones de marcador de gráfico en puntos de datos en Aspose.Slides .NET"
"url": "/es/slides/net/master-advanced-chart-customization/chart-marker-options/"
"weight": 11
---

## Introducción

Incorporar recursos visuales en las presentaciones es esencial para una comunicación eficaz. Aspose.Slides para .NET ofrece herramientas robustas para crear y personalizar gráficos, lo que permite a los desarrolladores optimizar sus presentaciones de datos. Una de sus características destacadas es la posibilidad de usar marcadores de gráficos en los puntos de datos, lo que permite una personalización precisa para obtener gráficos de aspecto profesional. Este artículo le guiará paso a paso para lograrlo.

## Prerrequisitos

Antes de continuar, asegúrese de lo siguiente:

- Aspose.Slides para .NET instalado: Descárguelo desde [aquí](https://releases.aspose.com/slides/net/).
- Configuración básica: un archivo de presentación, como "Test.pptx", en su directorio de trabajo.
- Entorno de desarrollo: Visual Studio o equivalente, configurado para .NET.

## Importación de espacios de nombres requeridos

Agregue los espacios de nombres necesarios a su proyecto para un desarrollo sin inconvenientes:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Paso 1: Crea un gráfico en tu presentación

Comience creando un gráfico predeterminado en la primera diapositiva de su presentación:

```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.Slides[0];

IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 600, 400);
```

Esto añade un `LineWithMarkers` Gráfico a su diapositiva con dimensiones específicas.

## Paso 2: Recuperar el índice de la hoja de trabajo de datos del gráfico

El índice de la hoja de cálculo de datos del gráfico predeterminado es esencial para una mayor personalización:

```csharp
int defaultWorksheetIndex = 0;
```

## Paso 3: Acceda al libro de trabajo de datos del gráfico

Para manipular datos del gráfico, recupere el libro de trabajo asociado:

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

## Paso 4: Configurar series de gráficos y agregar puntos de datos

Borrar la serie predeterminada y agregar nuevos puntos de datos para su serie:

```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Agregar puntos de datos a la serie
IChartSeries series = chart.ChartData.Series[0];
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 2, 4.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 2, 2.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 2, 3.5));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 2, 4.0));
```

## Paso 5: Aplicar rellenos de imagen a los marcadores de puntos de datos

Las imágenes personalizadas pueden hacer que los marcadores de datos sean visualmente atractivos:

```csharp
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "flower.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Establecer imágenes personalizadas para marcadores
series.DataPoints[0].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[0].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

series.DataPoints[1].Marker.Format.Fill.FillType = FillType.Picture;
series.DataPoints[1].Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

## Paso 6: Personalizar el tamaño del marcador

Modificar el tamaño de los marcadores para mejorar la visibilidad:

```csharp
series.Marker.Size = 20;
```

## Paso 7: Guardar la presentación actualizada

Guarde la presentación personalizada en la ubicación deseada:

```csharp
pres.Save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Conclusión

Aspose.Slides para .NET proporciona a los desarrolladores herramientas para crear gráficos profesionales con amplias opciones de personalización. Al aprovechar las opciones de marcadores de gráficos, puede mejorar significativamente el atractivo visual y la claridad de sus presentaciones. Esta guía paso a paso garantiza que incluso las personalizaciones más complejas sean fáciles de implementar.

## Preguntas frecuentes

### ¿Puedo usar cualquier formato de imagen para personalizar el marcador?
Sí, Aspose.Slides admite varios formatos de imagen, incluidos JPEG, PNG y BMP, para personalizar los marcadores.

### ¿Cómo cambio el tipo de gráfico después de su creación?
Para cambiar el tipo de gráfico, acceda a `chart.Type` propiedad y asignar una diferente `ChartType`.

### ¿Aspose.Slides para .NET es compatible con versiones anteriores de PowerPoint?
Sí, admite compatibilidad con formatos de PowerPoint más antiguos, lo que garantiza versatilidad.

### ¿Puedo actualizar dinámicamente los datos del gráfico?
Por supuesto. Usa el `IChartDataWorkbook` para actualizar programáticamente los datos del gráfico.

### ¿Dónde puedo encontrar más recursos?
Explora el [Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) o únete a la [foros comunitarios](https://forum.aspose.com/) para soporte.