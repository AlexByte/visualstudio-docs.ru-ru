---
title: IDiaPropertyStorage::Enum | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::Enum
ms.assetid: 00e462da-980a-40b3-a2d6-75a25ee809e5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6fd383270dabc0117434badf50f48af6f4e695a3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53966217"
---
# <a name="idiapropertystorageenum"></a>IDiaPropertyStorage::Enum
Получает перечислитель для свойств в этом наборе.  
  
## <a name="syntax"></a>Синтаксис  
  
```C++  
HRESULT Enum (   
   IEnumSTATPROPSTG** ppenum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppenum`  
 [out] Возвращает `IEnumSTATPROPSTG` объект (в пространстве имен Microsoft.VisualStudio.OLE.Interop), представляющий перечисление свойств.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="see-also"></a>См. также раздел  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)