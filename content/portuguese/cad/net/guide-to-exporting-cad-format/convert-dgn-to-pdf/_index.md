---
"description": "Aprenda a converter arquivos DGN para PDF sem esforço usando a poderosa biblioteca Aspose.CAD para .NET. Este guia passo a passo foi desenvolvido para desenvolvedores de todos os níveis."
"linktitle": "Converter DGN para PDF no Aspose.CAD para .NET"
"second_title": "Aspose.CAD .NET - Formato de arquivo CAD e BIM"
"title": "Converter DGN para PDF no Aspose.CAD para .NET"
"url": "/pt/cad/net/guide-to-exporting-cad-format/convert-dgn-to-pdf/"
"weight": 12
---

## Introdução

Navegar pelo mundo dos arquivos CAD pode ser desafiador, mas com o Aspose.CAD para .NET, os desenvolvedores podem manipular e converter facilmente vários formatos CAD. Uma necessidade comum é converter arquivos DGN para PDFs, que exploraremos passo a passo neste tutorial.

## Pré-requisitos

Para acompanhar, certifique-se de ter o seguinte:

- Proficiência básica em C# e no framework .NET.
- Biblioteca Aspose.CAD para .NET instalada. Você pode baixá-la [aqui](https://releases.aspose.com/cad/net/).
- Um arquivo DGN de amostra (por exemplo, Nikon_D90_Camera.dgn). 

## Etapa 1: Importar os namespaces necessários

Comece importando os namespaces relevantes no seu projeto C#:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Etapa 2: Carregue o arquivo DGN

Especifique o diretório para seu arquivo DGN e carregue-o usando o seguinte código:

```csharp
string myDir = "Your Document Directory";
string sourceFilePath = myDir + "Nikon_D90_Camera.dgn";

using (DgnImage cadImage = (DgnImage)Image.Load(sourceFilePath))
{
    // Processamento adicional ocorrerá aqui...
}
```

## Etapa 3: Configurar opções de rasterização

Em seguida, configure as opções de rasterização para definir como seu DGN será renderizado no PDF:

```csharp
CadRasterizationOptions rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 600, // Ajuste a largura conforme necessário
    PageHeight = 300, // Ajuste a altura conforme necessário
    NoScaling = true,
    AutomaticLayoutsScaling = false
};
```

## Etapa 4: Criar opções de PDF

Defina as opções de PDF, integrando as configurações de rasterização configuradas anteriormente:

```csharp
PdfOptions pdfOptions = new PdfOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Etapa 5: Salve o DGN como PDF

Por fim, salve o arquivo DGN como PDF usando as opções que você configurou:

```csharp
cadImage.Save(myDir + "ExportDGNToPdf_out.pdf", pdfOptions);
```

## Conclusão

Parabéns! Você converteu com sucesso um arquivo DGN em PDF usando o Aspose.CAD para .NET. Este tutorial simples o guiou pelo carregamento do arquivo DGN, configuração das opções de rasterização e salvamento do resultado como PDF.

## Perguntas frequentes

### Preciso de conhecimento prévio de CAD para usar o Aspose.CAD?  
Com certeza! O Aspose.CAD foi projetado para simplificar tarefas complexas de CAD, tornando-o acessível a todos os desenvolvedores, independentemente do seu conhecimento em CAD.

### Onde posso encontrar mais recursos e documentação para o Aspose.CAD?  
Você pode explorar guias e exemplos abrangentes no [Documentação do Aspose.CAD](https://reference.aspose.com/cad/net/).

### Existe uma versão de teste gratuita disponível para o Aspose.CAD?  
Sim, um teste gratuito pode ser obtido [aqui](https://releases.aspose.com/).

### Como posso obter uma licença temporária para o Aspose.CAD?  
Você pode solicitar licenças temporárias [aqui](https://purchase.conholdate.com/temporary-license/).

### Precisa de ajuda ou tem dúvidas?  
Junte-se à conversa no [Fórum Aspose.CAD](https://forum.aspose.com/c/cad/19) para suporte e consultas da comunidade.