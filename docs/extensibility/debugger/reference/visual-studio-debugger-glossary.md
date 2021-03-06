---
title: Глоссарий отладчика Visual Studio | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- glossary [Debugging SDK]
- debugging [Debugging SDK], glossary
ms.assetid: 4a2cfaab-1fbd-4a23-bd00-9ac4cc50d7fd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 98607365ef063653cd0721281a194e6c515780f0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918957"
---
# <a name="visual-studio-debugger-glossary"></a>Глоссарий отладчика Visual Studio
Ниже перечислены термины, используемые в [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] отладки пакета SDK.  
  
## <a name="terms"></a>Термины  
 связанная точка останова  
 Абстракция для точки останова, заданной в коде. Имеется однозначное соответствие между связанная точка останова и инструкции точки останова в потоке кода. Если код выгрузки, связанных точек останова может отменить привязку.  
  
 причинно-следственных связей  
 Предоставляет возможность отслеживать логический поток выполнения в нескольких физических потоков, процессов и машины, а также для реконструкции стека вызовов данного логического потока в любой момент во времени существования данного потока.  
  
 контекст кода  
 Предоставляет абстракцию для положения в коде, известные для обработчика отладки. Для большинства архитектур во время выполнения контекст кода — это адрес в потоке инструкций программы. Контекст кода для нетрадиционных языков, в которых код не представлены инструкции, можно представить с помощью других средств.  
  
 путь к коду  
 Представляет точку выполнения в коде, где будет выбрана ветвь или выполняется вызов функции. Трассировку стека представляет собой список путей кода вызов функции.  
  
 модуль отладки (DE)  
 Компонент, который позволяет выполнить отладку архитектуры среды выполнения. Модуль отладки работает совместно с интерпретатором или операционной системы и предоставляет службы отладки, такие как выполнение элемента управления, точки останова и оценки выражений.  
  
 контекст документа  
 Предоставляет краткое описание позиции в документе исходного файла, известно, модуль отладки. Для большинства языков контекст документа — позиция в исходном файле. Для нетрадиционных языков, для которых исходный файл не может быть текст, к контексту документа могут быть представлены либо иным образом. См. также *позиция документа*.  
  
 Позиция в документе  
 Предоставляет абстракцию для положения в файле исходного кода, известные в интегрированную среду разработки. Для большинства языков позиции документа — положение в исходном файле. Для нетрадиционных языков позиции документа может быть представлен по-другому. См. также *контекст документа*.  
  
 Ошибка точки останова  
 Абстракция для описания ошибки в точку останова. Ошибка точки останова могут описывать ошибку в расположении, ожидающая точка останова, выражение, связанное с ожидающая точка останова, или другие сведения, который предотвращает привязки ожидающая точка останова расположение кода.  
  
 Контекст оценки  
 Предоставляет краткое описание контекст программирования для оценки выражения. Как правило контекст вычисления является областью. При выполнении вычисления выражения в контексте выражения, выражения контекст предоставляет правила области видимости, которые соответствуют его точки создания. Например контексте выражения, созданные в кадре стека будет обеспечить контекст для оценки локальных переменных, параметров методов, члены класса (если применимо) и глобальные переменные.  
  
 перехваченные исключения  
 Исключение, перехватывается модуля отладки, даже если механизм обработки исключений, не находится в месте текущего кадра стека.  
  
 JustMyCode  
 Концепция Отладка только кода, к которой принадлежит пользователь и пропуск всех промежуточный код, например системного кода, даже если исходный код доступен для этого кода системы.  
  
 ожидающая точка останова  
 Предоставляет абстракцию для точки останова до, во время и после кода, загружен и способ виртуализировать точки останова. В ожидании точки останова:  
  
- Содержит все сведения, необходимые для привязки точку останова для кода в одну или несколько программ.  
  
- Выполнить привязку в нескольких местах кода, в одну или несколько программ.  
  
- Никогда не привязывает самого кода.  
  
  Загружает каждый код времени, всех ожидающих точек останова в программе проверяются на предмет того, можно привязать. Ожидающая точка останова говорят, что для хранения всех связанных точек останова, которые он выполняет привязку.  
  
  процесс  
  Физический процесс Win32. Процесс может содержать несколько программ. См. также *программы*.  
  
  программа  
  Одно пространство имен, выполняемых в рамках конкретной архитектуры среды выполнения. См. также *процесс*.  
  
  диспетчер отладки сеансов (SDM)  
  Управляет любое количество обработчиков отладки, отладки любое количество программ в нескольких процессах на любое число компьютеров. На базовом уровне SDM является мультиплексора подсистемы отладки. Кроме того SDM предоставляет единое представление сеанса отладки в интегрированную среду разработки.  
  
  кадр стека  
  Представляет состояние процесса вычисления на определенный кадр и определенного уровня вложенных вызовов функций.  
  
  thread  
  Обобщенный понятие выполнения команд на основе стека, под управлением по крайней мере одной программы.  
  
  Предупреждение точки останова  
  Абстракция для описания предупреждения в точку останова. Предупреждение точки останова описаны причины, почему ожидающая точка останова не еще выполнило расположение кода. Это может быть, что код не загружен еще для расположения, описываемого ожидающая точка останова или по другой причине.  
  
## <a name="see-also"></a>См. также  
 [Расширяемость отладчика Visual Studio](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)