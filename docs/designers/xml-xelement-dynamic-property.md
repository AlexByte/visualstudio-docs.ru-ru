---
title: Xml (динамическое свойство XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 87796afcc06190a54a3670581be7700fa8d49061
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53940563"
---
# <a name="xml-xelement-dynamic-property"></a>Xml (динамическое свойство XElement)

Возвращает неформатированное XML-содержимое элемента.

## <a name="syntax"></a>Синтаксис

```xaml
elem.Xml
```

## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Значение <xref:System.String>, представляющее неформатированное XML-содержимое элемента.

## <a name="remarks"></a>Примечания

Это свойство эквивалентно методу <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> класса <xref:System.Xml.Linq.XNode?displayProperty=fullName> с параметром `SaveOptions`, установленным равным <xref:System.Xml.Linq.SaveOptions>.

## <a name="see-also"></a>См. также

- [Динамические свойства класса XElement](../designers/xelement-class-dynamic-properties.md)
- [Значение](../designers/value-xelement-dynamic-property.md)