---
title: Отладка нарушения прав доступа при запуске приложения вне отладчика | Документация Майкрософт
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b65c10b07b93e657a9e3cb9da5f94d5c9b14362
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53854026"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Как отладить нарушения доступа при запуске программы без отладчика?

## <a name="problem-description"></a>Описание проблемы  
 Программа прекрасно работает в среде Visual Studio, но при автономном запуске под операционной системой Windows возникает нарушение доступа. Как это отладить?  
  
## <a name="solution"></a>Решение  
 Активируйте параметр [JIT-отладка](../debugger/just-in-time-debugging-in-visual-studio.md) и запустите автономное выполнение программы до момента возникновения нарушения доступа. Затем в диалоговом окне **Нарушение доступа** можно нажать **Отмена** и запустить отладчик.  
  
## <a name="see-also"></a>См. также раздел  
 [Вопросы и ответы по отладке машинного кода](../debugger/debugging-native-code-faqs.md)   
 [Отладка машинного кода](../debugger/debugging-native-code.md)