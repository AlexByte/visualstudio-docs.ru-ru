---
title: IDebugCodeContext3 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e9ff7ac48c745416dbbed799521048997fba5662
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54956445"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
Расширяет [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) интерфейс, чтобы обеспечить получение модулей и процессов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Реализуется отладчиков и потребляемых [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] отладочный пакет.  
  
## <a name="methods"></a>Методы  
 В дополнение к методам на `IDebugCodeContext2` интерфейс, этот интерфейс реализует следующие методы:  
  
|Метод|Описание:|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Извлекает ссылку на интерфейс модуля отладки.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Извлекает ссылку на интерфейс процесс отладки.|  
  
## <a name="remarks"></a>Примечания  
 Это дополнительный интерфейс, который обычно не должны быть реализованы.  
  
## <a name="requirements"></a>Требования  
 Заголовок: Msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll