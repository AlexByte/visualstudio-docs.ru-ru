---
title: Изменить и продолжить (Visual Basic) | Документация Майкрософт
ms.date: 10/11/2017
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue, 64-bit
- Edit and Continue [Visual Basic]
- debugging [Visual Basic], Edit and Continue
- Visual Basic, Edit and Continue
- 64-bit Edit and Continue
ms.assetid: 7e90f34f-e699-45ab-a4c9-a4b527c498c8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b3e1305a67fa4347a8b39b677c5be31ada257b65
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53838025"
---
# <a name="edit-and-continue-visual-basic"></a>Режим "Изменить и продолжить" (Visual Basic)
"Изменить и продолжить" — это режим [!INCLUDE [vbprvb](../code-quality/includes/vbprvb_md.md)] для отладки, позволяющий изменять код в режиме приостановки. После применения изменений кода можно возобновить выполнение кода с новыми изменениями и увидеть их эффект.  
  
 Можно использовать режим "Изменить и продолжить" всякий раз в режиме приостановки. В режиме приостановки указатель инструкций, желтая стрелка в окне исходного кода указывает на строку, содержащую исполняемые операторы в теле метода или свойства, которая будет выполнена следующей.

 Операция "Изменить и продолжить" поддерживает большинство изменений, которые могут потребоваться в ходе отладки, но существуют некоторые исключения. Дополнительные сведения см. в разделе [поддерживаемые изменения кода (C# и Visual Basic)](../debugger/supported-code-changes-csharp.md).   
  
 При несанкционированном изменении, измененный код отмечается фиолетовой волнистой линией и задача отображается в списке задач. Необходимо отменить несанкционированное изменение, если нужно продолжить в режиме "Изменить и продолжить". Некоторые несанкционированные изменения могут быть разрешены, если производить их вне режима "Изменить и продолжить". Если требуется сохранить результат такого несанкционированного изменения, необходимо остановить отладку и перезапустить приложение.  
  
 Изменить и продолжить поддерживается в приложениях универсальной платформы Windows для Windows 10 и x86 и x64 приложениях, предназначенных для .NET Framework 4.6 рабочего стола или более поздней версии, (.NET Framework является только версии настольного компьютера).

 > [!NOTE]
 > Неподдерживаемые приложения и платформы включают ASP.NET 5, Silverlight 5 и Windows 8.1.
  
 Режим "Изменить и продолжить" не поддерживается при отладке с использованием функции **Присоединение к процессу**. Изменить и продолжить не поддерживается для оптимизированного кода или смешанного управляемого и машинного кода. Дополнительные сведения см. в разделе [поддерживаемые изменения кода (C# и Visual Basic)](../debugger/supported-code-changes-csharp.md).
  
 Подразделы данного раздела предоставляют дополнительные сведения об использовании этого режима и о том, какие виды изменений запрещены.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. "Изменить и продолжить" в режиме приостановки выполнения](../debugger/how-to-apply-edits-in-break-mode-with-edit-and-continue.md)  
 Объясняется, как применять изменения кода в режиме приостановки.  
  
 [Поддерживаемые изменения кода (C# и Visual Basic)](../debugger/supported-code-changes-csharp.md)   
 Описываются типы изменений, которые невозможно выполнить в режиме "Изменить и продолжить" языка [!INCLUDE [vb_current_short](../debugger/includes/vb_current_short_md.md)].  
  
## <a name="related-sections"></a>Связанные разделы  
 [Изменить и продолжить](../debugger/edit-and-continue.md)  
 Предоставляет список разделов по режиму "Изменить и продолжить".
