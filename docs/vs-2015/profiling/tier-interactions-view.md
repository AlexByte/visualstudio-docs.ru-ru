---
title: Представление "Взаимодействия уровня" | Документы Майкрософт
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
- vs.performance.view.tierinteraction
helpviewer_keywords:
- Tier Interactions view
ms.assetid: bb4fb21c-f3f7-473a-8b5e-442da4c2c445
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b69144569738dc09368453faef13f5f38428df2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51726163"
---
# <a name="tier-interactions-view"></a>Представление "Взаимодействие между уровнями"
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Профилирование уровневого взаимодействия позволяет получить дополнительные сведения о времени выполнения в функциях многоуровневых приложений, взаимодействующих с базой данных посредством [!INCLUDE[vstecado](../includes/vstecado-md.md)]. Данные собираются только для синхронных вызовов функций.  
  
 **Требования**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)]  
  
  В представлении взаимодействия сведения об уровневом взаимодействии отображаются в двух областях.  
  
- Главная область представляет собой иерархическое дерево. Строка верхнего уровня содержит статистические данные для подключений страницы или процесса [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] к базе данных. Дочерние узлы содержат статистические данные по подключениям родительского узла к базе данных.  
  
- Если щелкнуть узел вызова базы данных в главной области, то в области сведений будут показаны сведения об экземпляре вызова базы данных.  
  
  Время отображается в виде числа миллисекунд или числа тактов процессора. Для изменения отображаемой единицы времени откройте меню **Сервис**, выберите пункт **Параметры**, а затем выберите одно из значений параметра **Показывать значения времени как**.  
  
## <a name="master-pane"></a>Главная область  
  
|Столбец|Описание:|  
|------------|-----------------|  
|**Name**|— Для строки верхнего уровня — имя профилируемого процесса или веб-страницы.<br />— Для строки подключения к базе данных — имя сервера, на котором располагается база данных.|  
|**База данных**|Имя базы данных (только для строк подключения к базе данных).|  
|**Количество**|Общее число запросов, созданных процессом, веб-страницей или подключением к базе данных.|  
|**Общее затраченное время**|Общее количество времени, затраченного на выполнение любого запроса из процесса, веб-страницы или подключения к базе данных.|  
|**Максимальное затраченное время**|Максимальное количество времени, затраченного на выполнение любого запроса из процесса, веб-страницы или подключения базы данных.|  
|**Минимальное затраченное время**|Минимальное количество времени, затраченного на выполнение любого запроса из процесса, веб-страницы или подключения базы данных.|  
|**Среднее затраченное время**|Среднее количество времени, затраченного на выполнение запроса из процесса, веб-страницы или подключения базы данных.|  
  
## <a name="database-connection-details-pane"></a>Область сведений о подключении к базе данных  
  
|Столбец|Описание:|  
|------------|-----------------|  
|**Текст команды**|SQL-запрос в запросе.|  
|**Количество запросов**|Количество запусков запроса.|  
|**Общее затраченное время**|Общее время, затраченное на выполнение экземпляров запроса.|  
|**Максимальное затраченное время**|Максимальное время, затраченное на выполнение любого экземпляра запроса.|  
|**Минимальное затраченное время**|Минимальное время, затраченное на выполнение любого экземпляра запроса.|  
|**Среднее затраченное время**|Среднее время, затраченное на выполнение экземпляра запроса.|



