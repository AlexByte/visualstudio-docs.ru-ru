---
title: Модульное тестирование кода Python
description: Настройте модульное тестирование кода Python в Visual Studio и воспользуйтесь всеми преимуществами функций обнаружения, выполнения и отладки тестов в обозревателе тестов.
ms.date: 11/12/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 5f808314639c72f530e64c4ccac08c49439c6818
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53858283"
---
# <a name="set-up-unit-testing-for-python-code"></a>Настройка модульного тестирования для кода Python

Модульные тесты — это сегменты кода, которые проверяют работу других частей кода в приложении, например изолированных функций, классов и т. д. Если приложение успешно проходит все модульные тесты, то вы по меньшей мере уверены, что все низкоуровневые функции работают правильно.

В Python модульное тестирование широко используется для проверки скриптов в процессе разработки. Поддержка Python в Visual Studio включает обнаружение, выполнение и отладку модульных тестов непосредственно в контексте процесса разработки, а значит, вам не потребуется выполнять эти тесты отдельно.

Эта статья содержит краткий обзор модульного тестирования в Visual Studio для Python. Общие сведения о модульном тестировании см. в статье о [модульном тестировании кода](../test/unit-test-your-code.md).

|   |   |
|---|---|
| ![значок кинокамеры для видео](../install/media/video-icon.png "Просмотреть видео") | [Просмотрите видео (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Testing-Python-hb46k6LWE_405918567) о модульном тестировании (2 мин 31 с). |

## <a name="discover-and-view-tests"></a>Обнаружение и просмотр тестов

По соглашению Visual Studio считает тестами все методы, имена которых начинаются с `test`. Это можно продемонстрировать на следующем примере:

1. Откройте [Проект Python](managing-python-projects-in-visual-studio.md), загруженный в Visual Studio, щелкните его правой кнопкой мыши, выберите **Добавить** > **Новый элемент**, а затем выберите **Модульный тест Python** и нажмите **Добавить**.

1. Это действие создает файл *test1.py* с кодом, который импортирует стандартный модуль `unittest`, производный от тестового класса `unittest.TestCase`, и вызывает метод `unittest.main()` при запуске скрипта напрямую:

    ```python
    import unittest

    class Test_test1(unittest.TestCase):
        def test_A(self):
            self.fail("Not implemented")

    if __name__ == '__main__':
        unittest.main()
    ```

1. Если нужно, сохраните этот файл, а затем откройте **обозреватель тестов**, последовательно выбрав **Тест** > **Окна** > **Обозреватель тестов**.

1. **Обозреватель тестов** ищет тесты в проекте и отображает результаты, как показано ниже. Дважды щелкните тест, чтобы открыть его исходный файл.

    ![Обозреватель тестов со стандартным тестом test_A](media/unit-test-A.png)

1. Когда тестов в проекте будет больше, их можно упорядочить в **обозревателе тестов**, используя команду **Группировать** на панели инструментов:

    ![Группировка на панели инструментов в меню обозревателя тестов](media/unit-test-group-menu.png)

1. Также вы можете ввести текст в поле **Поиск**, чтобы отфильтровать тесты по именам.

Дополнительные сведения о модуле `unittest` и создании тестов можно получить в [документации по Python 2.7](https://docs.python.org/2/library/unittest.html) или в [документации по Python 3.4](https://docs.python.org/3/library/unittest.html) (python.org).

## <a name="run-tests"></a>Выполнить тесты

В **обозревателе тестов** можно запустить тесты несколькими способами:

- Команда **Запустить все** явно выполняет все тесты из списка (с учетом фильтров).
- Команда меню **Запуск** позволяет одновременно выполнить все тесты, которые завершились успешно, завершились неудачно или еще не выполнялись.
- Также можно выбрать один или несколько тестов, щелкнуть их правой кнопкой мыши и выбрать команду **Запустить выбранные тесты**.

Тесты выполняются в фоновом режиме, а **обозреватель тестов** обновляет их состояние по мере завершения:

- Успешно выполненные тесты обозначаются зеленым флажком, и для них указывается затраченное время:

    ![Состояние успешного выполнения для теста test_A](media/unit-test-A-pass.png)

- Неудачные тесты обозначаются красным крестом и дополняются ссылкой **Output** (Вывод), которая позволяет изучить выходные данные на консоли и выходные данные `unittest`, полученные по результатам этого теста:

    ![Состояние неудачного выполнения для теста test_A](media/unit-test-A-fail.png)

    ![Описание причин неудачи для теста test_A](media/unit-test-A-fail-reason.png)

## <a name="debug-tests"></a>Отладка тестов

Модульные тесты являются частью кода проекта, и в них могут встречаться ошибки, как и в любом другом коде. Периодически тест следует запускать в отладчике, где можно установить точки останова, просмотреть переменные или выполнить код пошагово. Также Visual Studio предоставляет средства диагностики для модульных тестов.

Чтобы начать отладку, установите в коде начальную точку останова, а затем щелкните в **обозревателе тестов** правой кнопкой мыши этот тест (или выделенный набор тестов) и выберите **Отладить выбранные тесты**. Visual Studio запускает отладчик Python, как для обычного кода приложения.

![Отладка теста](media/unit-test-debugging.png)

Вы также можете использовать команды **Анализ покрытия кода для выбранных тестов** и **Профилировать тест**, если их поддерживает используемая версия Visual Studio (см. раздел [Матрица возможностей](overview-of-python-tools-for-visual-studio.md#features-matrix)).

### <a name="known-issues"></a>Известные проблемы

- Когда вы запускаете отладку, Visual Studio как будто бы запускает выполнение, затем останавливает и запускает снова. Это ожидаемое поведение.
- При отладке нескольких тестов они выполняются независимо друг от друга, и сеанс отладки прерывается.
- Visual Studio время от времени не удается запустить тест в режиме отладки. Обычно повторная попытка выполняется успешно.
- Во время отладки есть вероятность при выполнении шага перейти из теста в реализацию класса `unittest`. Обычно в таком случае на следующим шаге программа выполняется до конца и отладка завершается.
