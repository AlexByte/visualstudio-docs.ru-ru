---
title: Вложение на основе запуска | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fa0f03c37b92366e9872cbd170605a385aabdd1a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975859"
---
# <a name="launch-based-attachment"></a>Вложение на основе запуска
Вложение на основе запуска программы выполняется автоматически. При запуске процесса, размещающего программы, SDM вложение на основе запуска следует путь, у метода вручную вложения. Сведения см. в разделе [присоединения к программе](../../extensibility/debugger/attaching-to-the-program.md).  
  
## <a name="the-attaching-process"></a>Присоединение процесса  
 Основное различие заключается в последовательность событий следующие **Attach** вызвать, как показано ниже:  
  
1.  Отправить **IDebugEngineCreateEvent2** объект события для SDM. Дополнительные сведения см. в разделе [отправлять события](../../extensibility/debugger/sending-events.md).  
  
2.  Вызовите `IDebugProgram2::GetProgramId` метод **IDebugProgram2** передается интерфейс **Attach** метод.  
  
3.  Отправить **IDebugProgramCreateEvent2** объект события для уведомления SDM, локальной **IDebugProgram2** объект был создан для представления программы для DE.  
  
4.  Отправить [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) объект события для уведомления SDM о том, что для процесса, запустившего создается новый поток.  
  
## <a name="see-also"></a>См. также  
 [Отправка необходимых событий](../../extensibility/debugger/sending-the-required-events.md)   
 [Включение программы для отладки](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)