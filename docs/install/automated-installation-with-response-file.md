---
title: Автоматизация установки с помощью файла ответов
description: Сведения о создании файла ответов JSON для автоматизации установки Visual Studio
ms.date: 08/14/2017
ms.custom: seodec18
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- response file
- automate
- installation
- command-line
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4262e3d56793e1c664dc51a46403c8f9996e7bb7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53920301"
---
# <a name="how-to-define-settings-in-a-response-file"></a>Как определить параметры в файле ответов

При развертывании Visual Studio администраторы могут указать файл ответа, используя параметр `--in`, как показано в следующем примере:

```cmd
vs_enterprise.exe --in customInstall.json
```

Файлы ответов имеют формат [JSON](http://json-schema.org/) и содержат такие же значения, которые задаются аргументами командной строки.  Обычно, если параметр командной строки не принимает аргументов (например, `--quiet`, `--passive` и т. д.), в файле ответов должно содержаться значение true или false.  Если параметр принимает аргумент (например, `--installPath <dir>`), значение в файле ответов должно быть строкой.  Если параметр принимает аргумент и может встречаться в командной строке несколько раз (например, `--add <id>`), значение должно содержать массив строк.

Указанные в командной строке параметры переопределяют значения, заданные в файле ответов, за исключением тех параметров, которые принимают несколько входных значений (например, `--add`). Для таких параметров все значения, переданные в командной строке, объединяются со значениями из файла ответов.

## <a name="setting-a-default-configuration-for-visual-studio"></a>Настройка конфигурации по умолчанию для Visual Studio

Когда вы с помощью команды `--layout` создаете кэш макета сетевой установки, в этом макете создается первоначальный файл `response.json`. При создании частичного макета этот файл ответов содержит рабочие нагрузки и языки, которые были включены в макет.  Когда программа установки запускается из папки макета, она автоматически использует файл response.json, который выбирает рабочие нагрузки и компоненты, включенные в макет.  Пользователи могут по-прежнему выбирать или отменять выбор рабочих нагрузок в пользовательском интерфейсе программы установки перед установкой Visual Studio.

Администраторы, создающие макет, могут изменить файл `response.json` в макете, чтобы задать другие параметры по умолчанию, которые будут предложены пользователям при установке Visual Studio на основе макета.  Например, если администратор хочет по умолчанию устанавливать конкретные рабочие нагрузки и компоненты, он может добавить их в файл `response.json`.

Когда программа установки Visual Studio запускается из папки макета, она _автоматически_ использует файл ответов, содержащийся в этой папке.  Параметр `--in` использовать необязательно.

Вы можете изменить файл `response.json`, созданный в папке автономного макета, чтобы определить настройки по умолчанию для пользователей, выполняющих установку из этого макета.

> [!WARNING]
> Вам нужно обязательно оставить в нем все существующие свойства, которые были определены при создании макета.

Базовый файл `response.json` в макете должен выглядеть примерно так, как представлено ниже, но значения продукта и канала будут соответствовать условиям вашей установки.

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise"
}
```

При создании или обновлении макета также создается файл response.template.json.  Этот файл содержит все идентификаторы всех рабочих нагрузок, компонентов и языков, которые могут использоваться.  Этот файл предоставляется в виде шаблона для всего содержимого, которое может быть включено в настраиваемую установку.  Администраторы могут использовать этот файл в качестве отправной точки для пользовательского файла ответов.  Просто удалите идентификаторы тех компонентов, которые не нужно устанавливать, и сохраните их в собственном файле ответов.  Не настраивайте файл response.template.json файла, или изменения будут потеряны при каждом обновлении макета.

## <a name="example-layout-response-file-content"></a>Пример содержимого файла ответов в макете

В следующем примере показана установка Visual Studio Enterprise с шестью популярными рабочими нагрузками и компонентами и пользовательским интерфейсом на английском и французском языках. Вы можете использовать этот пример как шаблон, просто изменив список рабочих нагрузок и компонентов на те, которые вы хотите установить.

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise",

  "installPath": "C:\\VS2017",
  "quiet": false,
  "passive": false,
  "includeRecommended": true,
  "norestart": false,

  "addProductLang": [
    "en-US",
    "fr-FR"
    ],

    "add": [
        "Microsoft.VisualStudio.Workload.ManagedDesktop",
        "Microsoft.VisualStudio.Workload.Data",
        "Microsoft.VisualStudio.Workload.NativeDesktop",
        "Microsoft.VisualStudio.Workload.NetWeb",
        "Microsoft.VisualStudio.Workload.Office",
        "Microsoft.VisualStudio.Workload.Universal",
        "Component.GitHub.VisualStudio"
    ]
}
```

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>См. также

* [Идентификаторы рабочих нагрузок и компонентов Visual Studio 2017](workload-and-component-ids.md)
