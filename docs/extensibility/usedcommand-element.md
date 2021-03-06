---
title: Элемент UsedCommand | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6ccc96d92e83ea42c6921abd2159499c1e9c42c4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54930359"
---
# <a name="usedcommand-element"></a>Элемент UsedCommand
Позволяет VSPackage для доступа к команде, которая определена в другом vsct-файл. Например, если VSPackage использует стандарт **копирования** команду, которая определяется [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] оболочки, можно добавить команду в меню или панели инструментов без повторной реализации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|guid|Обязательный. Идентификатор GUID пары идентификатор GUID, который определяет команду.|  
|id|Обязательный. Идентификатор пары идентификатор GUID, который определяет команду.|  
|Условие|Необязательный параметр. См. в разделе [условные атрибуты](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|Нет||  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Элемент UsedCommands](../extensibility/usedcommands-element.md)|Группирует элементы UsedCommand и другими признаками UsedCommands.|  
  
## <a name="remarks"></a>Примечания  
 Добавив команду, чтобы `<UsedCommands>` элемента, сообщает VSPackage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] среды, что VSPackage требует команды. Следует добавить `<UsedCommand>` элемент для любой команды, пакет необходимо, не могут быть включены во все версии и конфигурации из Visual Studio. Например, если пакет вызывает команду, которая используется только в Visual C++, команда не будет доступна пользователям Visual Web Developer Если не включить `<UsedCommand>` элемента для команды.  
  
## <a name="example"></a>Пример  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>См. также  
 [Элемент UsedCommands](../extensibility/usedcommands-element.md)   
 [Файлы таблицы команд Visual Studio (VSCT-файлы)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)