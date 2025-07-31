---
"description": "Ismerd meg, hogyan használhatod ki az Aspose.Tasks .NET osztályát projektfeladatok szűrésére több feltétel alapján. Olyan kritériumok kombinálásával, mint az összefoglaló feladatok és a nem null attribútumok."
"linktitle": "Feladatszűrés ÉS művelet az Aspose.Tasks-ban"
"second_title": "Aspose.Tasks .NET API"
"title": "Feladatszűrés ÉS művelet az Aspose.Tasks-ban"
"url": "/hu/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Bevezetés

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan lehet az Aspose.Tasks for .NET projektfeladatok speciális szűrését elvégezni a következő használatával: `Util.And` osztály. Ez a hatékony funkció lehetővé teszi a fejlesztők számára, hogy hatékonyan szűrjék a feladatokat több kritérium alapján.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg arról, hogy a következőkkel rendelkezünk:

1. C# programozási alapismeretek.
2. Aspose.Tasks for .NET telepítve. Ha még nem tette meg, letöltheti innen: [ezt a linket](https://releases.aspose.com/tasks/net/).
3. Egy integrált fejlesztői környezet (IDE), mint például a Visual Studio, a kód írásához és futtatásához.

## Névterek importálása

A kezdéshez importálnia kell a szükséges névtereket a C# projektjébe. Ez lehetővé teszi az Aspose.Tasks által biztosított funkciók elérését.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## 1. lépés: A projekt inicializálása és a feladatok összegyűjtése

Először inicializálj egy Aspose.Tasks projektet, és gyűjtsd össze benne az összes feladatot. A demonstráció kedvéért feltételezzük, hogy van egy projektfájl, melynek neve `Project2.mpp`.

```csharp
// A dokumentumok könyvtárának elérési útja
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Gyűjtsd össze az összes alárendelt feladatot
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## 2. lépés: Szűrési feltételek meghatározása

Ebben a lépésben a feladatok szűrésének feltételeit fogjuk meghatározni. A példánkban két feltételt hozunk létre: az egyik az összefoglaló feladatok szűrésére szolgál, a másik pedig biztosítja, hogy a feladatok ne legyenek üresek.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## 3. lépés: Feltételek kombinálása az ÉS művelettel

A következő lépés ezen feltételek kombinálása a következő használatával: `Util.And` osztály. Ez lehetővé teszi számunkra, hogy egy összetett feltételt hozzunk létre, amely mindkét kritériumot előírja.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## 4. lépés: Alkalmazza a kombinált feltétel- és szűrőfeladatokat

Most alkalmazzuk az összegyűjtött feladatokra a kombinált feltételt, hogy kiszűrjük azokat a konkrét feladatokat, amelyek mindkét feltételnek megfelelnek.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## 5. lépés: A szűrt feladatok kimenete

Végül végigmegyünk a szűrt feladatainkon, és releváns részleteket adunk ki. Ez segít megérteni, hogy mely feladatok felelnek meg a kritériumainknak.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan végezhetünk speciális szűrési műveleteket az Aspose.Tasks for .NET-ben a következő használatával: `Util.And` osztály. Több feltétel kombinálásával hatékonyan szűrhetjük a feladatokat, ezáltal növelve projektmenedzsment alkalmazásaink hasznosságát.

## GYIK

### Mi az Aspose.Tasks .NET-hez?

Az Aspose.Tasks for .NET egy átfogó API, amelyet a fejlesztők számára terveztek a Microsoft Project fájlok programozott kezeléséhez a .NET alkalmazásokon belül.

### Kombinálhatok kettőnél több feltételt az Util.And használatával?

Igen! A `Util.And` Az osztály lehetővé teszi több feltétel kombinálását, lehetővé téve az Ön igényeire szabott komplex szűrési logikát.

### Van ingyenes próbaverzió az Aspose.Tasks-hoz?

Igen, letölthet egy ingyenes próbaverziót innen [ezt a linket](https://releases.aspose.com/).

### Hol találok részletes dokumentációt az Aspose.Tasks-hoz?

Részletes dokumentáció elérhető [itt](https://reference.aspose.com/tasks/net/).

### Hogyan kérhetek támogatást az Aspose.Tasks-hoz?

A támogatás az Aspose.Tasks közösségi fórumon keresztül érhető el, amely a következő címen érhető el: [itt](https://forum.aspose.com/c/tasks/15).