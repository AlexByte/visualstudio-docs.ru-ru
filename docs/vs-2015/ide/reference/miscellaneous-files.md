---
title: Прочие файлы | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cb9c7fb46517ff2d6dffdeb0cedfc4982c1f3366
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49258491"
---
# <a name="miscellaneous-files"></a>Прочие файлы
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Редакторы [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] можно использовать для работы с отдельными файлами из проекта или решения. Если решение открыто, файлы можно открывать и изменять, не добавляя их к решению или проекту. Файлы, работать с которыми необходимо независимо от контейнеров, называются прочими файлами. Прочие файлы являются внешними по отношению к решениям и проектам; они не включаются в сборки и не могут быть включены в решение, размещенное в системе управления версиями.  
  
 Открытие файлов независимо от контейнера может понадобиться по разным причинам. Может возникнуть необходимость просмотреть файл в процессе разработки решения с проектами, однако файл не будет являться частью этого процесса. Типичными примерами таких файлов являются замечания о разработке или инструкции, схема базы данных и фрагменты кода. Кроме того, может понадобиться создать автономный файл.  
  
 ![Проекты решений](../../ide/reference/media/projects-solutions-misc.gif "Projects_Solutions_Misc")  
  
 В обозревателе решений папка "Прочие файлы" отображается в случае, если для папки включены необходимые параметры. Эти параметры можно задать в диалоговом окне [Документы > Среда > Параметры](../../ide/reference/documents-environment-options-dialog-box.md). После закрытия прочего файла он не связывается с решением или проектом, если не установлен специальный параметр.  
  
 В папке "Прочие файлы" файлы представлены в виде ссылок. Хотя эта папка не является частью решения, при открытии решения некоторые или все прочие файлы, которые были открыты при последнем закрытии решения, открываются, если папка настроена соответствующим образом.  
  
> [!NOTE]
>  Некоторые файлы, не отображающиеся в папке "Прочие файлы", являются файлами, которые нельзя изменять в интегрированной среде разработки, например ZIP-файлы и DOC-файлы. Интегрированная среда разработки не будет отслеживать файлы, которые можно изменять только с помощью внешнего редактора.  
  
## <a name="commands-available-in-the-ide"></a>Команды, доступные в интегрированной среде разработки  
 Меню, панели инструментов и содержащиеся в них команды изменяются на основе формата открываемого файла. Например, при открытии текстового файла отображается панель инструментов для текстового редактора, и ее команды становятся доступными. Если затем открыть файл схемы XML, отображается панель инструментов для схемы XML. В процессе редактирования схемы XML команды на панели инструментов текстового редактора (или сама панель) становятся недоступными. Схема XML является активным окном и содержит выделенный фрагмент. При переходе от файла проекта к прочему файлу все команды, связанные с проектом, отключаются, и отображаются только те команды, которые непосредственно связаны с прочим файлом.  
  
## <a name="folder-display-options"></a>Параметры отображения папки  
 Для папки "Прочее" можно задать параметры отображения таким образом, чтобы она отображалась даже в том случае, если прочие файлы не открыты. Файл решения не контролирует список прочих файлов постоянно. Он использует дополнительную функцию, которая позволяет ему запоминать список последних использованных файлов для каждого пользователя.  
  
## <a name="see-also"></a>См. также  
 [Решения и проекты](../../ide/solutions-and-projects-in-visual-studio.md)   
 [Страница "Документы", папка "Среда", диалоговое окно "Параметры"](../../ide/reference/documents-environment-options-dialog-box.md)



