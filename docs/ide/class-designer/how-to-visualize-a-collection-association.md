---
title: Как выполнить Визуализация ассоциации коллекции (конструктор классов)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.collectionassociationline
- vs.classdesigner.ShowAssociationException
helpviewer_keywords:
- collection associations
- collections, collection associations
- Class Designer [Visual Studio], collection associations
ms.assetid: 54e39838-2fc9-4dc2-85b6-7e88a743108e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: acf1fd75770888f492833235f09a381d0836be34
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53925398"
---
# <a name="how-to-visualize-a-collection-association-in-class-designer"></a>Как выполнить Визуализация ассоциации коллекции в конструкторе классов

Свойства и поля, которые являются наборами других типов, могут отображаться в схеме классов как ассоциация набора. В отличие от обычной ассоциации, которая отображает поля или свойства в виде линии, связывающей класс-владелец с типом поля, ассоциация набора отображается как линия, связывающая класс-владелец с собранным типом.

## <a name="to-create-a-collection-association"></a>Создание ассоциации набора

1.  В коде создайте свойство или поле, тип которого является строго типизированным набором.

2.  В схеме классов разверните класс так, чтобы отображались свойства и поля.

3.  В классе щелкните правой кнопкой мыши поле или свойство и выберите **Показывать как ассоциацию наборов**.

Свойство или поле отображается в виде линии ассоциации, связанной с собранным типом.

## <a name="see-also"></a>См. также

- [Практическое руководство. Создание ассоциаций между типами в конструкторе классов](how-to-create-associations-between-types.md)
- [Конструирование классов и типов](designing-and-viewing-classes-and-types.md)
