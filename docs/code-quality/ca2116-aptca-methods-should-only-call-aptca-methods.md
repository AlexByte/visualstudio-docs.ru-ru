---
title: CA2116. APTCA-методы должны вызывать только APTCA-методы
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6ecd6c5a51feb025eb5e90fa63ae0b2a8bf877ed
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029795"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116. APTCA-методы должны вызывать только APTCA-методы

|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина

Метод в сборке с <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> атрибута вызывает метод в сборке, которая не имеет атрибута.

## <a name="rule-description"></a>Описание правила

По умолчанию, открытые или защищенные методы в сборках со строгими именами неявно защищены [требования связывания](/dotnet/framework/misc/link-demands) для полного доверия; только полностью доверенные, вызывающие объекты могут получить доступ к является сборкой со строгим именем. Сборки со строгими именами, имеющие <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA) нет эту защиту. Атрибут отключает компоновки, доступности сборки вызывающим объектам, не имеющие полного доверия, например код, выполнение из интрасети или Интернета.

Если в полностью доверенной сборке присутствует атрибут APTCA, и она выполняет код в другой сборке, которая не позволяет частично доверенным вызывающим объектам, возможен уязвимости безопасности. Если два метода `M1` и `M2` удовлетворять следующим условиям, злоумышленники могут использовать метод `M1` обходить требование связывания неявное полного доверия, который защищает `M2`:

- `M1` открытый метод, объявленный в полностью доверенной сборке, помеченной атрибутом APTCA.

- `M1` вызывает метод `M2` за пределами `M1`в сборку.

- `M2`в сборки не имеет атрибута APTCA и, таким образом, не будет выполнена, или от имени частично доверенных вызывающих.

Частично доверенного вызывающего `X` можно вызвать метод `M1`, вызывающие `M1` для вызова `M2`. Так как `M2` не имеет атрибута APTCA, его непосредственный вызывающий объект (`M1`) должен удовлетворять запрос ссылки для полного доверия; `M1` имеет полное доверие и пройти проверку. Угроза безопасности возникает, так как `X` не участвует в выполнении требования ссылки, которая защищает `M2` от ненадежных вызывающих объектов. Таким образом методы с атрибутом APTCA не должны вызывать методы, не имеющие атрибута.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Если требуется атрибут APCTA, используйте требование для защиты метода, вызывающего сборку с полным доверием. Точные разрешения, вы запросу будет зависеть от функциональности, предоставляемой методом. Если это возможно, следует Защитите метод требование полного доверия, чтобы убедиться, что частично доверенным вызывающим объектам не предоставляется базовая функциональность. Если это невозможно, выберите набор разрешений, защищающий функциональные возможности.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Чтобы безопасно подавить предупреждение из этого правила, необходимо убедиться, что функции, предоставляемые ваш метод прямо или косвенно позволяет вызывающим объектам доступ к конфиденциальной информации, операции или ресурсы, которые могут использоваться в злонамеренных целях.

## <a name="example-1"></a>Пример 1
 В следующем примере две сборки и тестовое приложение для демонстрации уязвимости системы безопасности, обнаруживаемый этим правилом. Первая сборка не имеет атрибута APTCA и не должны быть доступны частично доверенным вызывающим объектам (представленный `M2` в описании выше).

 [!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example-2"></a>Пример 2
 Вторая сборка является полностью доверенной и позволяет частично доверенным вызывающим объектам (представленный `M1` в описании выше).

 [!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example-3"></a>Пример 3
 Тестовое приложение (представленный `X` в предыдущем описании) является частично доверенным.

 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

В этом примере выводятся следующие данные:

```txt
Demand for full trust:Request failed.
ClassRequiringFullTrust.DoWork was called.
```

## <a name="related-rules"></a>Связанные правила

- [CA2117: APTCA-типы должны расширять только базовые APTCA-типы](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>См. также

- [Правила написания безопасного кода](/dotnet/standard/security/secure-coding-guidelines)
- [Использование библиотек из частично доверенного кода](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
- [Требования связывания](/dotnet/framework/misc/link-demands)
- [Данные и моделирование](/dotnet/framework/data/index)