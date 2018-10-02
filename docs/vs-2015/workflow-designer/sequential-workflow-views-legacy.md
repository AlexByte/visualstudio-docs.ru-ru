---
title: Представления последовательных рабочих процессов (для прежних версий) | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 46c37ec7f3813078b9e70076bf92e6d0e1b86453
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47571739"
---
# <a name="sequential-workflow-views-legacy"></a>Представления последовательных рабочих процессов (для прежних версий)
[!INCLUDE[vs2010](../includes/vs2010-md.md)] предоставляет средство [!INCLUDE[wfd1](../includes/wfd1-md.md)] прежних версий, которое можно использовать для приложений, работающих с [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] или [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 [!INCLUDE[wfd2](../includes/wfd2-md.md)] предоставляет способ создания с помощью графических средств приложений [!INCLUDE[wf](../includes/wf-md.md)] с использованием знакомого пользовательского интерфейса [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Приложения [!INCLUDE[wf](../includes/wf-md.md)] состоят из этапов рабочего процесса, называемых действиями. Чтобы создать рабочий процесс, объедините действия в области конструктора, перетащив конструкторы нужных действий из **элементов** в область конструктора.  
  
 При создании последовательного рабочего процесса, который является [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040), доступны три представления рабочего процесса. Эти представления доступны из **рабочего процесса** меню и в контекстном меню в области конструктора.  
  
 В следующей таблице перечислены имена и описание каждого представления.  
  
|Параметры меню/вкладок|Описание|  
|----------------------|-----------------|  
|**Представление SequentialWorkflow**|Щелкните правой кнопкой мыши область конструктора и выберите **представление SequentialWorkflow** параметр в контекстном меню, чтобы отобразить **последовательный рабочий процесс** представление, которое показывает, основанные на действиях графическое представление последовательного рабочего процесса. Или выберите **представление SequentialWorkflow** из **рабочего процесса** меню.|  
|**Просмотр обработчика отмены**|Щелкните правой кнопкой мыши область конструктора и выберите **Просмотр обработчика отмены** параметр в контекстном меню, чтобы отобразить **последовательный рабочий процесс** просмотра, которое показывает [CancellationHandlerActivity ](http://go.microsoft.com/fwlink?LinkID=65050) действия, связанного с рабочим процессом. Или выберите **Просмотр обработчика отмены** из **рабочего процесса** меню.|  
|**Просмотр обработчика ошибок**|Щелкните правой кнопкой мыши область конструктора и выберите **Просмотр обработчика ошибок** параметр в контекстном меню, чтобы отобразить **ошибок** просмотра, которое показывает [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) действие, связанное с рабочим процессом. Или выберите **Просмотр обработчика ошибок** из **рабочего процесса** меню.|  
  
 Дополнительные сведения о похожих представлениях см. в разделе [представления действий (для прежних версий)](../workflow-designer/activity-views-legacy.md).  
  
## <a name="see-also"></a>См. также  
 [Представления действий (для прежних версий)](../workflow-designer/activity-views-legacy.md)   
 [Создание проектов рабочих процессов для прежних версий](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Режимы разработки рабочего процесса](http://go.microsoft.com/fwlink?LinkID=65014)