---
title: PROGRAM_NODE_ARRAY | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- PROGRAM_NODE_ARRAY
helpviewer_keywords:
- PROGRAM_NODE_ARRAY structure
ms.assetid: 8eeea600-eda5-4b7c-868a-0b86d177b0a5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2ebdb40634deea9c1a2362e6027ea6d6ae5117ff
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54934027"
---
# <a name="programnodearray"></a>PROGRAM_NODE_ARRAY
Содержит массив объектов, описывающих программы интерес.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct tagPROGRAM_NODE_ARRAY {  
   DWORD                dwCount;  
   IDebugProgramNode2** Members;  
} PROGRAM_NODE_ARRAY;  
```  
  
```csharp  
public struct tagPROGRAM_NODE_ARRAY {  
   public uint                 dwCount;  
   public IDebugProgramNode2[] Members;  
}  
```  
  
## <a name="members"></a>Участники  
 dwCount  
 Число объектов в `Members` массива.  
  
 Участники  
 Массив [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) объектов, описывающих программы, в запросе.  
  
## <a name="remarks"></a>Примечания  
 Эта структура является частью [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) структуру, которая в свою очередь заполняется с помощью вызова [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) метод.  
  
## <a name="requirements"></a>Требования  
 Header: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Структуры и объединения](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)