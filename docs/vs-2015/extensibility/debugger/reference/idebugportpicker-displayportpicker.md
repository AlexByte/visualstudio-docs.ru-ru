---
title: IDebugPortPicker::DisplayPortPicker | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 62a215ee18bcd9e82047017bca90102163ff8b6f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51766609"
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Отображает указанный диалоговое окно, которое позволяет пользователю выбрать порт.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT DisplayPortPicker(  
   HWND hwndParentDialog,  
   BSTR* pbstrPortId  
);  
```  
  
```csharp  
public int DisplayPortPicker(  
   int hwndParentDialog,  
   out string pbstrPortId  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hwndParentDialog`  
 [in] Дескриптор родительского диалогового окна.  
  
 `pbstrPortId`  
 [out] Строка идентификатора порта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки. Возвращаемое значение, равное `S_FALSE` (или возвращаемое значение, равное `S_OK` с `BSTR` присвоено `NULL`) указывает, что пользователь нажал **отменить**.  
  
## <a name="see-also"></a>См. также  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)

