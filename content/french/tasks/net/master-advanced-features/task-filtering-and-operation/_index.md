---
"description": "Découvrez comment exploiter la classe Aspose.Tasks pour .NET pour filtrer les tâches d'un projet selon plusieurs conditions, en combinant des critères tels que les tâches récapitulatives et les attributs non nuls."
"linktitle": "Filtrage des tâches et fonctionnement dans Aspose.Tasks"
"second_title": "API .NET Aspose.Tasks"
"title": "Filtrage des tâches et fonctionnement dans Aspose.Tasks"
"url": "/fr/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Introduction

Dans ce tutoriel, nous allons explorer comment effectuer un filtrage avancé des tâches de projet dans Aspose.Tasks pour .NET en utilisant le `Util.And` classe. Cette fonctionnalité puissante permet aux développeurs de filtrer efficacement les tâches en fonction de plusieurs critères.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

1. Connaissances de base de la programmation C#.
2. Aspose.Tasks pour .NET est installé. Si ce n'est pas déjà fait, vous pouvez le télécharger ici. [ce lien](https://releases.aspose.com/tasks/net/).
3. Un environnement de développement intégré (IDE) comme Visual Studio pour écrire et exécuter le code.

## Importation d'espaces de noms

Pour commencer, vous devez importer les espaces de noms requis dans votre projet C#. Cela vous permettra d'accéder aux fonctionnalités d'Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Étape 1 : Initialiser le projet et collecter les tâches

Commencez par initialiser un projet Aspose.Tasks et regroupez toutes les tâches qu'il contient. À des fins de démonstration, nous supposerons qu'il existe un fichier projet nommé `Project2.mpp`.

```csharp
// Chemin vers le répertoire des documents
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Collecter toutes les tâches des enfants
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Étape 2 : Définir les conditions de filtrage

Dans cette étape, nous allons définir les conditions de filtrage des tâches. Dans notre exemple, nous allons créer deux conditions : une pour filtrer les tâches récapitulatives et une autre pour garantir que les tâches ne sont pas nulles.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Étape 3 : Combiner les conditions avec l'opération ET

L'étape suivante consiste à combiner ces conditions en utilisant le `Util.And` classe. Cela nous permet de créer une condition composite qui impose les deux critères.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Étape 4 : Appliquer les tâches combinées de condition et de filtrage

Appliquons maintenant la condition combinée aux tâches collectées pour filtrer les tâches spécifiques qui répondent aux deux conditions.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Étape 5 : Générer les tâches filtrées

Enfin, nous parcourrons nos tâches filtrées et afficherons les détails pertinents. Cela nous aidera à identifier les tâches qui répondent à nos critères.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Conclusion

Dans ce tutoriel, nous avons montré comment effectuer des opérations de filtrage avancées dans Aspose.Tasks pour .NET à l'aide de `Util.And` classe. En combinant plusieurs conditions, nous pouvons filtrer efficacement les tâches, améliorant ainsi l'utilité de nos applications de gestion de projet.

## FAQ

### Qu'est-ce qu'Aspose.Tasks pour .NET ?

Aspose.Tasks pour .NET est une API complète conçue pour permettre aux développeurs de manipuler les fichiers Microsoft Project par programmation dans les applications .NET.

### Puis-je combiner plus de deux conditions en utilisant Util.And ?

Oui! Le `Util.And` La classe vous permet de combiner plusieurs conditions, permettant une logique de filtrage complexe adaptée à vos besoins.

### Existe-t-il une version d'essai gratuite disponible pour Aspose.Tasks ?

Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ce lien](https://releases.aspose.com/).

### Où puis-je trouver une documentation détaillée pour Aspose.Tasks ?

Une documentation détaillée est disponible [ici](https://reference.aspose.com/tasks/net/).

### Comment puis-je demander de l'aide pour Aspose.Tasks ?

L'assistance est disponible via le forum communautaire Aspose.Tasks, accessible [ici](https://forum.aspose.com/c/tasks/15).