---
title: IDiaTable::Item | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e8ba825c0dba1b0218e53f9ad66f6958602d0c2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53953983"
---
# <a name="idiatableitem"></a>IDiaTable::Item
Извлекает ссылку на указанную запись в таблице.  
  
## <a name="syntax"></a>Синтаксис  
  
```C++  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `index`  
 [in] Индекс записи в таблице в диапазоне от 0 до `count`-1, где `count` возвращается [IDiaTable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)метод.  
  
 `element`  
 [out] Возвращает `IUnknown` , представляющий элемент указанной таблицы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Таблицы представляет коллекцию объектов. В зависимости от объектов элемент можно привести на соответствующий интерфейс. Например, если таблица содержит [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) объектов, а затем элемент параметра может быть приведен к `IDiaSegment` интерфейс.  
  
 Это наиболее распространенный подход для вызова `QueryInterface` метод в [IDiaTable](../../debugger/debug-interface-access/idiatable.md) интерфейса для интерфейса соответствующим перечислителем и использовать конкретные методы перечислителя для доступа к содержимому таблицы. См. в разделе [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) интерфейс пример.  
  
## <a name="see-also"></a>См. также раздел  
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [IDiaTable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)