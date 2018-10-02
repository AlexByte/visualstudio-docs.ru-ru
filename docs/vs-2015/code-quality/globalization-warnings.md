---
title: Предупреждения глобализации | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.globalizationrules
helpviewer_keywords:
- warnings, globalization
- globalization warnings
- globalization [Visual Studio], warnings
- managed code analysis warnings, globalization warnings
ms.assetid: a8d12d41-14bf-4b43-af24-168312d7c390
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2430b5cac7f3cbdf7d871f574438508fee0e625b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47572587"
---
# <a name="globalization-warnings"></a>Предупреждения глобализации
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [предупреждения глобализации](https://docs.microsoft.com/visualstudio/code-quality/globalization-warnings).  
  
Предупреждения глобализации поддерживают международные библиотеки и приложения.  
  
## <a name="in-this-section"></a>В этом разделе  
  
|Правило|Описание|  
|----------|-----------------|  
|[CA1300: укажите MessageBoxOptions](../code-quality/ca1300-specify-messageboxoptions.md)|Чтобы окно сообщения для языков, в которых используется порядок чтения справа налево, отображалось правильно, методу Show следует передать члены RightAlign и RtlReading перечисления MessageBoxOptions.|  
|[CA1301: не следует допускать повторяющихся сочетаний клавиш быстрого доступа](../code-quality/ca1301-avoid-duplicate-accelerators.md)|Клавиша доступа, также называемая клавишей быстрого доступа, обеспечивает клавиатурный доступ к элементу управления с помощью клавиши ALT. Если несколько элементов управления имеют дублирующиеся клавиши доступа, поведение клавиши доступа определено нечетко.|  
|[CA1302: не следует жестко кодировать строки, зависящие от языка](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|Перечисление System.Environment.SpecialFolder содержит члены, ссылающиеся на специальные системные папки. Расположение этих папок может различаться в разных ОС, пользователь может менять расположение этих папок, их имена могут быть локализованы. Метод Environment.GetFolderPath возвращает связанные с перечислением Environment.SpecialFolder расположения в локализованной форме, подходящей для использования на работающем в данный момент компьютере.|  
|[CA1303: не следует передавать литералы в виде локализованных параметров](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|Внешне видимый метод передает строковый литерал в виде параметра конструктору или методу в библиотеке классов [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], и эта строка должна быть локализуемой.|  
|[CA1304: укажите CultureInfo](../code-quality/ca1304-specify-cultureinfo.md)|Метод или конструктор вызывает член, имеющий перегрузку, которая принимает параметр System.Globalization.CultureInfo, вместо того чтобы вызвать перегрузку, принимающую параметр CultureInfo. Если объект CultureInfo или System.IFormatProvider не предоставляется, значение по умолчанию, поставляемое перегруженным членом, может не оказать ожидаемого воздействия во всех языковых стандартах.|  
|[CA1305: укажите IFormatProvider](../code-quality/ca1305-specify-iformatprovider.md)|Метод или конструктор вызывает один или несколько членов, имеющих перегрузки, которые принимают параметр System.IFormatProvider, вместо того чтобы вызвать перегрузку, принимающую параметр IFormatProvider. Если объект System.Globalization.CultureInfo или IFormatProvider не предоставляется, значение по умолчанию, поставляемое перегруженным членом, может не оказать ожидаемого воздействия во всех языковых стандартах.|  
|[CA1306: указывайте языковой стандарт для типов данных](../code-quality/ca1306-set-locale-for-data-types.md)|Язык и региональные параметры определяют представление элементов данных, таких как формат чисел, обозначение денежных единиц и порядок сортировки. При создании объектов DataTable или DataSet следует явным образом указывать языковой стандарт.|  
|[CA1307: укажите StringComparison](../code-quality/ca1307-specify-stringcomparison.md)|В операции сравнения строк используется перегрузка метода, которая не задает параметр StringComparison.|  
|[CA1308: строки следует нормализовать в верхнем регистре](../code-quality/ca1308-normalize-strings-to-uppercase.md)|Строки следует нормализовать в верхний регистр. Существует небольшая группа символов, которые после преобразования в нижний регистр не могут участвовать в круговом перемещении.|  
|[CA1309: используйте порядковый параметр StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)|Операция сравнения строк, не являющаяся лингвистической, не задает для параметра StringComparison ни значения Ordinal, ни значения OrdinalIgnoreCase. После явного задания для параметра значения StringComparison.Ordinal или StringComparison.OrdinalIgnoreCase код часто становится более надежным и правильным, кроме того, увеличивается скорость его выполнения.|  
|[CA2101: укажите тип маршалинга для строковых аргументов P/Invoke](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|Неуправляемого член позволяет частично доверенным вызывающим объектам, содержит строковый параметр и явным образом не маршалинга этой строки. Это может стать причиной потенциальной уязвимости безопасности.|


