---
title: CA1813. Избегайте незапечатанных атрибутов
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2bdb0e39051d109ffb6aa4e02c97830cf136fbe2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037685"
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813. Избегайте незапечатанных атрибутов

|||
|-|-|
|TypeName|AvoidUnsealedAttributes|
|CheckId|CA1813|
|Категория|Microsoft.Performance|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина

Открытый тип наследует от <xref:System.Attribute?displayProperty=fullName>, не является абстрактным и не является запечатанным (`NotInheritable` в Visual Basic).

## <a name="rule-description"></a>Описание правила

Библиотеки классов .NET Framework предоставляет методы для извлечения пользовательских атрибутов. По умолчанию эти методы осуществляют поиск иерархии наследования атрибутов. Например <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> производит поиск определенного типа атрибута или любой тип атрибута, который расширяет тип указанного атрибута. Запечатывание атрибута, поиск в иерархии наследования и может повысить производительность.

## <a name="how-to-fix-violations"></a>Устранение нарушений

Чтобы устранить нарушение данного правила, запечатайте атрибут или сделать абстрактным.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений

Его можно безопасно подавить предупреждение из этого правила. Подавляет только в том случае, если при определении иерархии атрибутов и нельзя запечатать атрибут или сделать абстрактным.

## <a name="example"></a>Пример

В примере показан настраиваемый атрибут, который соответствует данному правилу.

[!code-csharp[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
[!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]

## <a name="related-rules"></a>Связанные правила

- [CA1019: НЕОБХОДИМО Определять методы доступа для аргументов атрибутов](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)
- [CA1018: Пометьте атрибуты с помощью AttributeUsageAttribute](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>См. также

- [Атрибуты](/dotnet/standard/design-guidelines/attributes)