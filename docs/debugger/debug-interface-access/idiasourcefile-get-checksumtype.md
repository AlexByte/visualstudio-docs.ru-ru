---
title: IDiaSourceFile::get_checksumType | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 750d48cad07251f34e988fa8a6ced618821c443d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53825919"
---
# <a name="idiasourcefilegetchecksumtype"></a>IDiaSourceFile::get_checksumType
Извлекает тип контрольной суммы.  
  
## <a name="syntax"></a>Синтаксис  
  
```C++  
HRESULT get_checksumType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRetVal`  
 [out] Возвращает тип контрольной суммы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Тип контрольной суммы — значение, которое может быть сопоставлен алгоритма подсчета контрольной суммы. Например стандартные PDB-файлов можно обычно имеют один из следующих значений:  
  
|Тип контрольной суммы|Метка CryptoAPI|Описание|  
|-------------------|---------------------|-----------------|  
|0|\<none>|Контрольная сумма не существует.|  
|1|`CALG_MD5`|контрольная сумма, созданных с использованием алгоритма хэширования MD5.|  
|2|`CALG_SHA1`|контрольная сумма, созданных с использованием алгоритма хэширования SHA1.|  
  
 `CryptoAPI` Метки являются из `ALG_ID` перечисления. Дополнительные сведения о алгоритмы хэширования, обратитесь к `CryptoAPI` раздел Microsoft [!INCLUDE[winsdkshort](../../debugger/debug-interface-access/includes/winsdkshort_md.md)].  
  
 Чтобы получить байты фактическая контрольная сумма для исходного файла, вызовите [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) метод.  
  
## <a name="see-also"></a>См. также раздел  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)