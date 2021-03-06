---
title: DISASSEMBLY_FLAGS | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_FLAGS
helpviewer_keywords:
- DISASSEMBLY_FLAGS enumeration
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ada1fba496051d3e71b21c94e61c951f7c14c6c4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036437"
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
Задает флаги для Дизассемблированный код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
typedef DWORD DISASSEMBLY_FLAGS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
```  
  
## <a name="members"></a>Участники  
 DF_DOCUMENTCHANGE  
 Указывает, что эта инструкция находится в другой документ, отличный от предыдущего.  
  
 DF_DISABLED  
 Указывает, что эта инструкция будет выполнена.  
  
 DF_INSTRUCTION_ACTIVE  
 Указывает, что эта инструкция является одним из далее инструкциям для выполнения (может быть несколько).  
  
 DF_DATA  
 Указывает, что эта инструкция действительно данных (не в коде).  
  
 DF_HASSOURCE  
 Указывает, что эта инструкция имеет источник. Некоторые инструкции, такие как коллекции кода профилирования или сборки мусора, имеют нет соответствующего источника.  
  
 DF_DOCUMENT_CHECKSUM  
 Указывает, что `bstrDocumentUrl` поле содержит данные контрольной суммы после URL-адрес документа. См. в разделе "Примечания" [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) структуру как хранятся данные контрольной суммы.  
  
## <a name="remarks"></a>Примечания  
 Используется в качестве `dwFlags` членом [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) структуры.  
  
 Эти флаги могут быть объединены с побитовым объектом `OR`.  
  
## <a name="requirements"></a>Требования  
 Header: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)