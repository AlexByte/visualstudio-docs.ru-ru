---
title: SetThreadCount | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 13e7e2bb1ecabc67f60da7b2d4c68b413fa9cf92
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53844370"
---
# <a name="setthreadcount"></a>SetThreadCount
Задает глобальный счетчик потоков и назначает его текущему потоку.  
  
## <a name="syntax"></a>Синтаксис  
  
```cmd  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `threadCount`  
 Количество потоков для использования.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **HRESULT** с установленным битом **SUCCEEDED**, если счетчик потоков был обновлен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** *FileTracker.h*