---
"description": "Aprenda a utilizar a classe Aspose.Tasks para .NET para filtrar tarefas de projeto com base em múltiplas condições, combinando critérios como tarefas de resumo e atributos não nulos."
"linktitle": "Filtragem de tarefas E operação em Aspose.Tasks"
"second_title": "API Aspose.Tasks .NET"
"title": "Filtragem de tarefas E operação em Aspose.Tasks"
"url": "/pt/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Introdução

Neste tutorial, exploraremos como executar filtragem avançada de tarefas de projeto no Aspose.Tasks para .NET utilizando o `Util.And` classe. Este poderoso recurso permite que os desenvolvedores filtrem tarefas com base em múltiplos critérios de forma eficiente.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Conhecimento básico de programação em C#.
2. Aspose.Tasks para .NET instalado. Se ainda não o fez, pode baixá-lo em [este link](https://releases.aspose.com/tasks/net/).
3. Um ambiente de desenvolvimento integrado (IDE) como o Visual Studio para escrever e executar o código.

## Importando namespaces

Para começar, você precisa importar os namespaces necessários para o seu projeto C#. Isso permitirá que você acesse as funcionalidades fornecidas pelo Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Etapa 1: Inicializar o Projeto e Coletar Tarefas

Primeiro, inicialize um projeto Aspose.Tasks e reúna todas as tarefas nele contidas. Para fins de demonstração, vamos supor que exista um arquivo de projeto chamado `Project2.mpp`.

```csharp
// Caminho para o diretório de documentos
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Coletar todas as tarefas infantis
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Etapa 2: Definir condições de filtro

Nesta etapa, definiremos as condições para filtrar tarefas. No nosso exemplo, criaremos duas condições: uma para filtrar tarefas de resumo e outra para garantir que as tarefas não sejam nulas.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Etapa 3: Combine as condições com a operação AND

O próximo passo é combinar essas condições usando o `Util.And` classe. Isso nos permite criar uma condição composta que exige ambos os critérios.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Etapa 4: aplicar as tarefas de condição combinada e filtro

Agora, vamos aplicar a condição combinada às tarefas coletadas para filtrar as tarefas específicas que atendem a ambas as condições.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Etapa 5: Gerar as tarefas filtradas

Por fim, iteraremos pelas tarefas filtradas e geraremos detalhes relevantes. Isso nos ajudará a entender as tarefas que atendem aos nossos critérios.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Conclusão

Neste tutorial, demonstramos como executar operações de filtragem avançadas no Aspose.Tasks para .NET usando o `Util.And` classe. Ao combinar múltiplas condições, podemos filtrar tarefas com eficácia, aumentando assim a utilidade de nossos aplicativos de gerenciamento de projetos.

## Perguntas frequentes

### O que é Aspose.Tasks para .NET?

Aspose.Tasks para .NET é uma API abrangente projetada para desenvolvedores manipularem arquivos do Microsoft Project programaticamente em aplicativos .NET.

### Posso combinar mais de duas condições usando Util.And?

Sim! O `Util.And` A classe permite que você combine diversas condições, possibilitando uma lógica de filtragem complexa adaptada às suas necessidades.

### Existe uma versão de teste gratuita disponível para o Aspose.Tasks?

Sim, você pode baixar uma versão de teste gratuita em [este link](https://releases.aspose.com/).

### Onde posso encontrar documentação detalhada do Aspose.Tasks?

Documentação detalhada está disponível [aqui](https://reference.aspose.com/tasks/net/).

### Como posso buscar suporte para o Aspose.Tasks?

O suporte está disponível através do fórum da comunidade Aspose.Tasks, que pode ser acessado [aqui](https://forum.aspose.com/c/tasks/15).