---
title: Общие сведения о выделении памяти и значениях времени существования объектов | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools, .NET memory method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 518be5d4126dbfa2713fada4df8451292166dcbf
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53858955"
---
# <a name="understand-memory-allocation-and-object-lifetime-data-values"></a>Общие сведения о выделении памяти и значениях данных о времени существования объекта

Способ профилирования *Выделение памяти .NET* средств профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] собирает сведения о размере и числе объектов, созданных при выделении памяти или удаленных при сборке мусора, а также дополнительные сведения о *стеке вызовов* функции на момент события. *Стек вызовов* — это динамическая структура, в которой хранится информация о функциях, выполняющихся в процессоре.

Профилирование памяти прерывает работу процессора при каждом выделении памяти объекту .NET Framework в профилируемом приложении. Если при этом также собираются сведения о времени существования объектов, профилировщик прерывает работу процессора после каждой сборки мусора в .NET Framework. Данные собираются для каждой профилируемой функции и для каждого типа объекта.

## <a name="allocation-data"></a>Данные выделения

Когда происходит событие .memory, общее число и размер выделенных или удаленных объектов памяти увеличивается.

Когда происходит событие выделения .memory, профилировщик увеличивает число экземпляров каждой функции в стеке вызовов. После сбора данных в стеке вызовов выполняется код тела только одной функции. Остальные функции в стеке являются родительскими в иерархии вызовов функций, ожидающих возврата значений вызванными ими функциями.

- Для события выделения профилировщик увеличивает число *эксклюзивных* образцов функции, выполняющей его инструкции. Так как эксклюзивный образец также учитывается при подсчете общего числа (*инклюзивных*) образцов функции, увеличивается и число инклюзивных образцов активной в данный момент функции.

- Профилировщик увеличивает счетчики инклюзивных образцов для всех остальных функций в стеке вызовов.

## <a name="lifetime-data"></a>Сведения о времени существования

Сборщик мусора .NET Framework управляет выделением и освобождением памяти для приложения. Для оптимизации производительности сборщика мусора управляемая куча делится на три поколения: 0, 1 и 2. Сборщик мусора среды выполнения хранит новые объекты в поколении 0. Уровень объектов, оставшихся после сборок мусора, повышается, и они сохраняются в поколениях 1 и 2.

Сборщик мусора освобождает память путем удаления целого поколения объектов. Для объектов, созданных профилируемым приложением, в представлении "Время жизни объекта" отображаются количество и размер объектов, а также поколение, в котором они были удалены.