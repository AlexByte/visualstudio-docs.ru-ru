---
title: Присоединение строк ссылок к элементам модели UML | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML - extending, reference strings
ms.assetid: 15dbed99-efce-42fe-a768-714a5804e7d1
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: cf8a9e7e023e9c75f61fdf9a6bfb608edc3a7123
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51804590"
---
# <a name="attach-reference-strings-to-uml-model-elements"></a>Присоединение строк ссылок к элементам модели UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Вы можете написать код для присоединения произвольных строк к элементам модели. Строкой может быть, например, универсальный код ресурса (URI), кэшированный результат вычислений или ссылка ModelBus на элемент в другой модели. Каждая строка содержится в объекте IReference. К каждому элементу модели можно присоединить любое число объектов IReference.  
  
 У каждого объекта IReference есть имя. Это имя можно использовать для обозначения способа интерпретации значения ссылки. Например, можно задать в качестве имени URI, указав тем самым, что значение следует интерпретировать как универсальный код ресурса (URI). Существует несколько предварительно определенных значений имени ссылки, используемых средствами моделирования.  
  
## <a name="attaching-a-reference-to-an-ielement"></a>Присоединение ссылки к объекту IElement  
 Чтобы использовать описанные ниже методы, необходимо добавить следующую ссылку:  
  
 Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll  
  
 В код необходимо добавить следующую директиву:  
  
 `using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;`  
  
|Вызов метода|Описание:|  
|-----------------|-----------------|  
|`element.AddReference (nameString, valueString, duplicatesAllowed)`|Создает объект `IReference` с указанными строками имени и значения и связывает его с `element`. Возвращает `IReference`.<br /><br /> Вызывает исключение, если значение `duplicatesAllowed` равно false и уже существует объект `IReference` с таким именем, присоединенный к `element`.|  
|`element.GetReferences(name)`|Возвращает все объекты `IReference`, связанные с `element`, с заданным значением `name`.|  
|`element.DeleteAllReferences(name)`|Удаляет все объекты `IReference`, связанные с элементом с заданным именем.|  
|`reference.Delete()`|Удаляет этот объект `IReference`.|  
|`ReferenceConstants.WorkItem`|Значение, используемое для именования ссылок на рабочие элементы.|  
  
## <a name="see-also"></a>См. также  
 [Определение обработчика связей рабочего элемента](../modeling/define-a-work-item-link-handler.md)   
 [Определение и Установка расширения моделирования](../modeling/define-and-install-a-modeling-extension.md)   
 [Программирование с UML API](../modeling/programming-with-the-uml-api.md)



