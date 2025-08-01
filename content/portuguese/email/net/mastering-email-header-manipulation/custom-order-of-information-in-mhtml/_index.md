---
"description": "Aprenda como definir a ordem de informações personalizada em MHTML usando o Aspose.Email para .NET neste tutorial passo a passo."
"linktitle": "Ordem personalizada de informações em MHTML com Aspose.Email"
"second_title": "API de processamento de e-mail Aspose.Email .NET"
"title": "Ordem personalizada de informações em MHTML com Aspose.Email"
"url": "/pt/email/net/mastering-email-header-manipulation/custom-order-of-information-in-mhtml/"
"weight": 14
---

## Introdução

Criar formatos de e-mail avançados pode melhorar muito a comunicação, especialmente ao exportar e-mails para diferentes formatos de arquivo, como MHTML. O Aspose.Email para .NET oferece aos desenvolvedores um poderoso kit de ferramentas para manipular e-mails, o que inclui definir uma ordem personalizada de exibição das informações ao exportar para MHTML. Neste guia, detalharemos as etapas necessárias para isso, facilitando o acompanhamento, seja você um desenvolvedor experiente ou iniciante. Então, vamos direto ao assunto!

## Pré-requisitos

Antes de começar a definir a ordem personalizada das informações em MHTML, há alguns pré-requisitos que você precisa verificar na sua lista:

1. Ambiente de desenvolvimento .NET: certifique-se de ter um ambiente de desenvolvimento .NET configurado. Você pode usar o Visual Studio, o Visual Studio Code ou qualquer outro IDE compatível.

2. Biblioteca Aspose.Email: Você precisa ter a biblioteca Aspose.Email para .NET instalada. Você pode baixar a versão mais recente em [Página de lançamentos do Aspose](https://releases.aspose.com/email/net/).

3. Noções básicas de C#: a familiaridade com a programação em C# ajudará você a entender melhor o código.

4. Arquivo de e-mail de exemplo: você precisará de um exemplo `.eml` arquivo (por exemplo, `Attachments.eml`) para fins de teste.

Depois de atender a esses pré-requisitos, você estará pronto para seguir o tutorial!

## Pacotes de importação

Para começar a usar seu código, você precisará importar os namespaces necessários da biblioteca Aspose.Email. Isso é essencial para acessar todas as classes e métodos necessários para manipular arquivos de e-mail.

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;
```

Inclua-os no início do seu arquivo C#. Agora você está pronto para começar a programar!

Agora que você configurou tudo, vamos dividir o tutorial em etapas mais fáceis de gerenciar.

## Etapa 1: defina seu diretório de dados

A primeira coisa a fazer é definir um diretório onde seus arquivos de e-mail serão armazenados. Pode ser qualquer caminho na sua máquina local.

```csharp
string dataDir = "Your Data Directory";
```

Substituir `"Your Data Directory"` com o caminho real onde seu `.eml` o arquivo está localizado. Por exemplo, se o seu arquivo estiver em `C:\Emails`, você escreveria:

```csharp
string dataDir = @"C:\Emails\";
```

## Etapa 2: Carregue a mensagem de e-mail

Em seguida, você precisa carregar o `.eml` arquivar em um `MailMessage` objeto. Isso permite que você manipule o conteúdo e os metadados do e-mail.

```csharp
MailMessage eml = MailMessage.Load(dataDir + "Attachments.eml");
```

Certifique-se de que o nome do arquivo corresponda ao que você tem no diretório especificado. Se o seu arquivo tiver um nome diferente, atualize-o de acordo.

## Etapa 3: Configurar opções de salvamento MHTML

Com seu e-mail carregado, é hora de definir como você deseja salvá-lo como MHTML. Você pode começar com as opções padrão.

```csharp
MhtSaveOptions opt = SaveOptions.DefaultMhtml;
```

Esta linha inicializa as opções de salvamento do MHTML, preparando o cenário para a personalização posterior dos cabeçalhos.

## Etapa 4: salvar MHTML com ordem padrão

Vamos salvar o e-mail como MHTML usando a ordem padrão. Isso lhe dará uma base para comparação após a personalização.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_1.mhtml", opt);
```

Execute esta linha e verifique o diretório especificado. Agora você deverá ver um novo arquivo MHTML chamado `CustomOrderOfInformationInMHTML_1.mhtml`. Abra-o para ver como as informações são exibidas por padrão.

## Etapa 5: personalizar a ordem do cabeçalho

Agora vem a parte divertida! Você pode especificar quais cabeçalhos incluir na saída MHTML e em que ordem. Começaremos com alguns cabeçalhos comuns.

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.From);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
opt.RenderingHeaders.Add(MhtTemplateName.To);
opt.RenderingHeaders.Add(MhtTemplateName.Sent);
```

Ao adicionar esses cabeçalhos, você está dizendo ao Aspose como gostaria que o e-mail fosse exibido.

## Etapa 6: Salvar MHTML com pedido personalizado

Depois de personalizar os cabeçalhos, você precisa salvar o e-mail novamente como MHTML para ver como a nova ordem afeta a saída.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_2.mhtml", opt);
```

Execute este código e abra `CustomOrderOfInformationInMHTML_2.mhtml`. Compare-o com o primeiro para ver como as informações mudaram com base na ordem do seu cabeçalho.

## Etapa 7: Limpar e adicionar nova ordem de cabeçalho

se você quiser uma ordem totalmente diferente? Você pode começar do zero limpando as configurações de cabeçalho existentes.

```csharp
opt.RenderingHeaders.Clear();
```

Agora é hora de definir uma nova ordem para os cabeçalhos. Por exemplo, se você quiser priorizar anexos e copiar destinatários:

```csharp
opt.RenderingHeaders.Add(MhtTemplateName.Attachments);
opt.RenderingHeaders.Add(MhtTemplateName.Cc);
opt.RenderingHeaders.Add(MhtTemplateName.Subject);
```

## Etapa 8: Salvar MHTML com novo pedido personalizado

Por fim, salve o e-mail uma última vez com as novas configurações de cabeçalho.

```csharp
eml.Save(dataDir + "CustomOrderOfInformationInMHTML_3.mhtml", opt);
```

Depois de executar esta linha, abra `CustomOrderOfInformationInMHTML_3.mhtml` e verifique como ele apresenta as informações com base na sua nova personalização.

## Conclusão

E aí está — um guia simples para definir uma ordem personalizada de informações em MHTML usando o Aspose.Email para .NET. Seguindo esses passos, você pode controlar como seus e-mails são representados no formato MHTML, garantindo que as informações mais importantes sejam apresentadas de uma forma que atenda às suas necessidades. 

## Perguntas frequentes

### O que é MHTML?
MHTML significa "MIME HTML", um formato de arquivo de página da web que combina HTML e outros recursos, como imagens.

### Posso usar o Aspose.Email gratuitamente?
Sim, o Aspose oferece uma versão de teste gratuita para desenvolvedores explorarem. Você pode encontrá-la [aqui](https://releases.aspose.com/).

### E se eu tiver problemas ao usar o Aspose.Email?
Você pode obter suporte da comunidade por meio do [Fórum Aspose](https://forum.aspose.com/c/email/12/).

### Existe uma licença temporária disponível para o Aspose.Email?
Sim, você pode solicitar uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso comprar o Aspose.Email?
Você pode comprar a biblioteca aqui [link](https://purchase.aspose.com/buy).