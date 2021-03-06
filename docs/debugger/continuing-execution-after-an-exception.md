---
title: Продолжение выполнения после исключения | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a966709ed4b3fbb773d9f91726f4f79289af5504
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53864473"
---
# <a name="continuing-execution-after-an-exception"></a>Возобновление выполнения после исключения
Когда отладчик приостанавливает выполнение из-за исключения, вы увидите **помощника по исправлению ошибок**, по умолчанию. Если вы отключили **помощника по исправлению ошибок** в **параметры** диалоговом окне вы увидите **исключениям** (C# или Visual Basic) или  **Исключение** диалоговое окно (C++).  
  
 Когда **помощника по исправлению ошибок** отображается, можно попытаться устранить неполадку, вызвавшую исключение.
  
## <a name="managed-and-native-code"></a>Управляемого и машинного кода  
 В управляемого и машинного кода можно возобновить выполнение в том же потоке после необработанного исключения. **Помощника по исправлению ошибок** стек вызовов в точке, где возникло исключение.
  
## <a name="mixed-code"></a>Смешанный код  
 Если при отладке смешанного машинного и управляемого кода возникает необрабатываемое исключение, ограничения операционной системы не позволяют очистить стек вызовов. При попытке очистить стек вызовов с помощью контекстного меню отображается сообщение об ошибке, поясняющее, что при отладке смешанного кода отладчик не может вернуться в предыдущее состояние после возникновения необрабатываемого исключения.  
  
## <a name="see-also"></a>См. также раздел  
 [Управление исключениями с помощью отладчика](../debugger/managing-exceptions-with-the-debugger.md)