---
title: Выбранный класс невозможно удалить, потому что он используется как тип возвращаемого значения одного или нескольких методов DataContext
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 36ad2afe48b5af06bf7ee59fa3043221bc787ba6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53988979"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>Выбранный класс невозможно удалить, потому что он используется как тип возвращаемого значения одного или нескольких методов DataContext

Тип возврата одного или нескольких методов <xref:System.Data.Linq.DataContext> это выбранный класс сущностей. Удаление класса сущностей, который используется как тип возвращаемого значения для <xref:System.Data.Linq.DataContext> метод приводит к компиляции проекта переход на другой. Чтобы удалить выбранный класс сущностей, Идентифицируйте методы <xref:System.Data.Linq.DataContext>, которые его используют, и задайте их типам возврата другой класс сущностей.

Для возврата типов возврата методов <xref:System.Data.Linq.DataContext> к их исходным автоматически сгенерированным типам сначала удалите метод <xref:System.Data.Linq.DataContext> из области **методов** и потом перетащите объект из **Обозревателя серверов**/**Обозревателя базы данных** снова в **реляционный конструктор объектов**.

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Идентифицируйте методы <xref:System.Data.Linq.DataContext>, которые используют класс сущностей в качестве типа возврата, выбрав метод <xref:System.Data.Linq.DataContext> в области **методов** и проверив свойство **Тип возврата** в окне **Свойства**.

2. Установите **Тип возврата<xref:System.Data.Linq.DataContext> на другой класс сущностей или удалите метод**  из области методов.

## <a name="see-also"></a>См. также

- [Сообщения реляционного конструктора объектов](../data-tools/o-r-designer-messages.md)
- [Средства LINQ to SQL в Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)