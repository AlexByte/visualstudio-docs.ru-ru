---
title: Рефакторинг для удаления недоступного кода
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 481c0d116eb2aee2c4f931f1ca4cb2de7927c62e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53842542"
---
# <a name="remove-unreachable-code-refactoring"></a>Рефакторинг для удаления недоступного кода

Область применения этого рефакторинга:

- C#

**Что?** Удаление кода, который никогда не будет выполняться.

**Когда?** У приложения нет пути к фрагменту кода, что делает этот фрагмент кода ненужным.

**Зачем?** Повысить удобочитаемость и удобство поддержки, удалив код, который является избыточным и никогда не будет выполняться.

## <a name="how-to"></a>Практические советы

1. Поместите курсор в любом месте в области затемненного кода, который недоступен:

![Затемнение недоступного кода](media/unreachablecode-faded-cs.png)

1. Затем выполните одно из следующих действий:

   - **Клавиатура**
      - Нажмите клавиши **CTRL**+**.** чтобы активировать меню **Быстрые действия и рефакторинг**. Затем выберите во всплывающем окне предварительного просмотра пункт **Удалить недоступный код**.
   - **Мышь**
      - Щелкните код правой кнопкой мыши и выберите меню **Быстрые действия и рефакторинг**. Затем выберите во всплывающем окне предварительного просмотра пункт **Удалить недоступный**.

1. Если вы довольны результатами, нажмите клавишу **ВВОД** или выберите соответствующий пункт в меню, чтобы зафиксировать изменения.

Пример

```csharp
// Before
private void Method()
{
    throw new Exception(nameof(Method));
    Console.WriteLine($"Exception for method {nameof(Method)}");
}

// Remove unreachable code

// After
private void Method()
{
    throw new Exception(nameof(Method));
}
```

## <a name="see-also"></a>См. также

- [Рефакторинг](../refactoring-in-visual-studio.md)
- [Просмотр изменений](../../ide/preview-changes.md)