---
title: Отладка машинного кода | Документация Майкрософт
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
- vs.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
caps.latest.revision: 24
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8c81efece10fe55dc1cf228a3d0c23e7f5a64af
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51730556"
---
# <a name="debugging-native-code"></a>Отладка машинного кода
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В этом разделе освещаются основные проблемы и технологии отладки для приложений, написанных в машинных кодах. В данном разделе описаны методы высшего уровня. Механизм использования отладчика Visual Studio, см. в разделе [Путеводитель по отладчику](../debugger/debugger-basics.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Отладка оптимизированного кода](../debugger/how-to-debug-optimized-code.md)  
 Советы по отладке оптимизированного кода, в особенности — почему нужно отлаживать неоптимизированную версию программы, а также стандартные параметры оптимизации для конфигураций отладки и выпуска и советы по обнаружению ошибок, появляющихся только в оптимизированном коде (включенной оптимизации в отладочной конфигурации построения).  
  
 [DebugBreak и __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 Функция Win32 `DebugBreak` и ссылки на относящиеся к ней темы в разделе "Платформа SDK". Также описывает встроенный `__debugbreak`.  
  
 [Проверочные утверждения C/C++](../debugger/c-cpp-assertions.md)  
 Операторы утверждений, принципы их работы, преимущества их использования (перехватывание логических ошибок, проверка результатов операции, выявление причин ошибок), их взаимодействие с `_DEBUG`, а также типы утверждений, поддерживаемые в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 [Практическое руководство. Отладка встроенного кода ассемблера](../debugger/how-to-debug-inline-assembly-code.md)  
 Краткие инструкции по использованию окна дизассемблирования для просмотра инструкций ассемблера и окна регистров для просмотра содержимого регистров, а также ссылки на относящиеся к этому темы.  
  
 [Методы отладки MFC](../debugger/mfc-debugging-techniques.md)  
 Предоставляет способы отладки программ MFC, к которым, в частности, относятся функция afxDebugBreak, макрос TRACE, обнаружение утечек памяти в MFC, утверждения MFC и уменьшение размера отладочных построений MFC.  
  
 [Методы отладки CRT](../debugger/crt-debugging-techniques.md)  
 Ссылки на методы отладки библиотеки времени выполнения языка C, содержащие использование библиотеки отладки CRT, макрос для отчета, различия между функциями malloc и _malloc_dbg, написание отладочных функций-ловушек, а также отладочную кучу CRT.  
  
 [Вопросы и ответы по отладке машинного кода](../debugger/debugging-native-code-faqs.md)  
 Ответы на часто задаваемые вопросы об отладке программ Visual C++.  
  
 [Отладка COM и ActiveX](../debugger/com-and-activex-debugging.md)  
 Информация по отладке приложений COM и элементов управления ActiveX, в частности, о средствах отладки.  
  
 [Практическое руководство. Отладка машинных библиотек DLL](../debugger/how-to-debug-native-dlls.md)  
 Объясняется, как настроить отладку DLL в машинных кодах.  
  
 [Практическое руководство. Отладка внедренного кода](../debugger/how-to-debug-injected-code.md)  
 Руководство по отладке кода, использующего атрибуты. Инструкции: как включить комментирование исходного кода, как просмотреть введенный код, а также как просмотреть дизассемблированный код в текущей точке выполнения.  
  
 [Пошаговое руководство. Отладка параллельного приложения](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Описывает использование **параллельных задач** и **Параллельные стеки** средство windows для отладки параллельного приложения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типы проектов Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 Ссылки на темы, описывающие отладку машинных типов проектов, созданных на основе шаблонов проектов Visual C++.  
  
 [Отладка в Visual Studio](../debugger/debugging-in-visual-studio.md)  
 Ссылки на крупные разделы документации об отладке. В этих разделах описываются: новые возможности отладчика, параметры настройки и подготовка, точки останова, обработка исключений, функция "изменить и продолжить", отладка машинного кода, отладка SQL, ссылки на интерфейс пользователя.  
  
## <a name="see-also"></a>См. также  
 [Безопасность отладчика](../debugger/debugger-security.md)   
 [Отладка в Visual Studio](../debugger/debugging-in-visual-studio.md)



