---
"description": "Aprenda a converter layouts CAD em diversos formatos de imagem raster com eficiência usando o Aspose.CAD para .NET. Este guia completo orienta você no processo com um código claro."
"linktitle": "Exportar CAD para conversão de imagem raster"
"second_title": "Aspose.CAD .NET - Formato de arquivo CAD e BIM"
"title": "Exportar CAD para conversão de imagem raster com Aspose.CAD para .NET"
"url": "/pt/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## Introdução

Deseja converter layouts CAD em formatos de imagem raster sem esforço usando o Aspose.CAD para .NET? Este guia passo a passo foi elaborado para ajudar você a navegar pelo processo, completo com trechos de código concisos para uma experiência tranquila. Seja você um desenvolvedor experiente ou iniciante, este tutorial oferece insights valiosos para todos os níveis de habilidade.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Biblioteca Aspose.CAD para .NET: Baixe e instale a biblioteca do [Site Aspose.CAD](https://releases.aspose.com/cad/net/).
- Arquivo de desenho CAD: Tenha seu arquivo de desenho CAD (por exemplo, `conic_pyramid.dxf`) pronto para conversão.

## Importar namespaces necessários

No seu projeto .NET, você precisará importar os namespaces necessários para utilizar as funções do Aspose.CAD. Adicione o seguinte ao início do seu código:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Etapa 1: carregue seu desenho CAD

Primeiro, especifique o diretório e carregue seu arquivo CAD em uma instância de imagem:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// Carregar o desenho CAD
using (var image = Image.Load(sourceFilePath))
{
    // Prossiga para as próximas etapas
}
```

## Etapa 2: Criar opções de rasterização

Em seguida, configure as opções de rasterização, definindo as dimensões desejadas para a imagem de saída:

```csharp
// Inicializar CadRasterizationOptions
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## Etapa 3: especificar camadas para conversão

Se você quiser converter camadas específicas, adicione-as às suas opções de rasterização:

```csharp
// Especifique a camada a ser convertida
rasterizationOptions.Layers = new [] { "LayerA" };
```

## Etapa 4: Configurar opções de exportação JPEG

Agora, crie opções para o formato de imagem que você deseja exportar (JPEG neste caso):

```csharp
// Crie JpegOptions para exportação
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Etapa 5: Exportar para o formato JPEG

Por fim, salve a imagem convertida:

```csharp
// Defina o caminho do arquivo de saída e salve a imagem
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## Recurso adicional: converter todas as camadas

Para converter todas as camadas no seu desenho CAD, você pode implementar um método como este:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // Itere pelas camadas e salve cada uma como um arquivo JPEG separado
    // Seu código de implementação aqui
}
```

## Conclusão

Parabéns! Você aprendeu a converter layouts CAD em formatos de imagem raster com eficiência usando o Aspose.CAD para .NET. Este guia oferece uma abordagem simples, adequada para desenvolvedores que buscam conversões CAD eficientes.

## Perguntas frequentes

### Posso exportar para diferentes formatos de imagem?

Com certeza! Basta trocar `JpegOptions` com outras opções de formato, como `PngOptions` ou `BmpOptions`, dependendo de suas necessidades.

### Há uma versão de teste disponível?

Sim, você pode baixar uma versão de teste para explorar a funcionalidade seguindo este [link](https://releases.aspose.com/cad/net/).

### Onde posso encontrar suporte para o Aspose.CAD?

Para obter suporte da comunidade, confira o Aspose.CAD [fórum](https://forum.aspose.com/c/cad/19), ou considere comprar uma licença para uma assistência mais dedicada.

### Licenças temporárias são possíveis?

Sim, licenças temporárias estão disponíveis; você pode solicitar uma [aqui](https://purchase.conholdate.com/temporary-license/).

### Onde posso acessar a documentação detalhada?

Visite a documentação completa [aqui](https://reference.aspose.com/cad/net/) para maiores informações.