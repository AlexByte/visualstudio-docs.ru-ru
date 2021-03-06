---
title: -Build (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- builds, command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
- command-line builds
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30637a797d8c0845bae9548bb6a48e877d44727b
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2019
ms.locfileid: "54269479"
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)

Выполняет сборку решения или проекта с использованием заданного файла конфигурации решения.

## <a name="syntax"></a>Синтаксис

```shell
devenv SolutionName /Build [SolnConfigName [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>Аргументы

- *SolutionName*

  Обязательный. Полный путь и имя для файла решения.

- *SolnConfigName*

  Необязательный параметр. Имя конфигурации решения (например, `Debug` или `Release`) для использования при сборке решения, указанного в *SolutionName*. Если доступно несколько платформ решений, необходимо также указать платформу (например, `Debug|Win32`). Если этот аргумент не определен или является пустой строкой (`""`), используется действующая конфигурация решения.

- `/Project` *ProjName*

  Необязательный параметр. Путь и имя для файла проекта в решении. Можно ввести относительный путь из папки *SolutionName* к файлу проекта, отображаемое имя проекта или полный путь и имя для файла проекта.

- `/ProjectConfig` *ProjConfigName*

  Необязательный параметр. Имя конфигурации сборки проекта (например, `Debug` или `Release`) для использования при сборке указанного проекта. Если доступно несколько платформ решений, необходимо также указать платформу (например, `Debug|Win32`). Если этот параметр задан, он переопределяет аргумент *SolnConfigName*.

- `/Out` *OutputFilename*

  Необязательный параметр. Имя файла, в который вы хотите отправить выходные данные средства. Если файл уже существует, средство добавляет в его конец выходные данные.

## <a name="remarks"></a>Примечания

- Параметр `/Build` выполняет те же функции, что и команда меню **Выполнить сборку решения** в интегрированной среде разработки (IDE).

- Строки с пробелами заключаются в двойные кавычки.

- Сводные данные по сборкам, включая ошибки, могут отображаться в окне команд или в любом файле журнала, указанном с помощью параметра `/Out`.

- Параметр `/Build` выполняет сборку только тех проектов, которые изменились с момента последней сборки. Чтобы выполнить сборку всех проектов в решении, используйте [/rebuild](../../ide/reference/rebuild-devenv-exe.md).

- Если возникает сообщение об ошибке **Недопустимая конфигурация проекта**, убедитесь, что вы указали платформу решения или проекта (например, `Debug|Win32`).

## <a name="example"></a>Пример

Следующая команда выполняет сборку проекта `CSharpWinApp` с использованием конфигурации сборки проекта `Debug` в решении `MySolution`.

```shell
devenv "%USERPROFILE%\source\repos\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>См. также

- [Сборка и очистка проектов и решений](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Параметры командной строки для devenv](../../ide/reference/devenv-command-line-switches.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)