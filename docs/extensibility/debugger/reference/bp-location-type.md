---
title: BP_LOCATION_TYPE | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_TYPE
helpviewer_keywords:
- BP_LOCATION_TYPE structure
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b4f483ca341055e7d041fe690dcdb4271138cf97
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922224"
---
# <a name="bplocationtype"></a>BP_LOCATION_TYPE
Указывает тип местоположения точки останова для запроса точки останова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
typedef DWORD BP_LOCATION_TYPE;  
```  
  
```csharp  
public enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
```  
  
## <a name="members"></a>Участники  
 BPLT_NONE  
 Указывает расположение не точки останова.  
  
 BPLT_FILE_LINE  
 Указывает тип местоположения точки останова в строке файла.  
  
 BPLT_FUNC_OFFSET  
 Указывает тип местоположения точки останова, как функция смещение.  
  
 BPLT_CONTEXT  
 Указывает тип местоположения точки останова в качестве контекста.  
  
 BPLT_STRING  
 Указывает тип местоположения точки останова в виде строки.  
  
 BPLT_ADDRESS  
 Указывает тип местоположения точки останова, как адрес.  
  
 BPLT_RESOLUTION  
 Указывает тип местоположения точки останова, как разрешение.  
  
 BPLT_CODE_FILE_LINE  
 Указывает тип местоположения точки останова в строке исходного кода.  
  
 BPLT_CODE_FUNC_OFFSET  
 Указывает тип местоположения точки останова, как функция смещение кода.  
  
 BPLT_CODE_CONTEXT  
 Указывает тип местоположения точки останова, как контекст кода.  
  
 BPLT_CODE_STRING  
 Указывает тип местоположения точки останова в виде строки кода.  
  
 BPLT_CODE_ADDRESS  
 Указывает тип местоположения точки останова, как адрес кода.  
  
 BPLT_DATA_STRING  
 Указывает тип местоположения точки останова в виде строки данных.  
  
 BPLT_TYPE_MASK  
 Указывает битовую маску, чтобы тип точки останова могут быть извлечены из значения.  
  
 BPLT_LOCATION_TYPE_MASK  
 Указывает битовую маску, чтобы тип местоположения точки останова могут быть извлечены из значения.  
  
## <a name="remarks"></a>Примечания  
 Переданный в качестве параметра для [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md) метод.  
  
 Тип местоположения точки останова представляет собой тип точки останова и тип расположения. Это означает, что тип местоположения точки останова никогда не просто тип точки останова (например, `BPT_CODE`) или тип расположения (например, `BPLT_FILE_LINE`). Предопределенные константы для всех типов расположение точки останова, в настоящее время включены в это перечисление (`BPLT_CODE_FILE_LINE` через `BPLT_DATA_STRING`).  
  
 `BPT_CODE` и `BPT_DATA` являются членами [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) перечисления.  
  
## <a name="requirements"></a>Требования  
 Header: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)