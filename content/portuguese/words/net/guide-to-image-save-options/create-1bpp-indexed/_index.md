---
"description": "Este guia fornece instruções passo a passo e código de exemplo para ajudar você a criar eficientemente imagens indexadas de 1Bpp para arquivamento, impressão ou economia de espaço."
"linktitle": "Criar 1Bpp Indexado"
"second_title": "API de processamento de documentos Aspose.Words"
"title": "Criar 1Bpp Indexado"
"url": "/pt/words/net/guide-to-image-save-options/create-1bpp-indexed/"
"weight": 10
---

## Introdução

Você já precisou converter um documento do Word em uma imagem em preto e branco? Seja para arquivamento digital, impressão ou simplesmente para economizar espaço, converter seus documentos em uma imagem indexada de 1Bpp pode ser incrivelmente útil. Neste guia, mostraremos um método simples para fazer isso usando o Aspose.Words para .NET. Vamos começar!

## Pré-requisitos

Antes de mergulhar no código, certifique-se de ter o seguinte:

- Aspose.Words para .NET: Baixe e instale a biblioteca de [aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento .NET: embora o Visual Studio seja uma escolha popular, qualquer IDE que suporte .NET funcionará.
- Conhecimento básico de C#: A familiaridade com C# ajudará, mas manteremos as coisas simples.
- Exemplo de documento do Word: tenha um documento pronto para conversão.

## Etapa 1: Importar os namespaces necessários

Para usar o Aspose.Words, você precisa importar os namespaces relevantes. Isso é essencial para acessar as classes e métodos necessários para a manipulação de documentos.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 2: configure seu diretório de documentos

Especifique o caminho para o diretório onde o documento do Word está armazenado e onde você deseja salvar a imagem convertida.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Etapa 3: Carregue o documento do Word

Carregue seu documento do Word em um `Aspose.Words.Document` objeto. Este objeto permite que você manipule o documento programaticamente.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 4: Configurar opções de salvamento de imagem

Em seguida, configure o `ImageSaveOptions` para definir como o documento será salvo como imagem. Vamos configurá-lo para salvar no formato PNG com modo de cor indexada de 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1), // Converta apenas a primeira página
    ImageColorMode = ImageColorMode.BlackAndWhite, // Definir para preto e branco
    PixelFormat = ImagePixelFormat.Format1bppIndexed // Use o formato indexado 1Bpp
};
```

- SaveFormat.Png: Especifica que o formato de saída será PNG.
- PageSet(1): Indica que somente a primeira página do documento será convertida.
- ImageColorMode.BlackAndWhite: garante que a imagem esteja em preto e branco.
- ImagePixelFormat.Format1bppIndexed: define o formato de pixel como indexado em 1Bpp, otimizando o espaço.

## Etapa 5: Salve o documento como uma imagem

Por fim, use o `Save` método do `Document` objeto para salvar a imagem convertida.

```csharp
doc.Save(dataDir + "ConvertedImage.Format1BppIndexed.Png", saveOptions);
```

## Conclusão

Parabéns! Você converteu com sucesso um documento do Word em uma imagem indexada de 1Bpp usando o Aspose.Words para .NET. Este método não só é eficiente como também ajuda a criar imagens de alto contraste adequadas para diversas aplicações. Sinta-se à vontade para integrar esta funcionalidade aos seus projetos. Boa programação!

## Perguntas frequentes

### O que é uma imagem indexada de 1Bpp?
Uma imagem indexada de 1Bpp (1 bit por pixel) é um formato de imagem em preto e branco em que cada pixel é representado por um único bit, 0 ou 1. Esse formato é altamente eficiente em termos de espaço, o que o torna ideal para arquivamento.

### Posso converter várias páginas de um documento do Word de uma só vez?
Sim! Basta modificar o `PageSet` propriedade no `ImageSaveOptions` para incluir várias páginas ou configurá-lo para converter o documento inteiro.

### Preciso de uma licença para usar o Aspose.Words para .NET?
Sim, é necessária uma licença para a funcionalidade completa. Você pode obter uma [licença temporária aqui](https://purchase.aspose.com/temporary-license/).

### Para quais outros formatos de imagem posso converter meu documento do Word?
O Aspose.Words suporta vários formatos, incluindo JPEG, BMP e TIFF. Basta alterar o `SaveFormat` no `ImageSaveOptions` para o formato desejado.

### Onde posso encontrar mais documentação sobre o Aspose.Words para .NET?
Para documentação completa, visite o [Página de documentação do Aspose.Words para .NET](https://reference.aspose.com/words/net/).