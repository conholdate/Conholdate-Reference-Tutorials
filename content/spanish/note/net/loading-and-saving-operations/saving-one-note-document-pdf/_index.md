---
"description": "Aprenda a guardar documentos de Microsoft OneNote como archivos PDF de forma eficiente con Aspose.Note para .NET. Esta guía le explica los requisitos previos necesarios y ofrece preguntas frecuentes útiles."
"linktitle": "Guardar documentos de OneNote en PDF"
"second_title": "API .NET de Aspose.Note"
"title": "Cómo guardar documentos de OneNote en PDF con Aspose.Note para .NET"
"url": "/es/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Introducción

En este tutorial, exploraremos cómo guardar documentos en formato PDF con Aspose.Note para .NET. Aspose.Note es una potente biblioteca que permite a los desarrolladores trabajar con archivos de Microsoft OneNote mediante programación. Explicaremos los requisitos previos, la importación de espacios de nombres y proporcionaremos guías paso a paso para guardar documentos en PDF en diferentes diseños de página.

## Prerrequisitos
1. Visual Studio: asegúrese de que esté instalado.
2. Aspose.Note para .NET: Descargue e instale la biblioteca.
3. Conocimiento de C#: Se requiere comprensión básica del lenguaje.

## Importación de espacios de nombres necesarios
Antes de continuar, importe los siguientes espacios de nombres en su código:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Paso 1: Guardar en PDF con configuración de página de carta
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Actualizar esta ruta
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Carga el documento de OneNote y lo guarda como PDF utilizando configuraciones de página de tamaño carta.

## Paso 2: Guardar como PDF con configuración de página A4 (sin límite de altura)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Actualizar esta ruta
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Similar al paso 1, pero utiliza configuraciones de página A4 sin limitaciones de altura.

## Conclusión
El tutorial demuestra con éxito cómo convertir archivos de OneNote a formato PDF con Aspose.Note. Al utilizar diferentes configuraciones de página, los desarrolladores obtienen mayor flexibilidad en la gestión de documentos.

## Preguntas frecuentes
### ¿Puede Aspose.Note manejar archivos complejos de OneNote?
Sí, maneja eficazmente varias funciones de archivos complejos de OneNote.

### ¿Es Aspose.Note adecuado para proyectos comerciales?
Sí, puedes usarlo para aplicaciones comerciales después de comprar una licencia.

### ¿Aspose.Note ofrece una prueba gratuita?
Sí, hay una prueba gratuita disponible para explorar.

### ¿Dónde puedo encontrar documentación para Aspose.Note?
La documentación detallada está disponible en el sitio de referencia de Aspose.

### ¿Necesita más ayuda?
Para preguntas y asistencia, consulte el foro Aspose.Note.