---
title: Отчет о профиле выполнения | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Profile Report
ms.assetid: c8128472-a8ed-46f4-b1c8-a25358d6f2c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b90bdc015e31d2c9c4313be874b7f38a58a7ac45
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53986548"
---
# <a name="execution-profile-report"></a>Выполнение отчета профилирования
Отчет о профиле выполнения — это традиционный профиль выборки. Выборка выполняется приблизительно каждую миллисекунду в те периоды, когда поток выполняется на логическом ядре, и визуализатор параллелизма строит типичное дерево вызовов, разбирая накопленный набор стеков выборок. На данные в этой таблице может влиять текущий диапазон времени, скрытые потоки и следующие фильтры, которые могли быть применены:  
  
- Если выбран параметр "Только мой код", будут показаны только кадры стека, у которых есть пользовательский код, а также кадры на уровень ниже пользовательского кода.  
  
- Если задано значение для снижения уровня шума, разобранные стеки с частотой ниже заданной фильтруются в отчете.  
  
  В следующей таблице перечислены столбцы отчета.  
  
|Столбец|Описание|  
|------------|-----------------|  
|name|Имя функции для каждого уровня стека вызова.|  
|Включающие выборки|Общее количество выборок, собранных для всех стеков, сведенное в этот уровень дерева стека вызовов. Инклюзивное число — это сумма исключающих выборок для данной функции и инклюзивных счетчиков для всех ее дочерних узлов.|  
|Исключающие выборки|Общее количество собранных выборок, для которых эта функция является нижним уровнем стека вызовов.|  
|% включения|Процент от общего количества выборок, которые отображаются в столбце "Включающие выборки". Процентные значения округляются до двух десятичных разрядов.|  
|% исключения|Процент от общего количества выборок, которые отображаются в столбце "Исключающие выборки". Процентные значения округляются до двух десятичных разрядов.|  
|Подробные сведения|Полное имя функции. Включает число строк, если это значение доступно.|  
  
 Эта таблица отчета может отображаться в представлении [Время выполнения (представление "Потоки")](../profiling/execution-time-threads-view.md).  
  
## <a name="see-also"></a>См. также  
 [Представление потоков](../profiling/threads-view-parallel-performance.md)