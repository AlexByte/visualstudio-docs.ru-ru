---
title: Свойства декораторов
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, decorators
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 9cc30e43ea10a0b206351df9722d813b565b78a6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54942182"
---
# <a name="properties-of-decorators"></a>Свойства декораторов
Декораторы, значки, текст или развернуть/свернуть угловые скобки, которые могут присутствовать на формы или соединительные линии на диаграмме. В следующих таблицах показаны свойства три вида декоратор. Некоторые свойства отображаются только на декораторы формы или только на оформители соединителя.

 Дополнительные сведения см. в разделе [способ определения доменного языка](../modeling/how-to-define-a-domain-specific-language.md). Дополнительные сведения об использовании этих свойств см. в разделе [Настройка и расширение доменного языка](../modeling/customizing-and-extending-a-domain-specific-language.md).

## <a name="expandcollapse-decorator"></a>Развернуть/свернуть декоратор

|Свойство.|Описание|Значение по умолчанию|
|-|-|-|
|DisplayName|Имя декоратора, будет отображаться в созданном конструкторе.|Развернуть свернуть декоратор|
|name|Имя декоратора.|ExpandCollapseDecorator|
|Примечания|Неофициальные примечания, связанные с данным декоратором.|\<none>|
|HorizontalOffset|Горизонтальное смещение относительно положения декоратора по умолчанию в дюймах. (На только фигуры.)|0|
|VerticalOffset|Вертикальное смещение относительно положения декоратора по умолчанию в дюймах. (На только фигуры.)|0|
|OffsetFromLine|Смещение декоратора от линии, относительно его положения по умолчанию, в дюймах. (На соединители только.)|0|
|OffsetFromShape|Смещение декоратора от фигуры относительно его положения по умолчанию, в дюймах. (На соединители только.)|0|
|Положение|Положение декоратора по умолчанию.|SourceTop|

## <a name="icon-decorator"></a>Значок декоратора

|Свойство.|Описание|Значение по умолчанию|
|-|-|-|
|DefaultIcon|Путь к файлу значка или изображения для отображения.|\<none>|
|DisplayName|Имя декоратора отображаться в созданном конструкторе.|Значок декоратора|
|name|Имя декоратора.|IconDecorator|
|Примечания|Неформальные примечания, которые связаны с декоратора.|\<none>|
|HorizontalOffset|Горизонтальное смещение относительно положения декоратора по умолчанию в дюймах. (На только фигуры.)|0|
|VerticalOffset|Вертикальное смещение относительно положения декоратора по умолчанию в дюймах. (На только фигуры.)|0|
|OffsetFromLine|Смещение декоратора от линии, относительно его положения по умолчанию, в дюймах. (На соединители только.)|0|
|OffsetFromShape|Смещение декоратора от фигуры относительно его положения по умолчанию, в дюймах. (На соединители только.)|0|
|Положение|Положение декоратора по умолчанию.|SourceTop|

## <a name="textdecorator"></a>TextDecorator

|Свойство.|Описание|Значение по умолчанию|
|-|-|-|
|DefaultText|Отображаемый текст по умолчанию.|Метка|
|DisplayName|Имя декоратора отображаться в созданном конструкторе.|Метка|
|FontSize|Размер шрифта для текста, отображаемого в декораторе.|8|
|FontStyle|Стиль шрифта для текста, отображаемого в декораторе.|Регулярное|
|name|Имя декоратора.|Метка|
|Примечания|Неформальные примечания, которые связаны с декоратора.|\<none>|
|HorizontalOffset|Горизонтальное смещение относительно положения декоратора по умолчанию в дюймах. (На только фигуры.)|0|
|VerticalOffset|Вертикальное смещение относительно положения декоратора по умолчанию в дюймах. (На только фигуры.)|0|
|OffsetFromLine|Смещение декоратора от линии, относительно его положения по умолчанию, в дюймах. (На соединители только.)|0|
|OffsetFromShape|Смещение декоратора от фигуры относительно его положения по умолчанию, в дюймах. (На соединители только.)|0|
|Положение|Положение декоратора по умолчанию.|Targetbottom —|

## <a name="see-also"></a>См. также

- [Глоссарий по средствам доменного языка работы](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)