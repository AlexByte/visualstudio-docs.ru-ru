---
title: Метаданные элементов в пакетной обработке задач | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
- task batching [MSBuild]
- MSBuild, task batching
ms.assetid: 31e480f8-fe4d-4633-8c54-8ec498e2306d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 38f8691cc7b1b102b0d1747d8bd9a94411608f22
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891418"
---
# <a name="item-metadata-in-task-batching"></a>Метаданные элементов в пакетной обработке задач
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] может разделять списки элементов на разные категории или пакеты на основе метаданных элементов и поочередно выполнять задачи с использованием каждого пакета. Не так просто понять, какие именно элементы передаются с каким пакетом. В этом разделе рассматриваются наиболее распространенные сценарии, в которых используется пакетная обработка.  
  
-   Разделение списка элементов на пакеты  
  
-   Деление нескольких списков элементов на пакеты  
  
-   Пакетная обработка одного элемента за раз  
  
-   Фильтрация списков элементов  

Дополнительные сведения о пакетной обработке с помощью [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] см. в статье [Пакетная обработка в MSBuild](../msbuild/msbuild-batching.md).  
  
## <a name="divide-an-item-list-into-batches"></a>Разделение списка элементов на пакеты  
 Пакетная обработка позволяет разделить список элементов на различные пакеты на основе метаданных элементов и передать задаче каждый из пакетов отдельно. Это полезно при создании вспомогательных сборок.  
  
 В следующем примере показано, как разделить список элементов на пакеты на основе метаданных элементов. Список элементов `ExampColl` делится на три пакета на основе метаданных элементов `Number`. Если в атрибуте `Text` есть `%(ExampColl.Number)`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] получает уведомление о том, что необходимо выполнить пакетную обработку. Список элементов `ExampColl` делится на три пакета на основе метаданных `Number`, а каждый пакет отдельно передается задаче.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
        <ExampColl Include="Item4">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item5">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item6">  
            <Number>3</Number>  
        </ExampColl>  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Number: %(ExampColl.Number) -- Items in ExampColl: @(ExampColl)"/>  
    </Target>  
  
</Project>  
```  

[Задача Message](../msbuild/message-task.md) отображает следующие сведения:  
  
 `Number: 1 -- Items in ExampColl: Item1;Item4`  
  
 `Number: 2 -- Items in ExampColl: Item2;Item5`  
  
 `Number: 3 -- Items in ExampColl: Item3;Item6`  
  
## <a name="divide-several-item-lists-into-batches"></a>Разделение списка элементов на пакеты  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] может разделить несколько списков элементов на пакеты на основе одинаковых метаданных. Это упрощает деление различных списков элементов на пакеты для создания нескольких сборок. Например, у вас может быть список элементов с *CS*-файлами, разделенный на пакет приложения и пакет сборки, и список элементов с файлами ресурсов, разделенный на пакет приложения и пакет сборки. Затем, используя пакетную обработку, можно передать эти списки элементов одной задаче и создать приложение и сборку.  
  
> [!NOTE]
>  Если в передаваемом задаче списке элементов нет элементов с указанными метаданными, каждый элемент из этого списка передается во все пакеты.  
  
В следующем примере показано, как разделить несколько списков элементов на пакеты на основе метаданных элементов. Списки элементов `ExampColl` и `ExampColl2` делятся на три пакета на основе метаданных элементов `Number`. Если в атрибуте `Text` есть `%(Number)`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] получает уведомление о том, что необходимо выполнить пакетную обработку. Списки элементов `ExampColl` и `ExampColl2` делятся на три пакета на основе метаданных `Number`, а каждый пакет отдельно передается задаче.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
  
        <ExampColl2 Include="Item4">  
            <Number>1</Number>  
        </ExampColl2>  
        <ExampColl2 Include="Item5">  
            <Number>2</Number>  
        </ExampColl2>  
        <ExampColl2 Include="Item6">  
            <Number>3</Number>  
        </ExampColl2>  
  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Number: %(Number) -- Items in ExampColl: @(ExampColl) ExampColl2: @(ExampColl2)"/>  
    </Target>  
  
</Project>  
```  
  
[Задача Message](../msbuild/message-task.md) отображает следующие сведения:  
  
 `Number: 1 -- Items in ExampColl: Item1 ExampColl2: Item4`  
  
 `Number: 2 -- Items in ExampColl: Item2 ExampColl2: Item5`  
  
 `Number: 3 -- Items in ExampColl: Item3 ExampColl2: Item6`  
  
## <a name="batch-one-item-at-a-time"></a>Пакетная обработка одного элемента за раз  
 Пакетная обработка может также выполняться со стандартными метаданными, назначенными каждому элементу при создании. Это гарантирует, что каждый элемент в коллекции будет содержать некоторые метаданные для пакетной обработки. Значение метаданных `Identity` уникально для каждого элемента и используется для его выделения из списка элементов в отдельный пакет. Полный список стандартных метаданных элементов см. в статье [Стандартные метаданные элементов](../msbuild/msbuild-well-known-item-metadata.md).  
  
 Следующий пример демонстрирует поочередную пакетную обработку каждого элемента из списка элементов. Так как значение метаданных `Identity` каждого элемента является уникальным, список элементов `ExampColl` делится на шесть пакетов, каждый из которых содержит один элемент из списка элементов. Если в атрибуте `Text` есть `%(Identity)`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] получает уведомление о том, что необходимо выполнить пакетную обработку.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1"/>  
        <ExampColl Include="Item2"/>  
        <ExampColl Include="Item3"/>  
        <ExampColl Include="Item4"/>  
        <ExampColl Include="Item5"/>  
        <ExampColl Include="Item6"/>  
  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Identity: "%(Identity)" -- Items in ExampColl: @(ExampColl)"/>  
    </Target>  
  
</Project>  
```  
  
[Задача Message](../msbuild/message-task.md) отображает следующие сведения:  
  
```  
Identity: "Item1" -- Items in ExampColl: Item1  
Identity: "Item2" -- Items in ExampColl: Item2  
Identity: "Item3" -- Items in ExampColl: Item3  
Identity: "Item4" -- Items in ExampColl: Item4  
Identity: "Item5" -- Items in ExampColl: Item5  
Identity: "Item6" -- Items in ExampColl: Item6  
```  
  
## <a name="filter-item-lists"></a>Списки элементов фильтра  
 Пакетную обработку можно использовать для фильтрации определенных элементов из списка элементов перед их передачей задаче. Например, фильтрация по значению известных метаданных элементов `Extension` позволяет выполнить задачу только для файлов с определенным расширением.  
  
 В приведенном ниже примере показано, как разделить список элементов на пакеты на основе метаданных элементов, а затем отфильтровать эти пакеты при передаче их задаче. Список элементов `ExampColl` делится на три пакета на основе метаданных элементов `Number`. Атрибут задачи `Condition` указывает, что задаче будут переданы только пакеты со значением метаданных элемента `Number` равным `2`.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
        <ExampColl Include="Item4">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item5">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item6">  
            <Number>3</Number>  
        </ExampColl>  
  
    </ItemGroup>  
  
    <Target Name="Exec">  
        <Message  
            Text = "Items in ExampColl: @(ExampColl)"  
            Condition="'%(Number)'=='2'"/>  
    </Target>  
  
</Project>  
```  
  
[Задача Message](../msbuild/message-task.md) отображает следующие сведения:  
  
```  
Items in ExampColl: Item2;Item5  
```  
  
## <a name="see-also"></a>См. также  
 [Стандартные метаданные элементов](../msbuild/msbuild-well-known-item-metadata.md)   
 [Элемент Item (MSBuild)](../msbuild/item-element-msbuild.md)   
 [Элемент ItemMetadata (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Пакетная обработка](../msbuild/msbuild-batching.md)   
 [Основные понятия MSBuild](../msbuild/msbuild-concepts.md)   
 [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md)
