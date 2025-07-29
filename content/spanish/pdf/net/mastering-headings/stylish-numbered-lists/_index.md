---
"description": "Descubra cómo crear listas numeradas con estilo en sus documentos PDF con Aspose.PDF para .NET. Esta guía le guiará en el proceso de aplicar diversos estilos de numeración, como los números romanos."
"linktitle": "Listas numeradas con estilo usando Aspose.PDF para .NET"
"second_title": "Referencia de la API de Aspose.PDF para .NET"
"title": "Listas numeradas con estilo usando Aspose.PDF para .NET"
"url": "/es/net/programming-with-headings/stylish-numbered-lists/"
"weight": 10
---

## Introducción

¿Alguna vez ha necesitado crear listas numeradas y bien estructuradas en sus documentos PDF? Ya sea para documentos legales, informes o presentaciones, contar con estilos de numeración efectivos es crucial para organizar su contenido. Con Aspose.PDF para .NET, puede aplicar fácilmente diversos estilos de numeración a los encabezados de sus PDF, lo que resulta en documentos impecables y profesionales.

## Prerrequisitos

Antes de comenzar con la codificación, asegúrese de tener lo siguiente listo:

1. Aspose.PDF para .NET: Descargue la última versión desde [aquí](https://releases.aspose.com/pdf/net/).
2. Entorno de desarrollo: necesitará Visual Studio o cualquier IDE compatible con .NET.
3. .NET Framework: asegúrese de tener instalado .NET Framework 4.0 o superior.
4. Licencia: Puede utilizar una licencia temporal de [aquí](https://purchase.aspose.com/temporary-license/) o explorar el [prueba gratuita](https://releases.aspose.com/) opciones.

## Importación de paquetes necesarios

Comience importando los espacios de nombres necesarios en su proyecto:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 1: Configuración del documento

Comencemos creando un nuevo documento PDF y configurando su diseño, incluido el tamaño de página y los márgenes.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Establecer las dimensiones y los márgenes de la página
pdfDoc.PageInfo.Width = 612.0; // 8,5 pulgadas
pdfDoc.PageInfo.Height = 792.0; // 11 pulgadas
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo(72, 72, 72, 72); // márgenes de 1 pulgada
```

Esta configuración le da a su documento un tamaño de carta estándar con márgenes de una pulgada en todos los lados.

## Paso 2: Agregar una página al PDF

A continuación, agregaremos una página en blanco al documento PDF, donde posteriormente aplicaremos los estilos de numeración.

```csharp
// Agregar una nueva página al documento PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo = pdfDoc.PageInfo; // Utilice la misma configuración que el documento
```

## Paso 3: Creación de un cuadro flotante

Un FloatingBox le permite posicionar el contenido independientemente del flujo de la página, lo que le brinda un mayor control sobre su diseño.

```csharp
// Crear un FloatingBox para contenido estructurado
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox
{
    Margin = pdfPage.PageInfo.Margin
};
pdfPage.Paragraphs.Add(floatBox);
```

## Paso 4: Agregar encabezados con números romanos

Ahora, agreguemos nuestro primer encabezado con numeración en números romanos en minúscula.

```csharp
// Crea el primer encabezado con números romanos
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

## Paso 5: Agregar un segundo encabezado con un número inicial personalizado

A continuación, agregaremos un segundo encabezado, comenzando desde el número romano 13.

```csharp
// Crea un segundo encabezado que comience con el número romano 13
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

## Paso 6: Agregar un encabezado con numeración alfabética

Para variar, añadiremos un tercer encabezado utilizando numeración alfabética en minúsculas.

```csharp
// Crear un encabezado con numeración alfabética
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

## Paso 7: Guardar el PDF

Por último, guardemos el archivo PDF en el directorio deseado.

```csharp
// Guardar el documento PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine($"\nNumber style applied successfully in headings.\nFile saved at {dataDir}");
```

## Conclusión

¡Felicitaciones! Ha aplicado correctamente varios estilos de numeración (en números romanos y alfabéticos) a los encabezados de un archivo PDF con Aspose.PDF para .NET. La flexibilidad de Aspose.PDF le permite controlar el diseño de página, los estilos de numeración y la ubicación del contenido, lo que le permite crear documentos PDF bien organizados y profesionales.

## Preguntas frecuentes

### ¿Puedo aplicar diferentes estilos de números al mismo documento PDF?  
Sí, puede mezclar diferentes estilos de numeración, como números romanos, números arábigos y numeración alfabética dentro del mismo documento.

### ¿Cómo puedo personalizar el número inicial de los encabezados?  
Puede establecer el número de inicio para cualquier encabezado utilizando el `StartNumber` propiedad.

### ¿Hay alguna forma de restablecer la secuencia de numeración?  
Sí, puedes restablecer la numeración ajustando el `StartNumber` propiedad para cada encabezado.

### ¿Puedo aplicar estilo negrita o cursiva a los encabezados además de la numeración?  
¡Por supuesto! Puedes personalizar los estilos de encabezado modificando propiedades como fuente, tamaño, negrita y cursiva con el `TextState` objeto.

### ¿Cómo puedo obtener una licencia temporal para Aspose.PDF?  
Puede obtener una licencia temporal en [aquí](https://purchase.aspose.com/temporary-license/) para probar Aspose.PDF sin restricciones.