---
title: Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75d38b76-26d6-4f43-bbe7-cbacd7cc81e7
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 26ece0c0d46e5c747ac05bae8c2d4fc793c34601
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49207406"
---
# <a name="how-to-view-save-and-configure-build-log-files"></a>Практическое руководство. Просмотр, сохранение и настройка файлов журнала построения
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

После сборки проекта в интегрированной среде разработки Visual Studio вы можете просмотреть сведения об этой сборке в окне **Вывод**. С помощью этих сведений можно, например, найти и устранить сбой при сборке. Для проектов C++ те же самые сведения можно просмотреть в TXT-файле, который создается и сохраняется автоматически. Для проектов управляемого кода можно скопировать и вставить данные из окна **Вывод** в TXT-файл и сохранить его. Кроме того, можно прямо в интегрированной среде разработки указать, какие сведения вы хотите просмотреть о каждой сборке.  
  
 Если вы создаете любые типы проектов с помощью MSBuild, можете создать TXT-файл для хранения сведений о сборке. Дополнительные сведения см. в разделе [Получение журналов сборки](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
### <a name="to-view-the-build-log-file-for-a-c-project"></a>Просмотр файла журнала сборки для проекта C++  
  
1.  Откройте следующий файл в **проводнике****проводнике**: \\...\Visual Studio *версия*\Projects\\*имя_проекта*\\*имя_проекта*\Debug\\*имя_проекта*.txt  
  
### <a name="to-create-a-build-log-file-for-a-managed-code-project"></a>Создание файла журнала сборки для проекта управляемого кода  
  
1.  В строке меню последовательно выберите **Сборка**и **Собрать решение**.  
  
2.  В окне **Вывод** выделите данные из сборки, а затем скопируйте их в буфер обмена.  
  
3.  Откройте текстовый редактор, например "Блокнот", вставьте данные в файл и сохраните его.  
  
### <a name="to-change-the-amount-of-information-included-in-the-build-log"></a>Изменение объема сведений, включенных в журнал сборки  
  
1.  В строке меню выберите **Сервис**, **Параметры**.  
  
2.  На странице **Проекты и решения** выберите страницу **Сборка и запуск**.  
  
3.  В списке **Степень подробности сообщений при построении проекта MSBuild** выберите одно из указанных ниже значений, а затем нажмите кнопку **ОК**.  
  
    |Уровень детализации|Описание|  
    |---------------------|-----------------|  
    |Тихий NaN|Отображает только сводку по сборке.|  
    |Минимальный|Отображает сводку по сборке, а также ошибки, предупреждения и сообщения с высокой важностью.|  
    |Норм.|Отображает сводку по сборке, ошибки, предупреждения и сообщения с высокой важностью, а также основные шаги сборки. Этот уровень детализации будет использоваться чаще всего.|  
    |Подробный|Отображает сводку по сборке, ошибки, предупреждения и сообщения с высокой важностью, все шаги сборки, а также сообщения с обычной важностью.|  
    |Диагностический|Отображает все данные, которые доступны для сборки. Этот уровень детализации можно использовать для исправления проблем с пользовательскими скриптами сборки и других проблем сборки.|  
  
     Дополнительные сведения см. в разделах [Диалоговое окно "Параметры", "Проекты и решения", "Сборка и запуск"](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md) и <xref:Microsoft.Build.Framework.LoggerVerbosity>.  
  
    > [!IMPORTANT]
    >  Вам нужно перестроить проект, чтобы изменения в окне **Вывод** (все проекты) и *файле ProjectName*.txt (только проекты C++) вступили в силу.  
  
## <a name="see-also"></a>См. также  
 [Получение журналов построения](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Building and Cleaning Projects and Solutions in Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)  (Построение и очистка проектов и решений в Visual Studio)  
 [Компилирование и сборка](../ide/compiling-and-building-in-visual-studio.md)



