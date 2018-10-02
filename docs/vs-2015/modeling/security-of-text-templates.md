---
title: Безопасность текстовых шаблонов | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4ce9ccca0a144de7101e886712105315ec64fa75
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559450"
---
# <a name="security-of-text-templates"></a>Безопасность текстовых шаблонов
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [безопасность текстовых шаблонов](https://docs.microsoft.com/visualstudio/modeling/security-of-text-templates).  
  
Текстовые шаблоны имеют следующие рекомендации по безопасности:  
  
-   Текстовые шаблоны уязвимы для произвольного кода.  
  
-   Если механизм, используемый узлом для поиска процессор директив не является безопасным, может быть запущен вредоносный процессор директив.  
  
## <a name="arbitrary-code"></a>Произвольный код  
 При написании шаблона, можно поместить код в пределах \<## > теги. Это позволяет произвольный код, выполняемый из текстового шаблона.  
  
 Убедитесь, что получение шаблонов из надежных источников. Убедитесь в том, что предупредите конечных пользователей приложения не следует выполнять шаблоны, которые не исходят из надежных источников.  
  
## <a name="malicious-directive-processor"></a>Вредоносный процессор директив  
 Шаблон текста взаимодействует с узлом преобразования и один или несколько процессоров директив для преобразования текстового шаблона в выходной файл. Дополнительные сведения см. в разделе [процесс преобразования текстового шаблона](../modeling/the-text-template-transformation-process.md).  
  
 Если механизм, используемый узлом для поиска процессор директив не является безопасным, оно выполняется риск запуска вредоносных процессора директив. Вредоносный процессор директив может предоставить код, который выполняется в `FullTrust` режиме при выполнении шаблона. При создании узлом пользовательский текстовый шаблон преобразования, необходимо использовать безопасный механизм, такие как реестр, для поиска процессоры директив.


