---
title: "\"Параметры\", \"Текстовый редактор\", C/C++, \"Экспериментальный\""
ms.date: 08/02/2017
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Experimental
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Experimental
- VS.ToolsOptionsPages.Text_Editor.C\C++.Experimental
author: mikeblome
ms.author: mblome
manager: wpickett
ms.prod: visual-studio-dev15
ms.workload:
- cplusplus
ms.openlocfilehash: 13bcc65b3d8ffe4872c8b7d5f18b1bbf13bc67c5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53893332"
---
# <a name="options-text-editor-cc-experimental"></a>"Параметры", "Текстовый редактор", C/C++, "Экспериментальный"

Изменяя эти параметры, можно настроить поведение, связанное с IntelliSense и базой данных просмотра, при программировании на языке C или C++. Эти функции являются экспериментальными и могут быть удалены или изменены в будущем выпуске Visual Studio. В этом разделе описываются параметры в Visual Studio 2017. Если вы используете Visual Studio 2015, выберите **2015** в селекторе над содержанием.

Чтобы получить доступ к этой странице свойств, нажмите клавиши **CONTROL+Q** для активации `Quick Launch`, а затем введите "experimental". Функция быстрого запуска найдет страницу после ввода первых нескольких букв. Также для перехода на нее можно выбрать **Сервис | Параметры**, развернуть **Текстовый редактор**, а затем **C/C++** и выбрать **Экспериментальный**.

Эти функции доступны в установке Visual Studio 2017.

> [!NOTE]
> Отображаемые на компьютере имена или расположения некоторых элементов пользовательского интерфейса Visual Studio могут отличаться от указанных в следующих инструкциях. Это зависит от имеющегося выпуска Visual Studio и используемых параметров. См. статью [Персонализация интегрированной среды разработки Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="enable-predictive-intellisense"></a>Включение прогнозного IntelliSense

Прогнозный IntelliSense ограничивает число результатов, отображаемых в раскрывающемся списке IntelliSense, чтобы вы видели лишь результаты, релевантные в данном контексте. Например, если ввести <code>int x =</code> и вызвать раскрывающийся список IntelliSense, вы увидите только целые числа или функции, которые их возвращают. По умолчанию прогнозный IntelliSense отключен.

## <a name="enable-faster-project-load"></a>Ускорение загрузки проекта

**Visual Studio 2017 версии 15.3 и выше**. Эта функция теперь называется **Включить кэширование проектов** и перемещена на страницу свойств [Параметры проекта VC++](vcpp-project-settings-projects-and-solutions-options-dialog-box.md).
Этот параметр позволяет Visual Studio кэшировать данные проекта, чтобы при открытии проекта он мог загрузить эти данные, а не повторно вычислять их из файлов проекта. Использование кэшированных файлов может значительно ускорить время загрузки проектов.

## <a name="additional-features-in-the-visual-studio-marketplace"></a>Дополнительные функции в Visual Studio Marketplace

Список дополнительных функций текстового редактора можно найти в [Visual Studio Marketplace](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=All&sortBy=Downloads). Примером может служить расширение [C++ Quick Fixes](https://marketplace.visualstudio.com/items?itemName=VisualCppDevLabs.CQuickFixes2017), которое поддерживает перечисленные ниже возможности.

- **Добавление недостающих операторов #include** — для неизвестных символов в коде предлагаются подходящие операторы #include.

- **Добавление пространства имен using и полное определение символа** — аналогично предыдущему пункту, но относится к пространствам имен.

- **Добавление недостающих точек с запятой.**

- **Справка в Интернете** — поиск справки по сообщениям об ошибках.

- И многое другое!

## <a name="see-also"></a>См. также

- [Настройка параметров языка редактора](../../ide/reference/setting-language-specific-editor-options.md)
- [Рефакторинг в C++ (блог по VC)](https://blogs.msdn.microsoft.com/vcblog/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview/)
