---
title: Отладка управляемого кода | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e34d138ec65d2508244c6802ccee67d931e87257
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2019
ms.locfileid: "54270210"
---
# <a name="debugging-managed-code"></a>Отладка управляемого кода

В данном разделе приводится описание общих проблем отладки и способов их решения для управляемых приложений или приложений, написанных на языках, предназначенных для общеязыковой среды выполнения, например Visual Basic, C#, и C++). Описанные здесь методики — методики высшего уровня. [Первое знакомство с отладчиком](../debugger/debugger-feature-tour.md).

## <a name="in-this-section"></a>В этом разделе

[Диагностические сообщения в окне вывода](../debugger/diagnostic-messages-in-the-output-window.md)  
Описывает классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace>, с помощью которых можно записывать сообщения во время выполнения в окно **Выходные данные**. Эти классы содержат методы вывода, позволяющие выводить сведения без прерывания выполнения программы, и выводить сведения, которые также прерывают выполнение при невыполнении заданного условия.

[Утверждения в управляемом коде](../debugger/assertions-in-managed-code.md)  
Описывает утверждения в управляемом коде, которые проверяют условия, заданные в качестве аргументов методов `Assert`. Кроме того, этот раздел содержит пример кода, содержащий сведения об использовании методов классов <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace>, вопросы, касающиеся отладочной и выпускаемой версий кода, побочных эффектов, аргументов утверждений, настройки поведения утверждений и файлов конфигурации.

[Оператор Stop в Visual Basic](../debugger/stop-statements-in-visual-basic.md)  
Описывает оператор `Stop`, который представляет собой альтернативу указанию точки останова. Кроме того, раздел содержит пример кода и сравнение оператора `Stop` с оператором `End`, а также оператора `Stop` с оператором `Assert`.

[Пошаговое руководство: Отладка формы Windows Form](../debugger/walkthrough-debugging-a-windows-form.md)  
Пошаговые инструкции по созданию формы Windows Form и ее отладке. Форма Windows Forms - стандартный компонент приложения Windows, — один из наиболее распространенных вариантов управляемых приложений. В данном пошаговом руководстве используются языки Visual C# и Visual Basic, но методика создания форм Windows Forms с помощью C++ во многом аналогична.

[Отладка метода OnStart](../debugger/how-to-debug-the-onstart-method.md)  
Предоставляются примеры кода, позволяющие выполнять отладку метода `OnStart` управляемой службы Windows. Для отладки метода `OnStart` службы Windows необходимо добавить несколько строк кода для имитации работы службы.

[Mixed-Mode Debugging](../debugger/debugging-mixed-mode-applications.md)  
Обсуждение отладки приложений в смешанном режиме. Это подразумевает любое приложение, объединяющее машинный код с управляемым кодом.

[Ошибка: Отладка невозможна, так как в системе включен отладчик ядра](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)  
Описание сообщения об ошибке, которое появляется при попытке произвести отладку управляемого кода на компьютере, загруженном в режиме отладки под управлением операционной системы [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)], [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)], [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)] или Windows NT.

[JIT-отладка и оптимизация](../debugger/jit-optimization-and-debugging.md)  
Описывает эффекты по оптимизации по отладке JIT.

[Отладка LINQ и DLINQ](../debugger/debugging-linq.md)  
Описывает методы отладки LINQ запросов.

[Пошаговое руководство: Отладка параллельного приложения](../debugger/walkthrough-debugging-a-parallel-application.md)  
Описывает использование окон инструментов **Параллельные задачи** и **Параллельные стеки** для отладки параллельного приложения.

## <a name="related-sections"></a>Связанные разделы

[IntelliTrace](../debugger/intellitrace.md) поиска ошибок быстрее и проще, путем записи журнала выполнения приложения с помощью IntelliTrace. Перемещайтесь вперед или назад между различными записанными событиями и вызовами для определения состояния приложения в соответствующие моменты времени. Производите отладку приложения, не устанавливая множество точек останова и не перезапуская приложение слишком часто. Требуется Visual Studio Enterprise.

[Трассировка и инструментирование приложений](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
Описание трассировки приложений, позволяющей отследить ход выполнения приложения, и инструментирования приложений, размещающего операторы трассировки в стратегически важных местах кода. Кроме того, в данном разделе представлены ссылки на руководство по оборудованию и трассировке, а также по переключателям трассировки, слушателям трассировки, коду трассировки в приложении, добавлению оператора трассировки в код приложения и условной компиляции с использованием атрибутов <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace>.

[/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute)  
Описание параметра компоновщика, который добавляет <xref:System.Diagnostics.DebuggableAttribute> в код, написанный на языке C++. Этот атрибут необходим для использования таких возможностей отладчика, как, например, "присоединить с C++".

[Отладка служебных приложений Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)  
Рекомендации по отладке служебных приложений Windows, включая настройку, подключение к процессу, отладку кода в методе `OnStart` службы и кода в методе Main, задание точек останова и использование диспетчера управления службами для запуска, остановки, приостановки и продолжения выполнения службы пользователя.

[Отладка и профилирование](/dotnet/framework/debug-trace-profile/index)  
Описание отладки приложений .NET Framework и требований к конфигурации.

[Отладка приложений скриптов и веб-приложений](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)  
Описание общих задач и методов отладки скриптов и веб-приложений.

[Новые возможности отладчика в Visual Studio 2015](../debugger/what-s-new-for-the-debugger-in-visual-studio.md)  
Описание новых возможностей отладки, добавленных в данном выпуске [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

[Домашняя страница отладки](../debugger/debugger-feature-tour.md)  
Ссылки на крупные разделы документации об отладке. В них содержатся следующие сведения: новые возможности отладчика, сведения о параметрах и подготовке, точках останова, обработке исключений, изменении и продолжении выполнения, отладке управляемого кода, проектов Visual C++, объектов COM и ActiveX, библиотек DLL, SQL, а также ссылки на пользовательский интерфейс.

## <a name="see-also"></a>См. также

[Пошаговое руководство: Отладка пользовательских элементов управления Windows Forms во время разработки](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)  
[Безопасность отладчика](../debugger/debugger-security.md)  
[Отладка в Visual Studio](../debugger/index.md)  
[Первое знакомство с отладчиком](../debugger/debugger-feature-tour.md)