---
title: IDebugPortSupplier2::CanAddPort | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 650b65e043ca16a5aa73a298025819f2fe6802f6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54942390"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
Проверяет, что поставщик порта можно добавить новые порты.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Можно ли добавить порт, возвращает `S_OK`; в противном случае возвращает `S_FALSE` для указания порты не могут добавляться к этого поставщика порта.  
  
## <a name="remarks"></a>Примечания  
 Вызовите этот метод перед вызовом [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) метод, так как последний метод создает порт, а также добавление, которая может оказаться длительной операции.  
  
## <a name="see-also"></a>См. также  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)