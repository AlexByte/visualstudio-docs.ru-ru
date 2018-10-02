---
title: Изменения в синхронизации между XCode и Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c71a4d7c-120e-4559-a114-3a99c4b860a9
caps.latest.revision: 10
author: BrianPeek
ms.author: brpeek
manager: ghogen
ms.openlocfilehash: a18d21dc20d6bb8a8346013130bea15f094b5fff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47571287"
---
# <a name="sync-changes-between-xcode-and-visual-studio"></a>Изменения в синхронизации между XCode и Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [синхронизация изменений между XCode и Visual Studio](https://docs.microsoft.com/visualstudio/cross-platform/sync-changes-between-xcode-and-visual-studio).  
  
  
Компонент Microsoft Visual C++ для разработки мобильных приложений включает в себя функции удаленного взаимодействия для синхронизации работы между ПК и Mac. Когда компьютеры с Visual Studio и Mac связаны, для проектов приложений iOS в Visual Studio доступны новые возможности, позволяющие открыть проект в XCode, перемещать код между XCode и Visual Studio и очистить временный каталог проекта XCode.  
  
 Для использования возможностей удаленного компьютера проект должен быть проектом приложения iOS, а система Visual Studio должна быть связана с Mac. Необходимые условия и инструкции по связыванию Mac см. в разделе [Установка и настройка средств для разработки с помощью iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md).  
  
## <a name="the-remote-machine-menu"></a>Меню "Удаленный компьютер"  
 В **обозревателе решений** щелкните проект приложения iOS правой кнопкой мыши для отображения контекстного меню. Выберите пункт **Удаленный компьютер**, чтобы показать доступные параметры удаленного взаимодействия.  
  
 ![Пункт меню "Удаленный компьютер" в обозревателе решений](../cross-platform/media/cppmdd-u2-remotemachine-menu.jpg "CPPMDD_U2_RemoteMachine_Menu")  
  
 Эти команды позволяют открыть проект в XCode, перемещать локальные изменения или весь проект между Visual Studio и XCode, а также очистить временные файлы на удаленном компьютере.  
  
### <a name="open-in-xcode"></a>Открыть в XCode  
 Чтобы открыть проект из Visual Studio в XCode, в подменю **Удаленный компьютер** выберите **Открыть в XCode** для открытия выбранного проекта на связанном удаленном компьютере. Сервер vcremote используется для открытия XCode на компьютере Mac и перехода во временную папку с копией проекта. Visual Studio выводит диалоговое окно с временным каталогом для проекта. Действия, выполняемые на удаленном компьютере, также отображаются в окне **Вывод** Visual Studio. Чтобы увидеть их, может потребоваться выбрать элемент **Удаленный компьютер Visual C++** в раскрывающемся списке **Показать выходные данные из** в верхней части окна **Вывод**.  
  
 ![В окне вывода отображаются действия на удаленном компьютере.](../cross-platform/media/cppmdd-u2-remotemachine-output.png "CPPMDD_U2_RemoteMachine_Output")  
  
 На Mac можно использовать любые средства XCode для изменения кода, а также ресурсов, раскадровки и действий. В Visual Studio проект приложения iOS помечается как "Открыто в XCode", чтобы указать, что на удаленном компьютере могут вноситься изменения. После внесения изменений вы можете воспользоваться командой "Принудительное извлечение с удаленного компьютера" или "Инкрементное принудительное извлечение с удаленного компьютера", чтобы скопировать их обратно в проект Visual Studio.  
  
### <a name="push-to-remote-and-incremental-push-to-remote"></a>"Принудительная отправка на удаленный компьютер" и "Инкрементная принудительная отправка на удаленный компьютер"  
 После внесения изменений в проект приложения iOS в Visual Studio, можно воспользоваться командой "Принудительная отправка на удаленный компьютер" или "Инкрементная принудительная отправка на удаленный компьютер" для перемещения измененных файлов проекта на связанный удаленный компьютер. Команда "Принудительная отправка на удаленный компьютер" копирует все файлы проекта на удаленный компьютер. Команда "Инкрементная принудительная отправка на удаленный компьютер" копирует на удаленный компьютер только измененные файлы. Для крупных проектов с небольшими изменениями инкрементная команда позволят сэкономить время и пропускную способность.  
  
 Чтобы скопировать файлы проекта на Mac, в окне **обозревателя решений** Visual Studio щелкните проект приложения iOS правой кнопкой мыши для открытия контекстного меню. Выберите пункт **Удаленный компьютер** и затем команду **Принудительная отправка на удаленный компьютер** или **Инкрементная принудительная отправка на удаленный компьютер**, чтобы скопировать файлы проекта из Visual Studio на Mac.  
  
### <a name="pull-from-remote-and-incremental-pull-from-remote"></a>"Принудительное извлечение с удаленного компьютера" и "Инкрементное принудительное извлечение с удаленного компьютера"  
 После внесения изменения в проект в XCode переместите изменения обратно Visual Studio, чтобы обеспечить синхронизацию проектов.  
  
 Чтобы скопировать файлы проекта с Mac, в окне **обозревателя решений** Visual Studio щелкните проект приложения iOS правой кнопкой мыши для открытия контекстного меню. Выберите пункт **Удаленный компьютер** и затем команду **Принудительное извлечение с удаленного компьютера** или **Инкрементное принудительное извлечение с удаленного компьютера**, чтобы скопировать файлы проекта с Mac в Visual Studio.  
  
### <a name="clean-remote"></a>Очистить удаленный компьютер  
 Вы можете использовать команду "Очистить удаленный компьютер" для удаления файлов во временном каталоге проекта на удаленном компьютере. Содержимое этого каталога, включая все исходные файлы или результаты сборки, удаляется с Mac. Перед применением команды "Очистить удаленный компьютер" синхронизируйте все изменения, которые должны присутствовать в Visual Studio, с помощью команды "Принудительное извлечение с удаленного компьютера" или "Инкрементное принудительное извлечение с удаленного компьютера".  
  
 Чтобы очистить временный каталог проекта на удаленном компьютере, в окне **обозревателя решений** Visual Studio щелкните проект приложения iOS правой кнопкой мыши для открытия контекстного меню. Выберите пункт **Удаленный компьютер** и команду **Очистить удаленный компьютер**, чтобы удалить файлы в каталоге проекта с Mac.
