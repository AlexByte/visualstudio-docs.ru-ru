---
title: DBGPROP_INFO_FLAGS | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DBGPROP_INFO_FLAGS
apilocation:
- scrobj.dll
f1_keywords:
- DBGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS
ms.assetid: e9450a21-a802-4c3e-8b3d-8e202f555de1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 517999bce9c85475bd91ad2e54e7ed49cda23aab
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095762"
---
# <a name="dbgpropinfoflags"></a>DBGPROP_INFO_FLAGS
Используется для указания `DebugPropertyInfo` поля  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
enum {  
   DBGPROP_INFO_NAME  =0x001,  
   DBGPROP_INFO_TYPE  =0x002,  
   DBGPROP_INFO_VALUE  =0x004,  
   DBGPROP_INFO_FULLNAME  =0x020,  
   DBGPROP_INFO_ATTRIBUTES  =0x008,  
   DBGPROP_INFO_DEBUGPROP  =0x010,  
   DBGPROP_INFO_AUTOEXPAND  =0x8000000  
};  
```  
  
## <a name="members"></a>Члены  
 DBGPROP_INFO_NAME  
 Инициализирует `bstrName` поля.  
  
 DBGPROP_INFO_TYPE  
 Инициализирует `bstrType` поля.  
  
 DBGPROP_INFO_VALUE  
 Инициализирует `bstrValue` поля.  
  
 DBGPROP_INFO_FULLNAME  
 Инициализирует `bstrFullName` поля.  
  
 DBGPROP_INFO_ATTRIBUTES  
 Инициализирует `dwAttrib` поля.  
  
 DBGPROP_INFO_DEBUGPROP  
 Инициализирует `pDebugProp` поле, содержащее `IDebugProperty` интерфейс.  
  
 DBGPROP_INFO_AUTOEXPAND  
 Указывает, что поле значения должен содержать значение развернутый автоматически, если он доступен для этого типа объектов.  
  
## <a name="see-also"></a>См. также  
 [Структура DebugPropertyInfo](../../winscript/reference/debugpropertyinfo-structure.md)   
 [Интерфейс IDebugProperty](../../winscript/reference/idebugproperty-interface.md)