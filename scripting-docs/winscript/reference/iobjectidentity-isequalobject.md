---
title: IObjectIdentity::IsEqualObject | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IObjectIdentity.IsEqualObject
apilocation:
- scrobj.dll
helpviewer_keywords:
- IsEqualObject method
ms.assetid: 78c5c5c2-d299-4036-986c-7c1d87cbe7cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa233e478c83b723b13d19d27dc4b63ee4700bb5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095060"
---
# <a name="iobjectidentityisequalobject"></a>IObjectIdentity::IsEqualObject
Определяет, если объект равен текущему объекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT IsEqualObject(  
  IUnknown*punk  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `punk`  
 [in] Адрес объекта, сравниваемый с текущим объектом.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает `HRESULT`. Допустимые значения включают, но не ограничиваются, значения, приведенные в следующей таблице.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`S_OK`|Объекты равны.|  
|`S_FALSE`|Объекты не равны.|  
  
## <a name="remarks"></a>Примечания  
 Реализация `IsEqualObject` метод должен возвращать `S_OK` только в том случае, если объекты идентичны.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IObjectIdentity](../../winscript/reference/iobjectidentity-interface.md)