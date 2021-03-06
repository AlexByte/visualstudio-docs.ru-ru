---
title: Отладка клиентского скрипта | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], client-side scripts
- client-side scripts, debugging
ms.assetid: bb668527-2288-47bd-a6c8-cecbad76dde2
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3aa04ab77b6e3dc6264a517c83c4ed319f36d686
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51817806"
---
# <a name="client-side-script-debugging"></a>Отладка клиентского скрипта
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Отладчик Visual Studio предоставляет всеобъемлющую среду отладки для обнаружения и исправления ошибок в скриптах на стороне клиента на страницах ASP.NET.  
  
## <a name="opening-script-documents"></a>Открытие документов скрипта  
 Используйте окно **Обозреватель решений** , чтобы просмотреть списки серверных и клиентских документов скрипта. В окне **Обозреватель решений**можно открыть любой документ скрипта. Для получения дополнительной информации см. [How to: View Script Documents](../debugger/how-to-view-script-documents.md).  
  
## <a name="breakpoint-mapping"></a>Сопоставление точек останова  
 В Visual Studio невозможно непосредственно отлаживать код на стороне сервера, но можно установить точку останова в файле, находящемся на сервере. Visual Studio автоматически сопоставляет точку останова с соответствующим расположением в файле на стороне клиента и создает сопоставленную точку останова в коде на стороне клиента.  
  
## <a name="manually-or-automatically-attaching-to-script"></a>Автоматическое присоединение к скрипту или присоединение к скрипту в ручном режиме  
 Чтобы начать отладку скрипта в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], отладчику необходимо выполнить присоединение к скрипту, для которого необходимо выполнить отладку. Присоединение может быть выполнено в ручном режиме или автоматически.  
  
 Можно выполнить присоединение в ручном режиме, используя интерфейс отладчика [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , чтобы выбрать процесс выполняющегося скрипта, к которому необходимо выполнить присоединение. Для получения дополнительной информации см. [How to: Attach to Script](../debugger/how-to-attach-to-script.md).  
  
 Отладчик автоматически выполняет присоединение к скрипту при возникновении одного из следующих условий:  
  
- Достижение точки останова, установленной в скрипте.  
  
- Достижение оператора VBScript `Stop` или оператора JScript `debugger` в коде скрипта.  
  
- В браузере или сервере обнаруживается синтаксическая ошибка или ошибка во время выполнения в скрипте. Когда это происходит, появляется диалоговое окно с возможностью начать отладку.  
  
  При присоединении к скрипту в ручном режиме процесс скрипта продолжает выполняться до завершения по каким-либо причинам. Можно остановить выполнение этого скрипта с помощью команды **Прервать** в меню **Отладка** .  
  
  При автоматическом присоединении отладчика выполнение скрипта завершается на строке с точкой останова оператором `Stop` или оператором `debugger` , либо на строке, в которой возникает ошибка, либо в точке, в которой выбрано начать отладку в Internet Explorer.  
  
  В данной точке можно использовать обычные функции отладчика, чтобы начать отладку. Например, можно использовать команды **Шаг** , чтобы продолжить выполнять код построчно. Можно использовать окно **Стек вызовов** , чтобы просматривать и контролировать течение скрипта. Можно использовать окна переменных или окно **Интерпретация** , чтобы просматривать и изменять переменные и свойства.  
  
## <a name="enhanced-error-messages-for-script-debugging"></a>Улучшенные сообщения об ошибках для отладки скриптов  
 В Visual Studio представлены улучшенные сообщения об ошибках для общих проблем отладки скриптов. Эти сообщения не появляются, если не выполнить присоединение к Internet Explorer вручную. При возникновении условия, вызывающего ошибку при автоматическом открытии Internet Explorer, попытайтесь выполнить присоединение вручную, чтобы увидеть сообщения об ошибках.  
  
## <a name="debugging-ajax-script-applications"></a>Отладка приложений Ajax-скриптов  
 Веб-приложения с включенной технологией Ajax делают сложным использование кода скрипта и ставят проблемы специальной отладки. Дополнительные сведения о методах отладки Ajax см. в разделе  
  
 [Debugging and Tracing Ajax Applications Overview](http://msdn.microsoft.com/library/92684ea0-7bb4-4a34-9203-3aa6394ce375)можно открыть любой документ скрипта.  
  
## <a name="see-also"></a>См. также  
 [Отладка приложений ASP.NET и AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Ограничения на отладку скриптов](../debugger/limitations-on-script-debugging.md)   
 [Переменной Windows](http://msdn.microsoft.com/library/ce0a67f6-2502-4b7a-ba45-cc32f8aeba3e)   
 [Окно интерпретации](../ide/reference/immediate-window.md)   
 [Debugging and Tracing Ajax Applications Overview](http://msdn.microsoft.com/library/92684ea0-7bb4-4a34-9203-3aa6394ce375)



