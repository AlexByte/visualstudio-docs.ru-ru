---
title: THUNK_ORDINAL | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e139bceb9456e792ddf10d00d8b519a7677cc22
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53834065"
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
Определяет преобразователь типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```C++  
typedef enum THUNK_ORDINAL {   
   THUNK_ORDINAL_NOTYPE,  
   THUNK_ORDINAL_ADJUSTOR,  
   THUNK_ORDINAL_VCALL,  
   THUNK_ORDINAL_PCODE,  
   THUNK_ORDINAL_LOAD   
  
   // trampoline thunk ordinals - only for use in Trampoline thunk symbols  
   THUNK_ORDINAL_TRAMP_INCREMENTAL,  
   THUNK_ORDINAL_TRAMP_BRANCHISLAND,  
} THUNK_ORDINAL;  
```  
  
## <a name="elements"></a>Элементы  
 THUNK_ORDINAL_NOTYPE  
 Стандартный преобразователь.  
  
 THUNK_ORDINAL_ADJUSTOR  
 Объект `this` корректором преобразователь.  
  
 THUNK_ORDINAL_VCALL  
 Преобразователь виртуального вызова.  
  
 THUNK_ORDINAL_PCODE  
 Преобразователь P-кода.  
  
 THUNK_ORDINAL_LOAD  
 Преобразователь задержки загрузки.  
  
 THUNK_ORDINAL_TRAMP_INCREMENTAL  
 Добавочные trampoline преобразователь (trampoline преобразователь используется для переброса вызовы из пространства памяти в другой).  
  
 THUNK_ORDINAL_TRAMP_BRANCHISLAND  
 Преобразователь trampoline точки ветви.  
  
## <a name="remarks"></a>Примечания  
 Значения в этом перечислении возвращаются из вызова [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) метод.  
  
## <a name="requirements"></a>Требования  
 Заголовок: cvconst.h  
  
## <a name="see-also"></a>См. также раздел  
 [Перечисления и структуры](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)