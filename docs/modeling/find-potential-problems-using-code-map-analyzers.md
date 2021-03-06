---
title: Поиск потенциальных проблем с помощью анализаторов карт кода
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.progression.codemapanalyzers
helpviewer_keywords:
- code analysis, dependency graphs
- dependency graphs, analyzing code
- graph documents, analyzing
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 04e4d51fba62c56ce39fd34d8179f73baeeea77a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55025921"
---
# <a name="find-potential-problems-using-code-map-analyzers"></a>Поиск потенциальных проблем с помощью анализаторов карт кода

Запустите анализаторы для карт кода, чтобы выявить код, который может быть слишком сложным или может требовать улучшений. Например, можно использовать следующие анализаторы:

|**Чтобы найти код, который**|**Изучите эти области в следующих целях**|
|-|-|
|Содержит циклы или циклические зависимости|Определите, можете ли вы упростить их, и рассмотрите возможность прерывания этих циклов.|
|Содержит слишком много зависимостей|Выясните, не выполняют ли они слишком много функций, или определите влияние изменения этих областей. Правильно сформированная карта кода имеет минимальное количество зависимостей. Чтобы сделать код проще для поддержки, изменения, проверки и повторного использования, рассмотрите возможность рефакторинга этих областей, чтобы они были определены более четко, или возможность слияния кода, выполняющего аналогичные функции.|
|Не содержит зависимостей|Определите, необходимы ли они или этот код можно удалить.|

## <a name="analyze-code-maps"></a>Анализ карт кода

На панели инструментов карты выберите **макета** > **анализаторы**, а затем анализатор, который вы хотите запустить:

|**Анализатор**|**Для выявления следующих узлов**|
|-|-|
|**Анализатор циклических ссылок**|Узлы, которые содержат циклические зависимости друг от друга. **Примечание.**  Циклические зависимости, находящиеся в **универсальные шаблоны** группы, не отображаются на карте при развертывании группы.|
|**Анализатор "Найти концентраторы"**|Узлы, входящие в 25 % узлов, имеющих больше всего соединений.<br /><br /> **Скрытие всех узлов на карте**<br /><br /> -Откройте контекстное меню для карты, выберите **Дополнительно**, **выберите**, **Скрыть невыбранные**.<br />     Невыбранные узлы карты скрываются, и анализатор определяет новые узлы как концентраторы.|
|**Анализатор узлов, на которые нет ссылок**|Узлы, на которые не ссылаются другие узлы. **Внимание!**  Проверьте каждый из этих случаев, прежде чем делать предположение о том, что код не используется. Некоторые зависимости, такие как зависимости XAML и зависимости времени выполнения, не удается найти в коде статически.|

Анализаторы карт кода продолжают работу после их применения. Если изменить карту, все примененные анализаторы автоматически обрабатывают обновленную карту повторно. Чтобы остановить работу анализатора, на панели инструментов карты выберите **макета** > **анализаторы**. Отключите выбранный анализатор.

> [!TIP]
> В случае с очень большой картой запуск анализатора может привести к возникновению исключения "Недостаточно памяти". В этом случае измените карту, чтобы сузить ее область действия, или создайте карту меньшего размера, а затем запустите анализатор.

## <a name="see-also"></a>См. также

- [Сопоставление зависимостей во всех решениях](../modeling/map-dependencies-across-your-solutions.md)
- [Использование карт кода для отладки приложений](../modeling/use-code-maps-to-debug-your-applications.md)
- [Сопоставление методов в стеке вызовов при отладке](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
