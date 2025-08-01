---
"description": "Descubra cómo controlar con maestría la visibilidad del contenido en documentos de Word con Aspose.Words para .NET. Esta guía paso a paso."
"linktitle": "Administrar la visibilidad de marcadores en documentos de Word"
"second_title": "API de procesamiento de documentos de Aspose.Words"
"title": "Administrar la visibilidad de marcadores en documentos de Word"
"url": "/es/words/net/mastering-bookmarks/manage-bookmark-visibility-word-document/"
"weight": 10
---

## Introducción

¿Listo para mejorar tus habilidades de manipulación de documentos con Aspose.Words para .NET? Tanto si eres un desarrollador experimentado que automatiza tareas de documentos como si tienes curiosidad por explorar el control programático de archivos de Word, esta guía está hecha a tu medida. Hoy profundizaremos en cómo mostrar y ocultar contenido según los marcadores en un documento de Word. ¡Comencemos!

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Visual Studio: Cualquier versión compatible con .NET.
2. Aspose.Words para .NET: Descárgalo [aquí](https://releases.aspose.com/words/net/).
3. Conocimientos básicos de C#: será suficiente estar familiarizado con la escritura de programas C# simples.
4. Un documento de Word de muestra: prepare un documento de Word (por ejemplo, "Bookmarks.docx") que contenga marcadores para este tutorial.

### Crear un nuevo proyecto

1. Abra Visual Studio y cree un proyecto de aplicación de consola (.NET Core). Llámelo, por ejemplo, "BookmarkVisibilityManager".

### Instalar Aspose.Words para .NET

Agregue Aspose.Words a su proyecto a través del Administrador de paquetes NuGet:

1. Vaya a Herramientas > Administrador de paquetes NuGet > Administrar paquetes NuGet para la solución.
2. Busca "Aspose.Words".
3. Instalar el paquete.

Con el proyecto configurado, procedamos a cargar el documento.

## Importación de espacios de nombres

Comience importando los espacios de nombres esenciales. Estos proporcionan las clases y los métodos necesarios para manipular documentos de Word con Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

## Paso 1: Carga del documento

Para manipular el documento de Word, primero debemos cargarlo. Así es como se hace:

```csharp
// Define la ruta al directorio de tus documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

Este fragmento establece la ruta a su directorio de documentos y carga el documento en un `Document` objeto.

## Paso 2: Mostrar/ocultar contenido marcado

Ahora, vamos a crear un método para alternar la visibilidad del contenido según los marcadores. Lo llamaremos `ShowHideBookmarkedContent`.

Aquí está la implementación del método:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    if (bm != null)
    {
        Node currentNode = bm.BookmarkStart;
        while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
        {
            if (currentNode.NodeType == NodeType.Run)
            {
                Run run = (Run)currentNode;
                run.Font.Hidden = isHidden;
            }
            currentNode = currentNode.NextSibling;
        }
    }
}
```

- Recuperación de marcadores: `Bookmark bm = doc.Range.Bookmarks[bookmarkName];` Obtiene el marcador especificado.
- Recorrido de nodos: iteramos a través de los nodos dentro del marcador.
- Alternar visibilidad: para cada `Run` nodo (que representa un segmento de texto), lo establecemos `Hidden` propiedad basada en la `isHidden` parámetro.

## Paso 3: Aplicación del método

Ahora que tenemos nuestro método listo, usémoslo para mostrar u ocultar contenido dentro de un marcador específico:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true); // Oculta el contenido dentro de "MyBookmark1"
```

Esta línea ocultará el contenido asociado con el marcador llamado "MyBookmark1".

## Paso 4: Guardar el documento

Una vez que hayas realizado los cambios, no olvides guardar el documento modificado:

```csharp
doc.Save(dataDir + "UpdatedBookmarks.docx");
```

Esto guarda el documento con la configuración de visibilidad actualizada.

## Conclusión

¡Felicitaciones! Has aprendido a mostrar y ocultar el contenido marcado en un documento de Word con Aspose.Words para .NET. Esta potente biblioteca simplifica la manipulación de documentos, lo que la hace ideal para automatizar informes, crear plantillas o experimentar con archivos de Word. ¡Que disfrutes programando!

## Preguntas frecuentes

### ¿Puedo alternar entre varios marcadores a la vez?
Sí, simplemente llame al `ShowHideBookmarkedContent` método para cada marcador que desee alternar.

### ¿Ocultar contenido afecta la estructura del documento?
No, ocultar contenido solo afecta su visibilidad; el contenido permanece intacto dentro del documento.

### ¿Puedo utilizar este método para otros tipos de contenido?
Este método está diseñado específicamente para secuencias de texto. Para otros tipos de contenido, deberá adaptar la lógica de recorrido del nodo según corresponda.

### ¿Aspose.Words para .NET es gratuito?
Aspose.Words ofrece una prueba gratuita [aquí](https://releases.aspose.com/), pero se requiere una licencia completa para su uso en producción. Puedes adquirirla. [aquí](https://purchase.aspose.com/buy).

### ¿Cómo puedo obtener ayuda si encuentro problemas?
Para obtener ayuda, visite el foro de la comunidad de Aspose [aquí](https://forum.aspose.com/c/words/8).