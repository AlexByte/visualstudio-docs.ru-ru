---
title: 'CA1820: Проверьте наличие пустых строк, длина строки | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 680a9ee1681a98176f2c21fc989331bf82aa2b15
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49861024"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: проверьте наличие пустых строк путем проверки длины строки
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|Категория|Microsoft.Performance|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Строка сравнивается с пустой строкой, используя <xref:System.Object.Equals%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Описание правила
 Сравнение строк с помощью <xref:System.String.Length%2A?displayProperty=fullName> свойство или <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> значительно быстрее, чем использование метода <xref:System.Object.Equals%2A>. Это обусловлено <xref:System.Object.Equals%2A> выполняет значительно больше инструкции MSIL, чем любая <xref:System.String.IsNullOrEmpty%2A> или количество выполненных для получения инструкций <xref:System.String.Length%2A> свойство значение и сравнить это значение ноль.

 Следует иметь в виду, <xref:System.Object.Equals%2A> и <xref:System.String.Length%2A> == 0 ведут себя по-разному для строки null. Если попытаться получить значение <xref:System.String.Length%2A> свойство для строки null, среда CLR создает <xref:System.NullReferenceException?displayProperty=fullName>. Если выполнить сравнение строку null и пустые строки, среда CLR создает исключения; Операция сравнения возвращает `false`. Проверка значений null не оказывает существенного влияния относительную производительность этих двух подходов. При нацеливании на [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], используйте <xref:System.String.IsNullOrEmpty%2A> метод. В противном случае используйте <xref:System.String.Length%2A> == сравнения, когда это возможно.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, измените выражение, чтобы использовать <xref:System.String.Length%2A> свойства и выполнить проверку пустая строка. Если планируется использовать [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], используйте <xref:System.String.IsNullOrEmpty%2A> метод.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Его можно безопасно подавить предупреждение из этого правила, если производительность не является проблемой.

## <a name="example"></a>Пример
 В следующем примере показано различные методики, которые используются для поиска пустой строкой.

 [!code-csharp[FxCop.Performance.StringTest#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.StringTest/cs/FxCop.Performance.StringTest.cs#1)]



