---
title: Задача GetReferenceAssemblyPaths | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 485b8f9c19a8a91d686b603ee1be9da70b6c78e1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987879"
---
# <a name="getreferenceassemblypaths-task"></a>Задача GetReferenceAssemblyPaths
Возвращает пути к эталонным сборкам для различных версий .NET Framework.  
  
## <a name="parameters"></a>Параметры  
 В следующей таблице приводятся параметры задачи `GetReferenceAssemblyPaths` .  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`ReferenceAssemblyPaths`|Необязательный выходной параметр `String[]`.<br /><br /> Возвращает путь на основе параметра `TargetFrameworkMoniker`. Если `TargetFrameworkMoniker` равен NULL или пуст, этот путь имеет значение `String.Empty`.|  
|`FullFrameworkReferenceAssemblyPaths`|Необязательный выходной параметр `String[]`.<br /><br /> Возвращает путь на основе параметра `TargetFrameworkMoniker` без учета профильной части моникера. Если `TargetFrameworkMoniker` равен NULL или пуст, этот путь имеет значение `String.Empty`.|  
|`TargetFrameworkMoniker`|Необязательный параметр `String` .<br /><br /> Указывает моникер целевой платформы, связанный с путями базовых сборок.|  
|`RootPath`|Необязательный параметр `String` .<br /><br /> Указывает корневой путь, используемый для создания пути базовой сборки.|  
|`BypassFrameworkInstallChecks`|Необязательный параметр <xref:System.Boolean> .<br /><br /> Если задано значение `true`, обходит основные проверки, которые `GetReferenceAssemblyPaths` выполняет по умолчанию, чтобы убедиться в установке определенных платформ среды выполнения, в зависимости от целевой платформы.|  
|`TargetFrameworkMonikerDisplayName`|Необязательный выходной параметр `String`.<br /><br /> Задает отображаемое имя для моникера целевой платформы.|  
  
## <a name="remarks"></a>Примечания  
 Помимо параметров, перечисленных в таблице, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который сам является производным от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>См. также  
 [Задачи](../msbuild/msbuild-tasks.md)   
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)