---
title: Периоды ожидания для контроллеров тестирования и агентов тестирования
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- agents, configuring
- agetns, timeouts
- controllers, configuring
- controllers, timeouts
ms.assetid: 777d0db5-0073-458a-a2a3-58b1c1f24c60
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.openlocfilehash: 49d81090a0db94fe0215d01a1194f3eb4fabfcad
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53870457"
---
# <a name="how-to-specify-timeout-periods-for-test-controllers-and-test-agents"></a>Как выполнить задание периодов ожидания для контроллеров тестирования и агентов тестирования

Для контроллеров и агентов тестирования предусмотрено несколько параметров времени ожидания, которые определяют период времени, в течение которого они должны ожидать ответа друг от друга или от источника данных, прежде чем завершить работу с ошибкой. В некоторых случаях может потребоваться изменить значения времени ожидания в соответствии с потребностями топологии или другими характеристиками среды. Для изменения значений времени ожидания необходимо изменить XML-файл конфигурации, связанный с контроллером или агентом тестирования, как описано в следующих процедурах.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Чтобы изменить различные параметры времени ожидания контроллера или агента тестирования, изменить следующие файлы конфигурации, используя имена и значения разделов, указанные в представленных ниже таблицах.

-   Контроллер тестирования: *QTController.exe.config*

    |Имя раздела|Описание|Значение|
    |-|-----------------|-|
    |AgentConnectionTimeoutInSeconds|Период времени (в секундах), в течение которого агент прослушивает запрос, прежде чем подключение считается разорванным.|"n" секунд.|
    |AgentSyncTimeoutInSeconds|Период времени (в секундах) после начала тестового запуска синхронизации, в течение которого все агенты должны ожидать синхронизации, прежде чем прервать запуск.|"n" секунд.|
    |AgentInitializeTimeout|Период времени (в секундах), в течение которого все агенты и их сборщики данных должны ожидать инициализации в начале тестового запуска, прежде чем прервать запуск. Если используются сборщики данных, данное значение должно быть достаточно большим.|"n" секунд. По умолчанию: "120" (две минуты).|
    |AgentCleanupTimeout|Период времени (в секундах), в течение которого все агенты и их сборщики данных должны ожидать очистки, прежде чем завершить тестовый запуск. Если используются сборщики данных, данное значение должно быть достаточно большим.|"n" секунд. По умолчанию: "120" (две минуты).|

-   Агент тестирования: *QTAgentService.exe.config*

    |Имя раздела|Описание|Значение|
    |-|-----------------|-|
    |ControllerConnectionPeriodInSeconds|Количество секунд между попытками подключения к контроллеру.|"n" секунд. По умолчанию: "30" (тридцать секунд).|
    |RemotingTimeoutSeconds|Максимальная продолжительность (в секундах) вызова удаленного взаимодействия.|"n" секунд. По умолчанию: "600" (десять минут).|
    |StopTestRunCallTimeoutInSeconds|Период времени (в секундах), в течение которого вызов должен ожидать остановки тестового запуска.|"n" секунд. По умолчанию: "120" (две минуты).|
    |GetCollectorDataTimeout|Период ожидания сборщика данных (в секундах).|"n" секунд. По умолчанию: "300" (пять минут).|

## <a name="to-specify-agent-timeout-options-for-a-test-controller"></a>Задание периодов ожидания агента для контроллера тестирования

1. Откройте XML-файл конфигурации *QTCcontroller.exe.config*, расположенный в папке *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

2. Найдите тег `<appSettings>`.

    ```xml
    <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentConnectionTimeoutInSeconds" value="120"/>
      <add key="AgentSyncTimeoutInSeconds" value="300"/>
      <add key="ControllerServicePort" value="6901"/>
      <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
      <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
      <add key="CreateTraceListener" value="no"/>
    </appSettings>
    ```

3. Измените существующее значение для одного из разделов периода ожидания контроллера тестирования. Например, можно изменить значение по умолчанию для раздела `AgentConnectionTimeoutInSeconds` с двух до трех минут.

    ```xml
    <add key="AgentConnectionTimeoutInSeconds" value="180"/>
    ```

    - или -

    Добавьте дополнительный раздел и укажите значение периода ожидания. Например, можно добавить раздел `AgentInitializeTimeout` в раздел `<appSettings>` и указать значение пять минут:

    ```xml
    <appSettings>
            <add key="AgentInitializeTimeout" value="300"/>
    </appSettings>
    ```

## <a name="to-specify-agent-timeout-options-for-a-test-agent"></a>Задание параметров периода ожидания агента для агента тестирования

1. Откройте XML-файл конфигурации *QTAgentService.exe.config*, расположенный в папке *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

2. Найдите тег `<appSettings>`.

    ```xml
    <appSettings>
      <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentServicePort" value="6910"/>
      <add key="ControllerConnectionPeriodInSeconds" value="30"/>
      <add key="StopTestRunCallTimeoutInSeconds" value="120"/>
      <add key="CreateTraceListener" value="no"/>
      <add key="GetCollectorDataTimeout" value="300"/>
    </appSettings>  </appSettings>
    ```

3. Измените существующее значение для одного из разделов периода ожидания агента тестирования. Например, можно изменить значение по умолчанию для раздела `ControllerConnectionPeriodInSeconds` с тридцати секунд до одной минуты.

    ```xml
    <add key="ControllerConnectionPeriodInSeconds" value="60"/>
    ```

    - или -

    Добавьте дополнительный раздел и укажите значение периода ожидания. Например, можно добавить раздел `RemotingTimeoutSeconds` в раздел `<appSettings>` и указать значение пятнадцать минут:

    ```xml
    <appSettings>
            <add key=" RemotingTimeoutSeconds " value="900"/>
    </appSettings>
    ```

## <a name="see-also"></a>См. также

- [Установка и настройка агентов тестирования](../test/lab-management/install-configure-test-agents.md)
- [Изменение параметров ведения журнала для нагрузочного теста](../test/modify-load-test-logging-settings.md)
- [Настройка портов для контроллеров и агентов тестирования](../test/configure-ports-for-test-controllers-and-test-agents.md)
- [Практическое руководство. Указание максимального размера файла журнала](../test/how-to-specify-the-maximum-size-for-the-log-file.md)
- [Практическое руководство. Привязка контроллера тестирования или агента тестирования к сетевому адаптеру](../test/how-to-bind-a-test-controller-or-test-agent-to-a-network-adapter.md)