---
title: Как выполнить Автоматическое применение ключей продуктов при развертывании Visual Studio 2015 | Документация Майкрософт
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
caps.latest.revision: 11
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 1dd9127895a375ae02e6d4f18bae0a09bef494bb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53942048"
---
# <a name="how-to-automatically-apply-product-keys-when-deploying-visual-studio"></a>Как выполнить Автоматическое применение ключей продуктов при развертывании Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последние версии документации Visual Studio 2017, см. в разделе [автоматическое применение ключей продуктов при развертывании Visual Studio](/visualstudio/install/automatically-apply-product-keys-when-deploying-visual-studio).

Ключ продукта можно применить программным способом в составе сценария автоматизации развертывания Visual Studio 2015. Ключи продуктов могут быть заданы на устройстве программно во время установки Visual Studio или после завершения установки.

## <a name="apply-the-license-during-installation"></a>Применение лицензии во время установки
 Для применения ключа продукта во время установки Visual Studio следует использовать параметр/ProductKey. Этот параметр установки можно использовать вместе с параметром /Silent для установки версии Visual Studio, уже лицензированной для конечного пользователя. Чтобы использовать параметр /ProductKey, откройте командную строку. Запустите программу установки (например, vs_enterprise.exe или vs_professional.exe) и задайте для параметра/ProductKey значение ключа продукта (25 символов) без дефисов:

 Это пример команды для установки Visual Studio 2015 Enterprise с ключом продукта AAAAABBBBBCCCCCDDDDDEEEEEEE:

 `vs_enterprise.exe [any other setup parameters] /ProductKey AAAAABBBBBCCCCCDDDDDDEEEEEE`

## <a name="apply-the-license-after-installation"></a>Применение лицензии после установки
 Активировать установленную версию Visual Studio с помощью ключа продукта можно путем запуска служебной программы storePID.exe на конечных компьютерах в автоматическом режиме. StorePID.exe —это служебная программа, которая устанавливается вместе с Visual Studio по адресу **\<диск>:\\\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe**.

 Запустите storePID.exe с повышенными привилегиями либо с помощью агента System Center, либо из командной строки с повышенными привилегиями, указав ключ продукта (включая дефисы) и код продукта Майкрософт (MPC). В ключе продукта необходимо указывать дефисы!

 `StorePID.exe [product key including the dashes] [MPC]`

 Это пример команды для установки Visual Studio 2015 Enterprise с кодом MPC 07060 и ключом продукта «AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE»:

 `C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 07060`

 В следующей таблице перечислены коды MPC для каждого выпуска Visual Studio:

|Visual Studio 2013|MPC|
|---------------------------|---------|
|Visual Studio Enterprise|07060|
|Visual Studio Professional 2015|07062|
|Visual Studio Test Professional 2015|07066|
|Visual Studio Ultimate 2013|06181|
|Visual Studio Premium 2013|06191|
|Visual Studio Professional 2013|06177|
|Visual Studio Test Professional 2013|06194|

 Дополнительные сведения о получении ключа продукта, см. в разделе [как: Поиск ключа продукта Visual Studio](../install/how-to-locate-the-visual-studio-product-key.md).

 Если StorePID.exe успешно применены ключ продукта, возвращается 0. В случае возникновения ошибки возвращается число в диапазоне от 1 до 6.

## <a name="see-also"></a>См. также раздел
 [Установка Visual Studio](../install/install-visual-studio-2015.md)