---
title: Задача GetFrameworkPath | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkPath task [MSBuild]
- MSBuild, GetFrameworkPath task
ms.assetid: 5b7bcdd7-d4a0-442d-af29-8aadb3b10598
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dcad656c058fffaf3f075b195cb1f105079a8e5d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49248603"
---
# <a name="getframeworkpath-task"></a>Задача GetFrameworkPath
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Извлекает путь к сборкам [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].  
  
## <a name="task-parameters"></a>Параметры задачи  
 В следующей таблице приводятся параметры задачи `GetFrameworkPath`.  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`FrameworkVersion11Path`|Необязательный выходной параметр `String`.<br /><br /> Содержит путь к сборкам платформы .NET Framework версии 1.1, если они есть. В противном случае возвращает значение `null`.|  
|`FrameworkVersion20Path`|Необязательный выходной параметр `String`.<br /><br /> Содержит путь к сборкам платформы .NET Framework версии 2.0, если они есть. В противном случае возвращает значение `null`.|  
|`FrameworkVersion30Path`|Необязательный выходной параметр `String`.<br /><br /> Содержит путь к сборкам платформы .NET Framework версии 3.0, если они есть. В противном случае возвращает значение `null`.|  
|`FrameworkVersion35Path`|Необязательный выходной параметр `String`.<br /><br /> Содержит путь к сборкам платформы .NET Framework версии 3.5, если они есть. В противном случае возвращает значение `null`.|  
|`FrameworkVersion40Path`|Необязательный выходной параметр `String`.<br /><br /> Содержит путь к сборкам платформы .NET Framework версии 4.0, если они есть. В противном случае возвращает значение `null`.|  
|`Path`|Необязательный выходной параметр `String`.<br /><br /> Содержит путь к самым новым сборкам платформы, если они есть. В противном случае возвращает значение `null`.|  
  
## <a name="remarks"></a>Примечания  
 Если установлено несколько версий [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], эта задача возвращает версию, для которой предназначен [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].  
  
 Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример использует задачу `GetFrameworkPath` для сохранения пути к [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] в свойстве `FrameworkPath`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="FrameworkPath" />  
        </GetFrameworkPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>См. также  
 [Задачи](../msbuild/msbuild-tasks.md)   
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)



