---
title: Элемент TemplateID (шаблоны Visual Studio) | Документация Майкрософт
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateID
helpviewer_keywords:
- <TemplateID> element [Visual Studio Templates]
- TemplateID element [Visual Studio Templates]
ms.assetid: 6ca24b4e-0325-4a9e-855e-0cbbe7361d8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bcd8f318c66766e016aa146cc5be22ca3c57bb62
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54959922"
---
# <a name="templateid-element-visual-studio-templates"></a>Элемент TemplateID (шаблоны Visual Studio)
Задает идентификатор шаблона элемента, который относится к категории группы шаблонов элементов по [TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md) элемент.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<TemplateID >  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<TemplateID> ... </TemplateID>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Обязательный элемент.<br /><br /> Определяет категорию шаблона и то, отображается ли он в диалоговом окне **Новый проект** или **Добавить новый элемент** .|  
  
## <a name="text-value"></a>Текстовое значение  
 Объект `string` , представляющий идентификатор шаблона элемента, который относится к категории группы шаблонов элементов по `TemplateGroupID` элемент.  
  
## <a name="remarks"></a>Примечания  
 `TemplateID` — это необязательный элемент.  
  
 Если файл .vstemplate не содержит `TemplateID` элемент, а затем [имя](../extensibility/name-element-visual-studio-templates.md) элемент используется в качестве идентификатора для шаблона.  
  
 Значение `TemplateID` используется вместе с регистрацией системы проектов (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Projects\\) для фильтрации шаблонов, которые отображаются в **Добавление нового элемента** диалоговое окно.  
  
## <a name="see-also"></a>См. также  
 [Справочник по схеме шаблонов Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Создание шаблонов проектов и элементов](../ide/creating-project-and-item-templates.md)