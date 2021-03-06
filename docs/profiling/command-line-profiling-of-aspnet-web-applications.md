---
title: Профилирование веб-приложений ASP.NET из командной строки | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling ASP.NET applications
- profling tools,ASP.NET applications
ms.assetid: 897c00d5-5767-433b-a960-4a29c6023ede
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 2b2f4602e56a89452635ebe0ad94dbc1664c2fb3
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "53835348"
---
# <a name="command-line-profiling-of-aspnet-web-applications"></a>Профилирование веб-приложений ASP.NET из командной строки
В этом разделе описываются процедуры и параметры сбора данных о производительности для веб-приложений [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] с помощью средств профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] из командной строки.  
  
> [!NOTE]
>  Возможности расширенной безопасности в Windows 8 и Windows Server 2012 требовали значительных изменений в способе, которым профилировщик Visual Studio собирает данные на этих платформах. Для приложений универсальной платформы Windows также требуются новые методы сбора. Дополнительные сведения см. в статье [Средства оценки производительности в приложениях Windows 8 и Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Типичные задачи
  
| Задача | Связанное содержимое |
| - | - |
| **Удобный сбор базовых данных профилирования ASP.NET.** Используйте средство **VSPerfASPNETCmd** для сбора данных по выборкам, инструментированию, памяти .NET, конфликтам и взаимодействию уровней без настройки и без перезапуска Internet Information Services (IIS), которые требовались при работе с **VSPerfCmd**. **Средство VSPerfASPNETCmd** не позволяет собирать дополнительные данные или контролировать сбор данных. **Примечание.**  **VSPerfASPNETCmd** удобно использовать в случае, если необходим автономный профилировщик для профилирования веб-сайтов ASP.NET. | -   [Быстрое профилирование веб-сайтов с помощью средства VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md) |
| **Сбор статистики приложения.** Использование метода выборки для сбора статистики производительности. Данные выборки служат для анализа проблем использования ЦП и для изучения общих характеристик производительности приложения. | -   [Сбор статистики приложения с помощью метода выборки](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md) |
| **Сбор подробных сведений о времени.** Использование метода инструментирования для сбора подробных сведений о времени. Данные инструментирования удобно использовать для анализа ошибок ввода-вывода и подробного анализа сценариев приложений. | -   [Сбор подробных сведений о времени с помощью инструментирования](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md) |
| **Сбор данных об использовании памяти .NET.** Использование выборки или инструментирования для сбора данных о выделения памяти .NET, содержащих размер и количество объектов, для которых выделена память. Кроме того, можно собирать данные о времени существования объектов, в которых указывается размер и количество объектов, собранных в каждом поколении сборки мусора. | -   [Сбор данных об использовании памяти](../profiling/collecting-memory-data-from-an-aspnet-web-application.md) |
| **Сбор данных о параллелизме.** Использование метода параллелизма для сбора данных о конфликтах ресурсов. **Примечание.**  Недоступен сбор сведений об активности потока и визуализация данных для веб-приложений. | -   [Сбор данных параллелизма](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md) |
| **Добавление данных взаимодействия между уровнями.** Можно добавлять данные производительности о синхронных вызовах [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)], выполняемых веб-приложением [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] к базе данных Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]. | -   [Сбор данных о взаимодействии уровней](../profiling/adding-tier-interaction-data-from-the-command-line.md) |
  
## <a name="related-tasks"></a>Связанные задачи

  
|Задача|Связанное содержимое|  
|----------|---------------------|  
|**Профилирование автономных (клиентских) приложений**|-   [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Профилирование служб**|-   [Профилирование служб](../profiling/command-line-profiling-of-services.md)|