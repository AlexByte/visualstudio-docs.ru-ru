---
title: Практическое руководство. Настройка правил производительности | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.ruleseditor
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b4750dcd245094d0ea116097c7e58b87065aa91
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765105"
---
# <a name="how-to-configure-performance-rules"></a>Практическое руководство. Настройка правил производительности
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В предупреждении о производительности средств профилирования Visual Studio указываются проблемы профилируемого приложения, которые могут замедлить выполнение программы. Предупреждения также могут указывать на то, что может потребоваться изменить методы сбора для сбора более полезных данных. Предупреждения о производительности создаются в сеансе профилирования автоматически и отображаются в окне **Список ошибок** при открытии файла данных профилирования в [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]. Некоторые предупреждения могут не соответствовать интересующим вас сценариям, а другие могут быть созданы ошибочно. Можно настроить вывод или блокировку конкретных предупреждений о производительности.  
  
### <a name="to-configure-profiler-performance-warnings"></a>Настройка предупреждений о производительности профилировщика  
  
1.  В меню **Сервис** выберите пункт **Параметры**.  
  
2.  Разверните узел **Средства оценки производительности**, а затем щелкните **Правила**.  
  
3.  Чтобы включить или отключить предупреждение, установите или снимите флажок рядом с **идентификатором** и именем предупреждения.  
  
4.  Чтобы задать порог предупреждений правила, щелкните ячейку **Действие** рядом с правилом и выберите нужный порог.  
  
    -   **Отключено** — отключение правила (соответствует снятию флажка рядом с идентификатором правила).  
  
    -   **Предупреждение** — правило будет отображаться как предупреждение.  
  
    -   **Ошибка** — остановка профилирования и отображение правила в виде ошибки.  
  
    -   **Информация** — отображение правила только как информационного сообщения.



