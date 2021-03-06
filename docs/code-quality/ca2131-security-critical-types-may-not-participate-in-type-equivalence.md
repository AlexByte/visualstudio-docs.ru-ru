---
title: CA2131. Критические для безопасности типы не могут участвовать в эквивалентности типов
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d42b7f0104f00f346146de882c903c2ebd0ececc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54993169"
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131. Критические для безопасности типы не могут участвовать в эквивалентности типов

|||
|-|-|
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Тип участвует в эквивалентности типов и либо сам тип или член или поле типа помечены с <xref:System.Security.SecurityCriticalAttribute> атрибута.

## <a name="rule-description"></a>Описание правила
 Это правило применяется ко всем критическим типам или к типам, содержащим критические методы или поля, участвующие в эквивалентности типов. Когда среда CLR обнаруживает такой тип, его не удается загрузить его с <xref:System.TypeLoadException> во время выполнения. Обычно это правило срабатывает, только если пользователи реализуют эквивалентность типов вручную вместо того, чтобы позволить tlbimp и компиляторам обработать эквивалентность типов.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, удалите атрибут SecurityCritical.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример
 В следующих примерах показано, интерфейс, метод и поле, вызывающее срабатывание этого правила.

 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]

## <a name="see-also"></a>См. также
 [Прозрачный с точки зрения безопасности код, уровень 2](/dotnet/framework/misc/security-transparent-code-level-2)