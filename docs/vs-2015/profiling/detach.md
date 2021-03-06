---
title: Параметр Detach | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9d1b52c-7f28-467d-b1e0-512afc4e46c9
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97e5e64947f2d2807e2d3e34d50827e989ea18e2
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804725"
---
# <a name="detach"></a>Detach
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Параметр **Detach** программы VSPerfCmd.exe отключает профилировщик от заданных процессов или от всех процессов, если процессы не заданы. Для инициализации профилирования нужно использовать метод выборки.  
  
 Профилирование, запущенное с параметром **Launch** или **Attach**, можно отключить с помощью параметра **Detach**. Для повторного подключения профилировщика можно воспользоваться командами **Attach**.  
  
 Параметр **Detach** не приводит к закрытию файла данных профилирования. Чтобы завершить профилирование и закрыть файл данных, воспользуйтесь параметром **Shutdown**.  
  
> [!NOTE]
>  Если параметр **Start** был задан с параметром **Crosssession**, во всех вызовах команды **VSPerfCmd /Attach** или **VSPerfCmd /Detach** также должен быть указан параметр **Crosssession**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
VSPerfCmd.exe /Detach[:PIDs|ProcessNames]  
```  
  
#### <a name="parameters"></a>Параметры  
 `PIDs|ProcessNames`  
 `PID` — числовой системный идентификатор одного или нескольких процессов.  
  
 `ProcessNames` — имя процесса. Если запущено несколько экземпляров именованного процесса, результат будет непредсказуемым.  
  
 Разделяйте процессы запятыми.  
  
 Если процесс не задан, профилировщик отключится от всех профилируемых процессов.  
  
## <a name="valid-options"></a>Допустимые параметры  
 Указанные ниже параметры программы **VSPerfCmd** могут сочетаться с параметром **Attach** в одной командной строке.  
  
 **Crosssession**  
 Включает профилирование приложений в сеансах, отличных от сеанса входа в систему. Является обязательным, если параметр **Start** был задан с параметром **Crosssession**.  
  
## <a name="example"></a>Пример  
 В этом примере команда **Detach** приостанавливает профилирование, а команда **Shutdown** закрывает файл данных профилировщика.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
;REM Excercise the application  
VSPerfCmd.exe /Detach  
VSPerfCmd.exe /Shutdown  
```  
  
## <a name="see-also"></a>См. также  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Профилирование веб-приложений ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Профилирование служб](../profiling/command-line-profiling-of-services.md)



