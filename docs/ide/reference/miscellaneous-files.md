---
title: Прочие файлы
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- VS.newfile
- VS.OpenWith
- MiscellaneousFilesProject
helpviewer_keywords:
- solutions, miscellaneous files
- builds [Visual Studio], miscellaneous files
- standalone files
- Solution Explorer, miscellaneous files
- Miscellaneous Files folder
- files [Visual Studio], outside of containers
- files [Visual Studio], Miscellaneous Files folder
ms.assetid: 5b96640b-8efe-48a4-8d0a-1ae3f9587e44
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d764cea7992a9833bd8bddde8432388aebbc994
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867164"
---
# <a name="miscellaneous-files"></a>Прочие файлы
Редакторы [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] можно использовать для работы с отдельными файлами из проекта или решения. Если решение открыто, файлы можно открывать и изменять, не добавляя их к решению или проекту. Файлы, работать с которыми необходимо независимо от контейнеров, называются прочими файлами. Прочие файлы являются внешними по отношению к решениям и проектам; они не включаются в сборки и не могут быть включены в решение, размещенное в системе управления версиями.

 Открытие файлов независимо от контейнера может понадобиться по разным причинам. Может возникнуть необходимость просмотреть файл в процессе разработки решения с проектами, однако файл не будет являться частью этого процесса. Типичными примерами таких файлов являются замечания о разработке или инструкции, схема базы данных и фрагменты кода. Кроме того, может понадобиться создать автономный файл.

 ![Решения проектов](../../ide/reference/media/projects_solutions_misc.gif)

 В обозревателе решений папка "Прочие файлы" отображается в случае, если для папки включены необходимые параметры. Эти параметры можно задать в диалоговом окне [Документы > Среда > Параметры](../../ide/reference/documents-environment-options-dialog-box.md). После закрытия прочего файла он не связывается с решением или проектом, если не установлен специальный параметр.

 В папке "Прочие файлы" файлы представлены в виде ссылок. Хотя эта папка не является частью решения, при открытии решения некоторые или все прочие файлы, которые были открыты при последнем закрытии решения, открываются, если папка настроена соответствующим образом.

> [!NOTE]
> Некоторые файлы, не отображающиеся в папке "Прочие файлы", являются файлами, которые нельзя изменять в интегрированной среде разработки, например ZIP-файлы и DOC-файлы. Интегрированная среда разработки не будет отслеживать файлы, которые можно изменять только с помощью внешнего редактора.


## <a name="commands-available-in-the-ide"></a>Команды, доступные в интегрированной среде разработки
 Меню, панели инструментов и содержащиеся в них команды изменяются на основе формата открываемого файла. Например, при открытии текстового файла отображается панель инструментов для текстового редактора, и ее команды становятся доступными. Если затем открыть файл схемы XML, отображается панель инструментов для схемы XML. В процессе редактирования схемы XML команды на панели инструментов текстового редактора (или сама панель) становятся недоступными. Схема XML является активным окном и содержит выделенный фрагмент. При переходе от файла проекта к прочему файлу все команды, связанные с проектом, отключаются, и отображаются только те команды, которые непосредственно связаны с прочим файлом.

## <a name="folder-display-options"></a>Параметры отображения папки
 Для папки "Прочее" можно задать параметры отображения таким образом, чтобы она отображалась даже в том случае, если прочие файлы не открыты. Файл решения не контролирует список прочих файлов постоянно. Он использует дополнительную функцию, которая позволяет ему запоминать список последних использованных файлов для каждого пользователя.

## <a name="see-also"></a>См. также раздел

- [Решения и проекты](../../ide/solutions-and-projects-in-visual-studio.md)
- [Страница "Документы", папка "Среда", диалоговое окно "Параметры"](../../ide/reference/documents-environment-options-dialog-box.md)