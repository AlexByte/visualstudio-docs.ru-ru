---
title: IDebugReference2::Compare | Документация Майкрософт
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
- IDebugReference2::Compare
helpviewer_keywords:
- IDebugReference2::Compare
ms.assetid: 3361c495-2673-4b7c-82e3-dee74e1fa58d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 95c5baaea39e1996999da5aabed55555c054d0c5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51747926"
---
# <a name="idebugreference2compare"></a>IDebugReference2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Сравнивает одну ссылку на другой. Зарезервировано для будущего использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT Compare (   
   REFERENCE_COMPARE dwCompare,  
   IDebugReference2* pReference  
);  
```  
  
```csharp  
int Compare (   
   enum_REFERENCE_COMPARE dwCompare,  
   IDebugReference2       pReference  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwCompare`  
 [in] Значение из [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md) перечисление, указывающее операцию сравнения, например, равно, меньше или больше.  
  
 `pReference`  
 [in] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) объект, представляющий ссылку на который требуется сравнить с.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `E_NOTIMPL`.  
  
## <a name="see-also"></a>См. также  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)

