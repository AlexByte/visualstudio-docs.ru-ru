---
title: IDebugAddress | Документация Майкрософт
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
- IDebugAddress
helpviewer_keywords:
- IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 82c532434475a46a6bf13a5b2395d6db1799cc15
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51743995"
---
# <a name="idebugaddress"></a>IDebugAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Этот интерфейс представляет собой адрес элемента. Он возвращается с помощью обработчика символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
IDebugAddress : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Символ поставщик реализует этот интерфейс для представления адрес объекта.  
  
## <a name="notes-for-callers"></a>Заметки о вызывающих объектов  
 Многие методы на многих интерфейсов возвращают этот интерфейс.  
  
## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable  
 Этот интерфейс реализует следующий метод:  
  
|Метод|Описание:|  
|------------|-----------------|  
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|Извлекает [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) структуры, описывающий объект и его расположение.|  
  
## <a name="remarks"></a>Примечания  
 Поставщик символов возвращает этот интерфейс для представления объекта и его расположение в определенной области (например, функции, метода или класса). Этот интерфейс возвращается из и передать в различные методы поставщик символов и выражения средство оценки. Как правило поставщик символов является единственной сущностью, который должен интерпретировать содержимое этого интерфейса.  
  
## <a name="requirements"></a>Требования  
 Заголовок: sh.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы поставщика символов](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)

