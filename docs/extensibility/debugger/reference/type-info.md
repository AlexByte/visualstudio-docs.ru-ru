---
title: TYPE_INFO | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- TYPE_INFO
helpviewer_keywords:
- TYPE_INFO structure
ms.assetid: d725cb68-a565-49d1-a16f-ff0445c587a0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fcc5f5f6b37a632d2e634b22ab3d7032214af462
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54934284"
---
# <a name="typeinfo"></a>TYPE_INFO
Эта структура определяет различные виды информации о типа поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
struct _tagTYPE_INFO_UNION {  
   dwTYPE_KIND dwKind;  
   union {  
      METADATA_TYPE typeMeta;  
      PDB_TYPE      typePdb;  
      BUILT_TYPE    typeBuilt;  
      DWORD         unused;  
   } type;  
} TYPE_INFO;  
```  
  
```csharp  
public struct TYPE_INFO {  
   public uint   dwKind;  
   public IntPtr unionmember;  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 dwKind  
 Значение из [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) перечисления, которое определяет способ интерпретации объединение.  
  
 type.typeMeta  
 [C++] Содержит [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) структуры, если `dwKind` является `TYPE_KIND_METADATA`.  
  
 type.typePdb  
 [C++] Содержит [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) структуры, если `dwKind` является `TYPE_KIND_PDB`.  
  
 type.typeBuilt  
 [C++] Содержит [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) структуры, если `dwKind` является `TYPE_KIND_BUILT`.  
  
 Type.unused  
 Неиспользуемые заполнение.  
  
 type  
 Имя объединения.  
  
 unionmember  
 [C# только] Маршалинг, это тип подходящей структурой на основе `dwKind`.  
  
## <a name="remarks"></a>Примечания  
 Эта структура передается [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) метод, где он заполняется. Интерпретация содержимое структуры на основе `dwKind` поля.  
  
> [!NOTE]
>  [C++] Если `dwKind` равно `TYPE_KIND_BUILT`, то это необходимо для высвобождения базовый [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) объект при удалении `TYPE_INFO` структуры. Это выполняется с помощью вызова метода `typeInfo.type.typeBuilt.pUnderlyingField->Release()`.  
  
 [C# только] В следующей таблице показаны способ интерпретации `unionmember` член для каждого типа. В примере показано, как это можно сделать для одного типа.  
  
|`dwKind`|`unionmember` интерпретируется как|  
|--------------|----------------------------------|  
|`TYPE_KIND_METADATA`|[METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)|  
|`TYPE_KIND_PDB`|[PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)|  
|`TYPE_KIND_BUILT`|[BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)|  
  
## <a name="example"></a>Пример  
 В этом примере показано, как интерпретировать `unionmember` членом `TYPE_INFO` структуры в C#. В этом примере показано, Интерпретация только один тип (`TYPE_KIND_METADATA`), но остальные интерпретируются точно таким же образом.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(TYPE_INFO ti)  
        {  
            if (ti.dwKind == (uint)enum_dwTypeKind.TYPE_KIND_METADATA)  
            {  
                 METADATA_TYPE dataType = (METADATA_TYPE)Marshal.PtrToStructure(ti.unionmember,  
                                               typeof(METADATA_TYPE));  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Требования  
 Заголовок: sh.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Структуры и объединения](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)