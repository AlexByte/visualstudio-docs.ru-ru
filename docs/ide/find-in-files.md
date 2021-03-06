---
title: Поиск в файлах
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.findreplace.findinfiles
- vs.findinfiles
helpviewer_keywords:
- objects [Visual Studio], finding
- text searches, replacing text
- objects [Visual Studio], searching for
- Find and Replace window, Find in Files tab
- text searches, Find and Replace window
- documents, searching
- files, searching
- Find in Files tab, Find and Replace window
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 956af6e2ffc34a457bd3f5308b7104ef26ec1f4e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53963383"
---
# <a name="find-in-files"></a>Поиск в файлах

Функция **Поиск в файлах** позволяет выполнять поиск в указанном наборе файлов. Найденные совпадения и предпринятые действия перечисляются в окне **Результаты поиска**, выбранном в разделе **Параметры результатов**.

Для отображения функции **Поиск в файлах** в окне **Поиск и замена** можно использовать любой из указанных ниже методов.

## <a name="to-display-find-in-files"></a>Отображение функции поиска в файлах

1. В строке меню выберите **Правка** > **Найти и заменить**.

1. Выберите **Поиск в файлах**.

Чтобы отменить операцию поиска, нажмите клавиши **CTRL** + **BREAK**.

> [!NOTE]
> Средство поиска и замены не выполняет поиск в каталогах, для которых задан атрибут `Hidden` или `System`.

## <a name="find-what"></a>Найти

Чтобы найти новую текстовую строку или выражение, введите их в поле. Для поиска любой из 20 строк, которые вы искали недавно, откройте раскрывающийся список и выберите нужную строку. Нажмите расположенную рядом кнопку **Построитель выражений**, чтобы использовать в строке поиска одно или несколько регулярных выражений. Дополнительные сведения см. в статье [Использование регулярных выражений в Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

> [!NOTE]
> Кнопка **Построитель выражений** будет включена, только если вы выбрали **Использовать регулярные выражения** в области **Параметры поиска**.

## <a name="look-in"></a>Область поиска

Параметр, выбранный в раскрывающемся списке **Область поиска**, определяет, осуществляет ли функция **Поиск в файлах** поиск только в активных файлах или во всех файлах, хранимых в определенных папках. Выберите область поиска в списке или нажмите кнопку **Обзор (...)**, чтобы открыть диалоговое окно **Выбор папок поиска** и задать собственный набор каталогов. Можно также ввести путь непосредственно в поле **Область поиска**.

> [!WARNING]
> При использовании параметров **Все решение** или **Текущий проект** поиск в файлах проектов и решений не выполняется. Если вам требуется найти что-нибудь в файлах проекта, выберите папку поиска.

> [!NOTE]
> Если после выбора варианта **Область поиска** начинается поиск в файле, извлеченном из системы управления исходным кодом, поиск производится только в версии файла, скачанной на локальный компьютер.

## <a name="include-subfolders"></a>Включить вложенные папки

Указывает, что поиск будет выполняться во вложенных папках папки **Область поиска**.

## <a name="find-options"></a>Параметры поиска

Вы можете развернуть или свернуть раздел **Параметры поиска**. Можно установить или снять следующие флажки.

**С учетом регистра**

Если этот флажок установлен, функция **Результаты поиска** будет учитывать регистр.

**Слово целиком**

Если этот флажок установлен, в окне **Результаты поиска** будут отображаться только полноценные соответствия слову.

**Использование регулярных выражений**

Если этот флажок установлен, вы можете использовать специальные обозначения, чтобы определить шаблоны текста для поиска соответствия в текстовых полях **Найти** или **Заменить**. Список этих обозначений см. в статье [Использование регулярных выражений в Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

**Искать следующие типы файлов**

Этот список указывает типы файлов для поиска в каталогах **Область поиска**. Если это поле пусто, поиск будет выполняться по всем файлам в каталогах **Область поиска**.

Выберите любой элемент в списке, чтобы ввести заранее заданную строку для поиска указанных типов файлов.

## <a name="result-options"></a>Параметры результатов

Вы можете развернуть или свернуть раздел **Параметры результатов**. Можно установить или снять следующие флажки.

**Окно "Результаты поиска 1"**

Если выбран этот параметр, результаты текущего поиска заменяют содержимое окна **Результаты поиска 1**. Это окно с результатами поиска открывается автоматически. Чтобы открыть окно вручную, выберите **Другие окна** в меню **Вид** и выберите **Результаты поиска 1**.

**Окно "Результаты поиска 2"**

Если выбран этот параметр, результаты текущего поиска заменяют содержимое окна **Результаты поиска 2**. Это окно с результатами поиска открывается автоматически. Чтобы открыть окно вручную, выберите **Другие окна** в меню **Вид** и выберите **Результаты поиска 2**.

**Вывести только имена файлов**

Отображает список файлов, содержащих соответствия, а не сами совпадения.

**Добавить результаты**

Добавляет результаты поиска в результаты предыдущей операции поиска.

## <a name="see-also"></a>См. также

- [Поиск и замена текста](../ide/finding-and-replacing-text.md)
- [Заменить в файлах](../ide/replace-in-files.md)
- [Команды Visual Studio](../ide/reference/visual-studio-commands.md)