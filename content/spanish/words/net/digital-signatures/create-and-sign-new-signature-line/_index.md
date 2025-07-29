---
"description": "Aprenda a añadir fácilmente una firma digital a sus documentos de Word con Aspose.Words para .NET. Este completo tutorial abarca todo, desde la configuración de su entorno y la inserción de una línea de firma hasta el guardado y la verificación de sus documentos firmados."
"linktitle": "Crear y firmar una nueva línea de firma"
"second_title": "API de procesamiento de documentos de Aspose.Words"
"title": "Crear y firmar una nueva línea de firma"
"url": "/es/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## Introducción

¿Quieres añadir una firma digital a un documento de Word? ¡Con Aspose.Words para .NET, es más fácil de lo que crees! Este tutorial te guiará por los pasos para configurar tu entorno, añadir una línea de firma y firmar tu documento digitalmente. ¡Comencemos!

## Prerrequisitos

Antes de sumergirse en el código, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET - [Descárgalo aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo .NET: Visual Studio es ideal para esta tarea.
3. Documento para firmar: puede crear un nuevo documento de Word o utilizar uno existente.
4. Archivo de certificado - A `.pfx` El archivo es necesario para las firmas digitales.
5. Imagen de la línea de firma (opcional): puede incluir un archivo de imagen para la firma.

## Importar espacios de nombres requeridos

Para utilizar las funcionalidades de Aspose.Words, debe importar los siguientes espacios de nombres:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Paso 1: Configuración del directorio de documentos

Comience por definir la ruta a su directorio de documentos. Aquí guardará y recuperará sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Especifique la ruta del directorio de su documento
```

## Paso 2: Crear un nuevo documento

A continuación, crearemos un nuevo documento de Word. Este documento servirá como lienzo para la línea de firma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Inserción de la línea de firma

Ahora, utiliza el `DocumentBuilder` clase para insertar una línea de firma en su documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Paso 4: Guardar el documento

Una vez insertada la línea de firma, guarde el documento. Este paso es crucial antes de firmar.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Paso 5: Configuración de las opciones de firma

Configure las opciones del proceso de firma. Esto incluye especificar el ID de la línea de firma y la imagen opcional que se mostrará con la firma.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // Camino a tu imagen
};
```

## Paso 6: Carga del certificado

Cargue el archivo de certificado necesario para firmar el documento:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // Ajustar el nombre del archivo y la contraseña
```

## Paso 7: Firma del documento

Finalmente, firme el documento utilizando el `DigitalSignatureUtil` Clase. Guarde el documento firmado con un nuevo nombre para futuras referencias.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## Conclusión

¡Felicitaciones! Ha creado correctamente un documento de Word, le ha añadido una línea de firma y lo ha firmado digitalmente con Aspose.Words para .NET. Esta potente herramienta simplifica la automatización de documentos, garantizando que sus contratos y documentos formales estén firmados y autenticados de forma segura.

## Preguntas frecuentes

### ¿Puedo utilizar otros formatos de imagen para la línea de firma?

Sí, puedes utilizar varios formatos de imagen, incluidos PNG, JPG y BMP.

### ¿Es necesario utilizar un? `.pfx` ¿archivo para el certificado?

Sí, una `.pfx` El archivo es un formato estándar para almacenar certificados y claves privadas para firmas digitales.

### ¿Puedo agregar varias líneas de firma en un solo documento?

¡Claro! Puedes insertar varias líneas de firma repitiendo el paso de inserción según sea necesario.

### ¿Qué pasa si no tengo un certificado digital?

Necesitará obtener un certificado digital de una autoridad de certificación confiable o generar uno utilizando herramientas como OpenSSL.

### ¿Cómo verificar la firma digital en el documento?

Puede verificar la firma digital abriendo el documento firmado en Word y verificando los detalles de la firma para confirmar su autenticidad e integridad.