---
title: IDebugComPlusSymbolProvider::ReplaceSymbols | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ReplaceSymbols
- IDebugComPlusSymbolProvider::ReplaceSymbols
ms.assetid: 82fbc8db-c4b1-432f-bec9-1a9dc09570be
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 61370695ad363d6e3eb3a62ac517f34c707eac94
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54963013"
---
# <a name="idebugcomplussymbolproviderreplacesymbols"></a>IDebugComPlusSymbolProvider::ReplaceSymbols
Заменяет текущий отладочные символы в указанный поток данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReplaceSymbols(  
   ULONG32  ulAppDomainID,  
   GUID     guidModule,  
   IStream* pStream  
);  
```  
  
```csharp  
int ReplaceSymbols(  
   uint    ulAppDomainID,  
   Guid    guidModule,  
   IStream pStream  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ulAppDomainID`  
 [in] Идентификатор домена приложения.  
  
 `guidModule`  
 [in] Уникальный идентификатор модуля.  
  
 `pStream`  
 [in] Поток данных, содержащий новые символы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реализовать этот метод для **CDebugSymbolProvider** объекта, который предоставляет [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) интерфейс.  
  
```cpp  
HRESULT CDebugSymbolProvider::ReplaceSymbols(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    IStream* pStream  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::ReplaceSymbols );  
  
    IfFailGo( GetModule( idModule, &pModule ) );  
    IfFailGo( pModule->ReplaceSymbols( pStream ) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::ReplaceSymbols, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)