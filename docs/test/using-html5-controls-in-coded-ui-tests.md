---
title: Использование элементов управления HTML5 в закодированных тестах пользовательского интерфейса
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: dbb34804e827ddd0eefdaf4585ba517034a31392
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2019
ms.locfileid: "54269895"
---
# <a name="using-html5-controls-in-coded-ui-tests"></a>Использование элементов управления HTML5 в закодированных тестах пользовательского интерфейса

Закодированные тесты ИП поддерживают некоторые элементы управления HTML5 в Internet Explorer 9 и Internet Explorer 10.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

 **Требования**

-   Visual Studio Enterprise

> [!WARNING]
> В версиях до Internet Explorer 10 можно было выполнять закодированные тесты пользовательского интерфейса на более высоком уровне привилегий, чем у процесса Internet Explorer. Во время выполнения закодированных тестов пользовательского интерфейса на Internet Explorer 10 эти тесты и процесс Internet Explorer должны быть на одинаковом уровне привилегий. Это вызвано более безопасными функции AppContainer в Internet Explorer 10.

> [!WARNING]
> Если закодированный тест пользовательского интерфейса создан в Internet Explorer 10, он может не работать в Internet Explorer 9 или Internet Explorer 8. Это происходит потому, что Internet Explorer 10 включает элементы управления HTML5, такие как Audio, Video, ProgressBar и Slider. Эти элементы управления HTML5 не распознаются в Internet Explorer 9 или Internet Explorer 8. Таким же образом, закодированный тест пользовательского интерфейса, созданный с помощью Internet Explorer 9, может включать некоторые элементы управления HTML5, которые не распознаются в Internet Explorer 8.

## <a name="audio-control"></a>Элемент управления звуком

**Элемент управления звуком:** действия на элементе управления звуком HTML5 правильно записываются и воспроизводятся.

![Элемент управления HTML5 Audio](../test/media/codedui_html5_audio.png)

|Действие|Запись|Созданный код|
|-|---------------|-|
|**Воспроизведение звука**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Воспроизведение аудио \<название> от 00:00:00|HtmlAudio.Play(TimeSpan)|
|**Переход к определенному моменту времени в аудио**|Переход в аудио \<название> к 00:01:48|HtmlAudio.Seek(TimeSpan)|
|**Приостановка аудио**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Приостановка аудио \<название> на 00:01:53|HtmlAudio.Pause(TimeSpan)|
|**Отключение звука**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Отключение звука аудио \<название>|HtmlAudio.Mute()|
|**Включение звука**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Включение звука аудио \<название>|HtmlAudio.Unmute()|
|**Изменение громкости звука**|Установка громкости аудио \<название> на 79 %|HtmlAudio.SetVolume(float)|

Список свойств, для которых можно добавить утверждение, см. в разделе [HTMLAudioElement](https://developer.mozilla.org/docs/Web/API/HTMLAudioElement).

 **Свойства поиска:** свойства поиска для `HtmlAudio` равны `Id`, `Name` и `Title`.

 **Свойства фильтра:** свойства фильтра для `HtmlAudio` равны `Src`, `Class`, `ControlDefinition`, и `TagInstance`.

> [!NOTE]
> Период времени для перехода и приостановки может быть значительным. Во время воспроизведения закодированный тест пользовательского интерфейса ожидает время, указанное в `(TimeSpan)` перед приостановкой аудио. Если при каких-то особых обстоятельствах указанное время истечет до обращения к команде приостановки, будет создано исключение.


## <a name="video-control"></a>Элемент управления видео
 **Элемент управления видео:** действия на элементе управления видео HTML5 правильно записываются и воспроизводятся.

 ![Элемент управления HTML5 Video](../test/media/codedui_html5_video.png)

|Действие|Запись|Созданный код|
|-|---------------|-|
|**Воспроизведение видео**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Воспроизведение видео \<название> от 00:00:00|HtmlVideo.Play(TimeSpan)|
|**Переход к определенному моменту времени в видео**|Переход в видео \<название> к 00:01:48|HtmlVideo.Seek(TimeSpan)|
|**Приостановка видео**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Приостановка видео \<название> на 00:01:53|HtmlVideo.Pause(TimeSpan)|
|**Отключение звука видео**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Отключение звука видео \<название>|HtmlVideo.Mute()|
|**Включение звука видео**<br /><br /> Непосредственно из элемента управления или в контекстном меню элемента управления.|Включение звука видео \<название>|HtmlVideo.Unmute()|
|**Изменение громкости звука видео**|Установка громкости видео \<название> на 79 %||

Список свойств, для которых можно добавить утверждение, см. в разделе [HTMLVideoElement](https://developer.mozilla.org/docs/Web/HTML/Element/video).

 **Свойства поиска:** свойства поиска для `HtmlVideo` равны `Id`, `Name` и `Title`.

 **Свойства фильтра:** свойства фильтра для `HtmlVideo` равны `Src`, `Poster`, `Class`, `ControlDefinition` и `TagInstance`.

> [!NOTE]
> Если необходимо перемотать видео вперед или назад, используя метки -30s или +30s, данные будут использоваться для перехода к соответствующему времени.

## <a name="progressbar"></a>ProgressBar
 **Элемент управления ProgressBar:** с элементом управления ProgressBar невозможно взаимодействовать. Вы можете добавить утверждения о свойствах `Value` и `Max` этого элемента управления. Дополнительные сведения см. в разделе [HTMLProgressElement](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress).

 ![Элемент управления HTML5 ProgressBar](../test/media/codedui_html5_progressbar.png)

## <a name="see-also"></a>См. также

- [Элементы HTML](https://developer.mozilla.org/docs/Web/HTML/Element)
- [Использование автоматизации пользовательского интерфейса для тестирования кода](../test/use-ui-automation-to-test-your-code.md)
- [Создание закодированных тестов пользовательского интерфейса](../test/use-ui-automation-to-test-your-code.md)
- [Поддерживаемые конфигурации и платформы для закодированных тестов пользовательского интерфейса и записей действий](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
