---
title: CA1011. Попробуйте передать базовые типы в качестве параметров
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5d3f293e6e75986e4c3097e972e7047c25756d65
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957615"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011. Попробуйте передать базовые типы в качестве параметров

|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Категория|Microsoft.Design|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина

Объявление метода содержит формальный параметр, который является производным типом, и метод вызывает только члены базового типа параметра.

## <a name="rule-description"></a>Описание правила

Если в объявлении метода в качестве параметра указан базовый тип, любой тип, производный от базового, можно передать методу в качестве соответствующего аргумента. Если аргумент используется в теле метода, конкретный метод, который выполняется зависит от типа аргумента. Если дополнительные функции, предоставляемые производный тип не является обязательной, использование базового типа позволяет более широко применять метод.

## <a name="how-to-fix-violations"></a>Устранение нарушений

Чтобы устранить нарушение этого правила, измените тип параметра со своим базовым типом.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений

Его можно безопасно подавить предупреждение из этого правила

- Если метод требует конкретные функции, предоставляемые производным типом

     \- или -

- для принудительного применения, что только производный тип, или производного типа, передается в метод.

В этом случае код будет более устойчивым из-за строгая проверка типов, предоставляемые компилятором и средой выполнения.

## <a name="example"></a>Пример

В следующем примере показан метод `ManipulateFileStream`, который может использоваться только с <xref:System.IO.FileStream> объект, который нарушает это правило. Второй метод `ManipulateAnyStream`, соответствующий этому правилу, заменив <xref:System.IO.FileStream> параметра с помощью <xref:System.IO.Stream>.

[!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
[!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
[!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]

## <a name="related-rules"></a>Связанные правила

[CA1059: Члены не должны предоставлять определенные устойчивые типы](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)