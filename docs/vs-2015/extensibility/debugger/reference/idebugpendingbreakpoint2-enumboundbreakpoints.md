---
title: IDebugPendingBreakpoint2::EnumBoundBreakpoints | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPendingBreakpoint2::EnumBoundBreakpoints
helpviewer_keywords:
- EnumBoundBreakpoints method
- IDebugPendingBreakpoint2::EnumBoundBreakpoints method
ms.assetid: 179c7c54-8446-462d-b099-e0f9cf06dc52
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cb903be055ffae239f358417c65f5267d13d298f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47568645"
---
# <a name="idebugpendingbreakpoint2enumboundbreakpoints"></a>IDebugPendingBreakpoint2::EnumBoundBreakpoints
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [IDebugPendingBreakpoint2::EnumBoundBreakpoints](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints).  
  
Перечисляет все точки останова, привязанный из этого ожидающая точка останова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT EnumBoundBreakpoints(   
   IEnumDebugBoundBreakpoints2** ppEnum  
);  
```  
  
```csharp  
int EnumBoundBreakpoints(   
   out IEnumDebugBoundBreakpoints2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppEnum`  
 [out] Возвращает [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) объект, который перечисляет связанных точек останова.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки. Возвращает `E_BP_DELETED` Если точка останова была удалена.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реализовать этот метод для простого `CPendingBreakpoint` объекта, который предоставляет [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) интерфейс.  
  
```cpp#  
HRESULT CPendingBreakpoint::EnumBoundBreakpoints(IEnumDebugBoundBreakpoints2** ppEnum)    
{    
   HRESULT hr;    
  
   // Verify that the passed IEnumDebugBoundBreakpoints2 interface pointer   
   // is valid.    
   if (ppEnum)    
   {    
      *ppEnum = NULL;  
  
      // Verify that the pending breakpoint has not been deleted. If   
      // deleted, then return hr = E_BP_DELETED.    
      if (m_state.state != PBPS_DELETED)    
      {    
         // If the bound breakpoint member variable is valid.  
         if (m_pBoundBP)    
         {    
            // Get the bound breakpoint.    
            CComPtr<IDebugBoundBreakpoint2> spBoundBP;    
            hr = m_pBoundBP->QueryInterface(&spBoundBP);    
            assert(hr == S_OK);    
            if (hr == S_OK)    
            {    
               // Create the bound breakpoint enumerator.    
               CComObject<CEnumDebugBoundBreakpoints>* pBoundEnum;    
               hr = CComObject<CEnumDebugBoundBreakpoints>::CreateInstance(&pBoundEnum);    
               assert(hr == S_OK);    
               if (hr == S_OK)    
               {    
                  // Initialize the enumerator of bound breakpoints with   
                  // the IDebugBoundBreakpoint2 information.      
                  IDebugBoundBreakpoint2* rgBoundBP[] = { spBoundBP.p };    
                  hr = pBoundEnum->Init(rgBoundBP, &(rgBoundBP[1]), NULL, AtlFlagCopy);    
                  if (hr == S_OK)    
                  {    
                     // Verify that the passed IEnumDebugBoundBreakpoints2     
                     // interface can be queried by the created  
                     // CEnumDebugBoundBreakpoints object.    
                     hr = pBoundEnum->QueryInterface(ppEnum);    
                     assert(hr == S_OK);    
                  }    
  
                  // Otherwise, delete the CEnumDebugBoundBreakpoints object.    
                  if (FAILED(hr))    
                  {    
                     delete pBoundEnum;    
                  }    
               }    
            }    
         }    
         else    
         {    
            hr = S_FALSE;    
         }    
      }    
      else    
      {    
         hr = E_BP_DELETED;    
      }    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>См. также  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)
