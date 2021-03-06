---
title: 'Практическое: проверка параметров свойства IIS | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- IIS, property settings
- debugging Web applications, troubleshooting
- IIS administration tool
- Web applications, setting properties
- properties [debugger], setting with IIS administration tool
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4639055fe9320c8fd1bf1b2575bca323642dd17f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51742076"
---
# <a name="how-to-verify-iis-property-settings"></a>Практическое руководство. Проверка параметров свойства IIS
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Можно задать свойства для веб-приложения с помощью средства администрирования IIS. Чтобы приложение выполнялось, эти свойства должны быть заданы правильно. Поэтому проверка этих параметров часто является необходимым шагом в устранении неполадок.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-check-iis-settings-for-the-web-application"></a>Проверка параметров IIS для веб-приложения  
  
1.  Откройте **Администрирование** окно: на **запустить** последовательно выберите пункты **программы**и нажмите кнопку **Администрирование**. Если **Администрирование** не отображается в **программы** меню, а затем искать его в **панели управления**.  
  
    -   В Windows 2000, выберите **Диспетчер служб Интернета**.  
  
    -   В Windows XP, выберите **Internet Information Services**.  
  
    -   В Windows Server 2003, дважды щелкните **Управление данным сервером**.  
  
         **Управление данным сервером** откроется окно. В разделе **сервера приложений**, нажмите кнопку **управление этим сервером приложения**.  
  
         **Сервера приложений** откроется окно. Откройте **Internet Information Services (IIS) Manager** узел в области слева.  
  
2.  В диалоговом окне выберите дерево элемента управления узлами для своего компьютера. Нажмите кнопку **веб-сайтов** узел и выберите узел веб-приложения. Это может быть веб-узел и таким образом, элементом одного уровня **Default Web Site** узла или виртуального каталога узла под существующим узлом веб-сайта.  
  
3.  Щелкните правой кнопкой мыши веб-приложения и в контекстном меню, щелкните **свойства**.  
  
4.  Проверьте параметры безопасности для веб-приложения:  
  
    1.  В веб-приложении **свойства** окно, нажмите кнопку **Безопасность каталога** , а щелкните **изменить**.  
  
    2.  В **методы проверки подлинности** выберите **включить анонимный доступ** и **Windows интегрированной проверки подлинности** если они еще не выбран.  
  
    3.  Нажмите кнопку **ОК** закрыть **методы проверки подлинности** диалоговое окно.  
  
5.  Для приложения сервера ATL необходимо проверить, связана ли команда DEBUG с расширением ISAPI. Дополнительные сведения см. в разделе [как: связать команда DEBUG с расширением](http://msdn.microsoft.com/en-us/50d261d3-4bd4-41c0-b44e-3591086f121e).  
  
6.  Для [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] приложения, убедитесь, что виртуальная папка для приложения имеет имя приложения в **Internet Information Services (IIS) Manager**, **Диспетчер служб Интернета** или  **Internet Information Services**.  
  
    1.  В веб-приложении **свойства** выберите **Directory** вкладку, если приложение находится в виртуальном каталоге, или **домашний каталог** вкладку, если приложение находится в веб-сайта.  
  
    2.  Убедитесь, что имя в **локальный путь** совпадает с именем каталога, где приложение было развернуто.  
  
    3.  В разделе **параметры приложения**, введите имя корневого каталога, содержащего приложение.  
  
    4.  Нажмите кнопку **ОК** закрыть **свойства** диалоговое окно.  
  
7.  Для [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] приложения, нажмите кнопку **ASP.NET** и убедитесь, что правильная версия [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] указан.  
  
8.  Нажмите кнопку **ОК** закрыть **свойства** диалоговое окно.  
  
9. Нажмите кнопку **ОК** закрыть **Internet Information Services (IIS) Manager**, **Диспетчер служб Интернета**, или **Internet Information Services**диалоговое окно.  
  
## <a name="see-also"></a>См. также  
 [Устранение неполадок](../debugger/debugging-web-applications-troubleshooting.md)



