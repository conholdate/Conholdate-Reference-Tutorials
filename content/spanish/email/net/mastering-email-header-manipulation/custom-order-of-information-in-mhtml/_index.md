---
"description": "Aprenda a definir un orden de información personalizado en MHTML usando Aspose.Email para .NET en este tutorial paso a paso."
"linktitle": "Orden personalizado de información en MHTML con Aspose.Email"
"second_title": "API de procesamiento de correo electrónico Aspose.Email .NET"
"title": "Orden personalizado de información en MHTML con Aspose.Email"
"url": "/es/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## Introducción

Crear formatos de correo electrónico enriquecidos puede mejorar enormemente la comunicación, especialmente al exportar correos electrónicos a diferentes formatos de archivo como MHTML. Aspose.Email para .NET ofrece a los desarrolladores un potente conjunto de herramientas para manipular correos electrónicos, que incluye la definición de un orden personalizado para la visualización de la información al exportar a MHTML. En esta guía, detallaremos los pasos necesarios para lograrlo, facilitándole el seguimiento tanto a desarrolladores experimentados como a principiantes. ¡Comencemos!

## Prerrequisitos

Antes de sumergirte en la definición del orden personalizado de la información en MHTML, hay algunos requisitos previos que debes marcar en tu lista:

1. Entorno de desarrollo .NET: Asegúrate de tener configurado un entorno de desarrollo .NET. Puedes usar Visual Studio, Visual Studio Code o cualquier otro IDE compatible.

2. Biblioteca Aspose.Email: Necesita tener instalada la biblioteca Aspose.Email para .NET. Puede descargar la última versión desde [Página de lanzamiento de Aspose](https://releases.aspose.com/email/net/).

3. Comprensión básica de C#: la familiaridad con la programación en C# le ayudará a comprender mejor el código.

4. Archivo de correo electrónico de muestra: Necesitará una muestra `.eml` archivo (por ejemplo, `Attachments.eml`) para fines de prueba.

Una vez que tengas estos prerrequisitos, ¡estarás listo para seguir el tutorial!

## Importar paquetes

Para comenzar con su código, deberá importar los espacios de nombres necesarios de la biblioteca Aspose.Email. Esto es esencial para acceder a todas las clases y métodos necesarios para manipular los archivos de correo electrónico.

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

Inclúyelos al principio de tu archivo de C#. ¡Ya estás listo para empezar a programar!

Ahora que tienes todo configurado, dividamos el tutorial en pasos manejables.

## Paso 1: Configure su directorio de datos

Lo primero que debe hacer es crear un directorio donde se almacenarán sus archivos de correo electrónico. Puede ser cualquier ruta en su equipo local.

```csharp
string dataDir = "Your Data Directory";
```

Reemplazar `"Your Data Directory"` con el camino real donde se encuentra `.eml` se encuentra el archivo. Por ejemplo, si su archivo está en `C:\Emails`, escribirías:

```csharp
string dataDir = @"C:\Emails\";
```

## Paso 2: Cargar el mensaje de correo electrónico

A continuación, debes cargar el `.eml` archivo en un `MailMessage` objeto. Esto le permite manipular el contenido y los metadatos del correo electrónico.

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

Asegúrese de que el nombre del archivo coincida con el del directorio especificado. Si el nombre del archivo es diferente, actualícelo según corresponda.

## Paso 3: Configurar las opciones de guardado de MHTML

Con tu correo electrónico cargado, es hora de definir cómo quieres guardarlo como MHTML. Puedes empezar con las opciones predeterminadas.

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

Esta línea inicializa las opciones de guardado de MHTML, preparando el escenario para personalizar los encabezados más adelante.

## Paso 4: Guardar MHTML con orden predeterminado

Guardemos el correo electrónico como MHTML con el orden predeterminado. Esto te dará una base para compararlo después de la personalización.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

Ejecute esta línea y revise el directorio especificado. Debería ver un nuevo archivo MHTML llamado `CustomOrderOfInformationInMHTML_1.mhtml`. Ábrelo para ver cómo se muestra la información de forma predeterminada.

## Paso 5: Personalizar el orden del encabezado

¡Ahora viene la parte divertida! Puedes especificar qué encabezados incluir en la salida MHTML y en qué orden. Empezaremos con algunos encabezados comunes.

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

Al agregar estos encabezados, le estás diciendo a Aspose cómo deseas que se muestre el correo electrónico.

## Paso 6: Guardar MHTML con orden personalizado

Después de personalizar los encabezados, debe guardar nuevamente el correo electrónico como MHTML para ver cómo el nuevo orden afecta la salida.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

Ejecute este código y luego abra `CustomOrderOfInformationInMHTML_2.mhtml`Compárelo con el primero para ver cómo ha cambiado la información según el orden del encabezado.

## Paso 7: Borrar y agregar nuevo orden de encabezado

¿Qué pasa si quieres un orden completamente diferente? Puedes empezar de cero borrando la configuración del encabezado.

```csharp
opt.RenderingHeaders.Clear();
```

Ahora es el momento de definir un nuevo orden para los encabezados. Por ejemplo, si desea priorizar los archivos adjuntos y los destinatarios de las copias:

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## Paso 8: Guardar MHTML con nuevo orden personalizado

Por último, guarde el correo electrónico una última vez con la nueva configuración del encabezado.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

Después de ejecutar esta línea, abra `CustomOrderOfInformationInMHTML_3.mhtml` y comprobar cómo presenta la información en función de su nueva personalización.

## Conclusión

Aquí lo tiene: una guía sencilla para definir un orden personalizado de información en MHTML con Aspose.Email para .NET. Siguiendo estos pasos, puede controlar cómo se representan sus correos electrónicos en formato MHTML, garantizando que la información más importante se presente de forma adaptada a sus necesidades. 

## Preguntas frecuentes

### ¿Qué es MHTML?
MHTML significa "MIME HTML", un formato de archivo de páginas web que combina HTML y otros recursos como imágenes.

### ¿Puedo utilizar Aspose.Email gratis?
Sí, Aspose ofrece una versión de prueba gratuita para que los desarrolladores la exploren. Puedes encontrarla [aquí](https://releases.aspose.com/).

### ¿Qué pasa si encuentro problemas al utilizar Aspose.Email?
Puede obtener apoyo de la comunidad a través de [Foro de Aspose](https://forum.aspose.com/c/email/12/).

### ¿Hay una licencia temporal disponible para Aspose.Email?
Sí, puedes solicitar una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo comprar Aspose.Email?
Puedes adquirir la biblioteca en este [enlace](https://purchase.aspose.com/buy).