---
title: Профилирование и безопасность Windows Vista | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
caps.latest.revision: 24
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 32605cb21b79e035bba9d234cdb7b3d513417363
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51772954"
---
# <a name="profiling-and-windows-vista-security"></a>Профилирование и безопасность Windows Vista
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В зависимости от параметров разрешений на доступ пользователей [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)], предоставленных администратором компьютера, отдельный пользователь может иметь разрешение безопасности для профилирования процесса на этом компьютере. Возможные различия между пользователями проиллюстрированы в следующих примерах:  
  
- Некоторые пользователи могут воспользоваться расширенными возможностями профилирования, если администратор задал драйвер и запускаемую службу.  
  
- Пользователям домена доступно только профилирование выборки.  
  
- Некоторые пользователи могут запрещать доступ к профилированию всем другим пользователям.  
  
  Дополнительные сведения см. в разделе [VSPerfCmd](../profiling/vsperfcmd.md) в описании параметров ADMIN.  
  
## <a name="cross-session-profiling"></a>Профилирование в нескольких сеансах  
 *Профилирование в нескольких сеансах* означает возможность профилирования процесса, запущенного в различных сеансах входа в систему. Например, большинство служб выполняется в сеансе 0, и пользователи не могут запускать что-либо непосредственно в сеансе 0. С помощью кнопки **Присоединиться к процессу** на панели инструментов обозревателя производительности или параметр /attach средства командной строки VSPerfCmd, можно выполнить профилирование большинства процессов в различных сеансах входа в систему.  
  
 Управлять списком доступных процессов можно посредством установки параметров видимости процессов для профилирования. Эти параметры доступны в диалоговом окне **Присоединение к процессу**, которое отображается после нажатия кнопки **Присоединиться к процессу**.  
  
-   **Показать процессы, запущенные всеми пользователями**  
  
     Если этот параметр не выбран, в списке отображаются только процессы, принадлежащие текущему пользователю. При выборе параметра **Показать процессы, запущенные всеми пользователями** в списке отображаются процессы, принадлежащие всем пользователям.  
  
-   **Показать процессы во всех сеансах**  
  
     Если этот параметр не выбран, в списке отображаются процессы в текущем сеансе. Если этот параметр выбран, в списке отображаются процессы во всех сеансах.  
  
## <a name="see-also"></a>См. также  
 [Разделы общих сведений](../profiling/overviews-performance-tools.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Практическое руководство. Присоединение к выполняемому процессу](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)



