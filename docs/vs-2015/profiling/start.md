---
title: Start | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b85d0fe9-f67a-4b7c-8d48-7eecf3f2dfe9
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c2f52a000cdf5eaa1a1ef4b9afeb141500f1911
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51724176"
---
# <a name="start"></a>Запуск
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Start** — это параметр программы VSPerfCmd.exe, который инициализирует профилировщик для использования указанного метода профилирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>Параметры  
 `Method`  
 Должен иметь в качестве значения одно из следующих ключевых слов:  
  
-   **TRACE** — задает метод инструментирования;  
  
-   **SAMPLE** — задает метод выборки;  
  
-   **COVERAGE** — задает объем протестированного кода;  
  
-   **CONCURRENCY** — задает метод состязания за ресурсы.  
  
## <a name="required-options"></a>Обязательные параметры  
 Если в командной строке задан параметр **Start**, необходимо указать параметр **Output**.  
  
 **Output:** `filename`  
 Задает имя выходного файла.  
  
## <a name="exclusive-options"></a>Монопольные параметры  
 Указанные ниже параметры могут использоваться только с параметром **Start** в командной строке.  
  
 **CrossSession**&#124;**CS**  
 Включает профилирование в нескольких процессах. Поддерживаются оба имени параметра: **CrossSession** и **CS**.  
  
 **User:**[`domain\`]`username`  
 Позволяет клиентам получать доступ к монитору с помощью указанной учетной записи.  
  
 **WinCounter:** `Path` [**Automark**:`n`]  
 **WinCounter** задает счетчик производительности Windows, который включается в файл данных профилирования в виде метки. **AutoMark** задает интервал в миллисекундах между сборами файла данных.  
  
## <a name="invalid-options"></a>Недопустимые параметры  
 Указанные ниже параметры не могут использоваться с параметром **Start** в командной строке.  
  
 **Status**  
 Параметр **Status** применяется к процессам, для которых выполняется профилирование. Этот параметр перечисляет процессы и потоки и их текущее состояние профилирования (On/Off). Например, если процесс остановлен, параметр **Status** не отразит это в отчете. **Status** показывает, выполняется ли профилирование для процесса или нет.  
  
 **Shutdown**[**:**`Timeout`]  
 Отключает профилировщик.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере кода показано, как с помощью параметра **Start** программы VSPerfCmd.exe инициализировать профилировщик.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>См. также  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Профилирование веб-приложений ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Профилирование служб](../profiling/command-line-profiling-of-services.md)



