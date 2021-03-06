---
title: 'Практическое: отладка рабочих процессов, основанных на ASP.NET (устаревшая версия) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: b9da40b0b40216fc36ea45b199ecde9c6dc4a89d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49236890"
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>Как отлаживать рабочие процессы, основанные на ASP.NET (для прежних версий)
В этом разделе описывается отладка основанных на [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] приложений [!INCLUDE[wf](../includes/wf-md.md)], которые ориентируются на работу с [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] или [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] в средстве [!INCLUDE[wfd1](../includes/wfd1-md.md)] прежних версий.  
  
 Отладку рабочих процессов прежних версий, которые запущены в ASP.NET, или рабочих процессов более ранней версии, которые опубликованы как веб-службы, можно выполнить посредством присоединения к процессу, в котором размещается рабочий процесс.  
  
### <a name="to-debug-an-aspnet-based-workflow"></a>Отладка рабочих процессов, основанных на ASP.NET  
  
1.  Включить отладку для приложения ASP.NET, задав **debug = true** в файле web.config.  
  
2.  Установите библиотеку рабочего процесса как автозагружаемый проект, установите в рабочем процессе точки останова.  
  
3.  Введите URL-адрес веб-страницы по умолчанию в свойствах проекта рабочего процесса **Отладка** параметр **запустить браузер, используя внешний URL-адрес** текстовое поле.  
  
4.  Выберите **присоединение к процессу** на **Отладка** меню.  
  
5.  Выберите процесс для присоединения из **доступные процессы** списка.  
  
     Присоединение к процессу w3wp.exe, webdev.webserver или aspnet_wp, в котором размещается рабочий процесс.  
  
6.  Нажмите кнопку **выберите** рядом с полем **присоединение к** текстовое поле.  
  
     **Выбор типа кода** откроется диалоговое окно.  
  
7.  Выберите **отладить код следующих типов** и выберите **рабочего процесса**.  
  
8.  Нажмите кнопку **ОК**.  
  
9. Нажмите кнопку **Присоединить**.  
  
10. Откройте веб-страницу по умолчанию в браузере и запустите рабочий процесс.  
  
## <a name="see-also"></a>См. также  
 [Вызов отладчика Visual Studio для Windows Workflow Foundation (для прежних версий)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)   
 [Практическое: задайте точки останова в рабочих процессах (для прежних версий)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)   
 [Отладка рабочих процессов прежних версий](../workflow-designer/debugging-legacy-workflows.md)