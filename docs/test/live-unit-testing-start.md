---
title: Сведения о том, как проверить код с помощью Live Unit Testing 2017 | Документация Майкрософт
ms.date: 08/31/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 6b96faf4ec1daa80bdd6d97e623fd0e155a39325
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53942191"
---
# <a name="get-started-with-live-unit-testing-in-visual-studio"></a>Начало работы с Live Unit Testing в Visual Studio | Документы Майкрософт

При включении функции Live Unit Testing в решении Visual Studio она визуально описывает покрытие тестов и их состояние. Она также динамически выполняет тесты при каждом изменении кода и немедленно уведомляет, если изменение вызвало сбой.

Live Unit Testing можно использовать для тестирования решений, предназначенных как для .NET Framework, так и для .NET Core. В этом учебнике вы научитесь использовать Live Unit Testing, создав простую библиотеку классов, ориентированную на .NET Standard, а также создадите проект MSTest, ориентированный на .NET Core, для тестирования.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
Полноценное решение на C# можно скачать из репозитория [MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/csharp/UtilityLibraries/) на сайте GitHub.
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
Полноценное решение на Visual Basic можно скачать из репозитория [MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/visual-basic/UtilityLibraries/) на сайте GitHub.

---

## <a name="prerequisites"></a>Предварительные требования

Для работы с учебником нужно установить Visual Studio 2017 Enterprise Edition версии 15.3 с рабочей нагрузкой .NET Core 2.0.

## <a name="create-the-solution-and-the-class-library-project"></a>Создание решения и проекта библиотеки классов

Начните с создания решения Visual Studio с именем `UtilityLibraries`, состоящего из одного проекта библиотеки классов `StringLibrary` .NET Standard. Вы можете написать `StringLibrary` на C# или Visual Basic.

Решение — это просто контейнер для одного или нескольких проектов. Чтобы создать решение, откройте Visual Studio 2017 и сделайте следующее:

1. Выберите **Файл** > **Создать** > **Проект** в меню верхнего уровня Visual Studio.

1. В диалоговом окне **Новый проект** разверните узел **Другие типы проектов** и выберите **Решения Visual Studio**. Выберите шаблон **Пустое решение** в правой области и введите `UtilityLibraries` в текстовом поле **Имя**, как показано на следующем рисунке:

   ![Диалоговое окно "Новый проект"](./media/lut-start/new-solution.png)

1. Нажмите кнопку **ОК**, чтобы создать решение.

После создания решения вы создадите библиотеку классов с именем `StringLibrary`, которая содержит несколько методов расширения для работы со строками.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. В **обозревателе решений** щелкните решение `UtilityLibraries` правой кнопкой мыши и последовательно выберите пункты **Добавить** > **Новый проект**.

1. В диалоговом окне **Добавление нового проекта** выберите узел C#, а затем **.NET Standard**.

   > [!NOTE]
   > Так как наша библиотека ориентирована скорее на платформу .NET Standard, чем на ее конкретную реализацию .NET, ее можно вызвать из любой реализации .NET, которая поддерживает эту версию .NET Standard. Дополнительные сведения см. в статье [.NET Standard](/dotnet/standard/net-standard).

1. Выберите шаблон **Библиотека классов (.NET Standard)** в правой области и введите `StringLibrary` в текстовом поле **Имя**, как показано на следующем рисунке:

   ![Диалоговое окно "Добавление нового проекта"](./media/lut-start/add-project-cs.png)

1. Нажмите кнопку **ОК**, чтобы создать проект.

1. Замените весь существующий код, отображаемый в окне кода, следующим кодом:

   [!code-csharp[StringLibrary source code](samples/csharp/utilitylibraries/stringlibrary/class1.cs)]

   `StringLibrary` имеет три статических метода.

      - `StartsWithUpper` возвращает `true`, если строка начинается с прописной буквы; в противном случае он возвращает `false`.

      - `StartsWithLower` возвращает `true`, если строка начинается со строчной буквы; в противном случае он возвращает `false`.

      - `HasEmbeddedSpaces` возвращает `true`, если строка содержит внедренный пробел; в противном случае он возвращает `false`.

1.  Выберите **Сборка** > **Сборка решения** в меню верхнего уровня Visual Studio. Система Visual Studio должна успешно создать вашу библиотеку.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. В **обозревателе решений** щелкните решение `UtilityLibraries` правой кнопкой мыши и последовательно выберите пункты **Добавить** > **Новый проект**.

1. В диалоговом окне **Добавление нового проекта** выберите узел Visual Basic, а затем **.NET Standard**.

   > [!NOTE]
   > Так как наша библиотека ориентирована скорее на платформу .NET Standard, чем на ее конкретную реализацию .NET, ее можно вызвать из любой реализации .NET, которая поддерживает эту версию .NET Standard. Дополнительные сведения см. в статье [.NET Standard](/dotnet/standard/net-standard).

1. Выберите шаблон **Библиотека классов (.NET Standard)** в правой области и введите `StringLibrary` в текстовом поле **Имя**, как показано на следующем рисунке:

   ![Диалоговое окно "Добавление нового проекта"](./media/lut-start/add-project-vb.png)

1. Нажмите кнопку **ОК**, чтобы создать проект.

1. Замените весь существующий код, отображаемый в окне кода, следующим кодом:

   [!code-vb[StringLibrary source code](samples/visual-basic/utilitylibraries/stringlibrary/class1.vb)]

   `StringLibrary` имеет три статических метода.

      - `StartsWithUpper` возвращает `true`, если строка начинается с прописной буквы; в противном случае он возвращает `false`.

      - `StartsWithLower` возвращает `true`, если строка начинается со строчной буквы; в противном случае он возвращает `false`.

      - `HasEmbeddedSpaces` возвращает `true`, если строка содержит внедренный пробел; в противном случае он возвращает `false`.

1. В **обозревателе решений** щелкните проект StringLibrary правой кнопкой мыши и выберите пункт **Свойства**. На вкладке **Приложение** удалите текст в поле **Корневое пространство имен**, как показано на следующем рисунке. Корневое пространство имен определяется [оператором Namespace](/dotnet/visual-basic/language-reference/statements/namespace-statement) в исходном коде.

   ![Диалоговое окно "Свойства проекта" для проекта Visual Basic](./media/lut-start/vb-properties.png)

1.  Выберите **Сборка** > **Сборка решения** в меню верхнего уровня Visual Studio. Система Visual Studio должна успешно создать вашу библиотеку.

---

## <a name="create-the-test-project"></a>Создание тестового проекта

Следующим шагом является создание проекта модульного теста для тестирования библиотеки `StringLibrary`. Создайте модульные тесты, выполнив следующие действия:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. В **обозревателе решений** щелкните решение `UtilityLibraries` правой кнопкой мыши и последовательно выберите пункты **Добавить** > **Новый проект**.

1. В диалоговом окне **Добавление нового проекта** выберите узел C#, а затем **.NET Core**.

   > [!NOTE]
   > Модульные тесты необязательно писать на том же языке, что и библиотеку классов.

1. Выберите шаблон **Проект модульного теста (.NET Core)** в правой области и введите `StringLibraryTests` в текстовом поле **Имя**, как показано на следующем рисунке:

   ![Диалоговое окно "Добавление нового проекта" для проекта модульного теста](./media/lut-start/add-unit-test-cs.png)

1. Нажмите кнопку **ОК**, чтобы создать проект.

   > [!NOTE]
   > Этот учебник по началу работы использует Live Unit Testing с платформой тестирования MSTest. Вы также можете использовать платформы тестирования xUnit и NUnit.

1. Проект модульного теста не может автоматически получить доступ к тестируемой библиотеке классов. Вы предоставляете доступ к библиотеке тестов, добавив ссылку на проект библиотеки классов. Для этого щелкните проект `StringLibraryTests` правой кнопкой мыши и выберите **Добавить** > **Ссылка**. В диалоговом окне **Диспетчер ссылок** убедитесь, что выбрана вкладка **Решение**, и выберите проект `StringLibrary`, как показано на приведенном ниже рисунке.

   ![Диалоговое окно "Диспетчер ссылок"](./media/lut-start/add-reference.png)

1. Замените стандартный код модульного теста, включенный в шаблон, следующим кодом:

   [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest1.cs)]

1. Сохраните проект, выбрав значок **Сохранить** на панели инструментов.

1. Так как код модульного теста включает некоторые отличные от ASCII символы, Visual Studio отображает указанное ниже диалоговое окно с предупреждением о том, что при сохранении файла в формате ASCII по умолчанию некоторые символы будут потеряны. Нажмите кнопку **Сохранить в другой кодировке**.

   ![Выберите кодировку файла](media/lut-start/ascii-encoding.png)

1. В раскрывающемся списке **Кодировка** диалогового окна **Дополнительные параметры сохранения** выберите параметр **Юникод (UTF-8, без сигнатуры), кодовая страница 65001**, как показано на следующем рисунке:

   ![Выбор кодировки UTF-8](media/lut-start/utf8-encoding.png)

1. Скомпилируйте проект модульного теста, выбрав **Сборка** > **Перестроить решение** в меню верхнего уровня Visual Studio.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)

1. В **обозревателе решений** щелкните решение `UtilityLibraries` правой кнопкой мыши и последовательно выберите пункты **Добавить** > **Новый проект**.

1. В диалоговом окне **Добавление нового проекта** выберите узел Visual Basic, а затем **.NET Core**.

   > [!NOTE]
   > Модульные тесты необязательно писать на том же языке, что и библиотеку классов.

1. Выберите шаблон **Проект модульного теста (.NET Core)** в правой области и введите `StringLibraryTests` в текстовом поле **Имя**, как показано на следующем рисунке:

   ![Диалоговое окно "Добавление нового проекта" для модульного теста](./media/lut-start/add-unit-test-vb.png)

1. Нажмите кнопку **ОК**, чтобы создать проект.

   > [!NOTE]
   > Этот учебник по началу работы использует Live Unit Testing с платформой тестирования MSTest. Вы также можете использовать платформы тестирования xUnit и NUnit.

1. Проект модульного теста не может автоматически получить доступ к тестируемой библиотеке классов. Вы предоставляете доступ к библиотеке тестов, добавив ссылку на проект библиотеки классов. Для этого щелкните проект `StringLibraryTests` правой кнопкой мыши и выберите **Добавить** > **Ссылка**. В диалоговом окне **Диспетчер ссылок** убедитесь, что выбрана вкладка **Решение**, и выберите проект `StringLibrary`, как показано на приведенном ниже рисунке.

   ![Диалоговое окно "Диспетчер ссылок"](./media/lut-start/add-reference.png)

1. Замените стандартный код модульного теста, включенный в шаблон, следующим кодом:

   [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest1.vb)]

1. Сохраните проект, выбрав значок **Сохранить** на панели инструментов.

1. Так как код модульного теста включает некоторые отличные от ASCII символы, Visual Studio отображает указанное ниже диалоговое окно с предупреждением о том, что при сохранении файла в формате ASCII по умолчанию некоторые символы будут потеряны. Нажмите кнопку **Сохранить в другой кодировке**.

   ![Выберите кодировку файла](media/lut-start/ascii-encoding.png)

1. В раскрывающемся списке **Кодировка** диалогового окна **Дополнительные параметры сохранения** выберите параметр **Юникод (UTF-8, без сигнатуры), кодовая страница 65001**, как показано на следующем рисунке:

   ![Выбор кодировки UTF-8](media/lut-start/utf8-encoding.png)

1. Скомпилируйте проект модульного теста, выбрав **Сборка** > **Перестроить решение** в меню верхнего уровня Visual Studio.

---

Вы создали библиотеку классов, а также несколько модульных тестов для нее. Вы завершили подготовку к использованию Live Unit Testing.

## <a name="enable-live-unit-testing"></a>Включение Live Unit Testing

Вы уже написали тесты для библиотеки классов `StringLibrary`, но еще не запускали их. После включения функция Live Unit Testing выполняет их автоматически. Для этого сделайте следующее:

1. При необходимости выберите окно кода, содержащее код для `StringLibrary`. Это либо *Class1.cs* для проекта C#, либо *Class1.vb* для проекта Visual Basic. (Этот шаг позволяет визуально оценить результат тестов и объем протестированного кода после включения Live Unit Testing.)

1. В меню верхнего уровня Visual Studio выберите **Тест** > **Live Unit Testing** > **Запустить**.

1. Visual Studio запускает функцию Live Unit Testing, которая автоматически выполняет все тесты.

По окончании выполнения **обозреватель тестов** отображает как общие результаты, так и результаты отдельных тестов. Кроме того, в окне кода выводится графическое представление для результатов тестов и объема протестированного кода. Как показано на следующем рисунке, все три теста прошли успешно. Кроме того, видно, что наши тесты охватили все ветви кода в методе `StartsWithUpper` и все эти тесты были выполнены успешно (на что указывает зеленая галочка "✓"). Наконец, он показывает, что ни один из других методов в `StringLibrary` не имеет объем протестированного кода (на что указывает синяя линия "➖").

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Обозреватель тестов и окно кода после запуска Live Unit Testing](media/lut-start/lut-results-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
![Обозреватель тестов и окно кода после запуска Live Unit Testing](media/lut-start/lut-results-vb.png)

---

Вы также можете получить более подробные сведения о покрытии и результатах тестов, щелкнув отдельный значок объема протестированного кода в окне кода. Чтобы изучить эту информацию, сделайте следующее:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Щелкните зеленую галочку в строке, где `if (String.IsNullOrWhiteSpace(s))` считывается в методе `StartsWithUpper`. Как показано на следующем рисунке, Live Unit Testing указывает, что эту строку кода охватили три теста и все они были выполнены успешно.

   ![Объем протестированного кода для условного оператора "if"](media/lut-start/code-coverage-cs1.png)

1. Щелкните зеленую галочку в строке, где `return Char.IsUpper(s[0])` считывается в методе `StartsWithUpper`. Как показано на следующем рисунке, Live Unit Testing указывает, что эту строку кода охватили всего два теста и все они были выполнены успешно.

   ![Объем протестированного кода для оператора return](media/lut-start/code-coverage-cs2.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Щелкните зеленую галочку в строке, где `If (String.IsNullOrWhiteSpace(s)) Then` считывается в методе `StartsWithUpper`. Как показано на следующем рисунке, Live Unit Testing указывает, что эту строку кода охватили три теста и все они были выполнены успешно.

   ![Объем протестированного кода для условного оператора "If"](media/lut-start/code-coverage-vb1.png)

1. Щелкните зеленую галочку в строке, где `Return Char.IsUpper(s(0))` считывается в методе `StartsWithUpper`. Как показано на следующем рисунке, Live Unit Testing указывает, что эту строку кода охватили всего два теста и все они были выполнены успешно.

   ![Объем протестированного кода для оператора return](media/lut-start/code-coverage-vb2.png)

---

Основной поднятый Live Unit Testing вопрос — это неполный объем протестированного кода. Ему и посвящен следующий раздел.

## <a name="expand-test-coverage"></a>Увеличение объема протестированного кода

В этом разделе вы расширите область действия модульных тестов, чтобы они захватывали метод `StartsWithLower`. При этом Live Unit Testing продолжит динамически тестировать ваш код.

Чтобы увеличить объем протестированного кода, захватив метод `StartsWithLower`, сделайте следующее:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Добавьте следующие методы `TestStartsWithLower` и `TestDoesNotStartWithLower` в файл исходного кода теста проекта:

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#1)]

1. Измените метод `DirectCallWithNullOrEmpty`, добавив следующий код сразу после вызова метода [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse).

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#2)]

1. Live Unit Testing автоматически выполняет новые и измененные тесты, когда вы изменяете исходный код. Как показано на следующем рисунке **обозревателя тестов**, все тесты, включая два добавленных и один измененный, были выполнены успешно.

   ![Обозреватель тестов после расширения объема протестированного кода.](media/lut-start/test-dynamic.png)

1. Перейдите в окно, содержащее исходный код для класса `StringLibrary`. Live Unit Testing показывает, что объем протестированного кода расширен и распространяется на метод `StartsWithLower`.

    ![Объем протестированного кода для метода StartsWithLower](media/lut-start/lut-extended-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Добавьте следующие методы `TestStartsWithLower` и `TestDoesNotStartWithLower` в файл исходного кода теста проекта:

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#1)]

1. Измените метод `DirectCallWithNullOrEmpty`, добавив следующий код сразу после вызова метода [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse).

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#2)]

1. Live Unit Testing автоматически выполняет новые и измененные тесты, когда вы изменяете исходный код. Как показано на следующем рисунке **обозревателя тестов**, все тесты, включая два добавленных и один измененный, были выполнены успешно.

   ![Обозреватель тестов после расширения объема протестированного кода.](media/lut-start/test-dynamic.png)

1. Перейдите в окно, содержащее исходный код для класса `StringLibrary`. Live Unit Testing показывает, что объем протестированного кода расширен и распространяется на метод `StartsWithLower`.

    ![Объем протестированного кода для StartsWithLower](media/lut-start/lut-extended-vb.png)

---

В некоторых случаях успешные тесты в **обозревателе тестов** могут быть выделены серым. Это означает, что тест выполняется прямо сейчас либо не запускался повторно из-за отсутствия изменений в коде, которые повлияли бы на тест, со времени последнего его выполнения.

Пока что все наши тесты прошли успешно. В следующем разделе мы рассмотрим, что делать в случае сбоя теста.

## <a name="handle-a-test-failure"></a>Обработка сбоя при тесте

В этом разделе вы узнаете, как использовать Live Unit Testing для идентификации, диагностики и устранения сбоев тестов. Для этого вы расширите объем протестированного кода, захватив метод `HasEmbeddedSpaces`.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Добавьте следующий метод в файл теста:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/unittest2.cs#3)]

1. При выполнении теста Live Unit Testing указывает, что произошел сбой метода `TestHasEmbeddedSpaces`, как показано на следующем рисунке:

   ![Обозреватель тестов сообщает о непройденном тесте.](media/lut-start/test-failure.png)

1. Выберите окно, где отображается код библиотеки. Обратите внимание, что для Live Unit Testing был расширен объем протестированного кода с захватом метода `HasEmbeddedSpaces`. Эта функция также сообщает о сбое теста, добавляя красные значки "🞩" для строк, охваченных непройденными тестами.

1. Наведите указатель мыши на строку с сигнатурой метода `HasEmbeddedSpaces`. Live Unit Testing отображает подсказку, сообщающую, что метод охвачен одним тестом, как показано на следующем рисунке:

   ![Информация Live Unit Testing о непройденном тесте.](media/lut-start/test-failure-info-cs.png)

1. Выберите непройденный тест **TestHasEmbeddedSpaces**. Обратите внимание, что Live Unit Testing предоставляет ряд параметров, таких как выполнение всех тестов, выполнение выбранных тестов, отладка всех тестов и отладка выбранных тестов, как показано на этом рисунке:

   ![Параметры Live Unit Testing для непройденного теста.](media/lut-start/test-failure-options.png)

1. Выберите **Отладить выбранные**, чтобы отладить непройденный тест.

1. Visual Studio выполняет тест в режиме отладки. Наш тест присваивает каждую строку в массиве переменной с именем `phrase` и передает ее в метод `HasEmbeddedSpaces`. Когда выражение утверждения в первый раз принимает значение `false`, выполнение программы приостанавливается и вызывается отладчик. Диалоговое окно исключения, полученное в результате непредвиденного значения в вызове метода [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue), показано на следующем рисунке.

   ![Диалоговое окно исключения для Live Unit Testing.](media/lut-start/exception-dialog-cs.png)

   Кроме того, для диагностики непройденного теста мы можем использовать все предоставляемые Visual Studio средства отладки, как показано на следующем рисунке:

   ![Средства отладки в Visual Studio.](media/lut-start/debugging-tools-cs.png)

   Обратите внимание, что в окне **Видимые** переменная `phrase` имеет значение "Name\tDescription", что соответствует второму элементу массива. Метод теста ожидает, что `HasEmbeddedSpaces` возвращает `true` при передаче данной строки; вместо этого он возвращает `false`. Очевидно, он не распознает символ табуляции "\t" как внедренный пробел.

1. Выберите **Отладка** > **Продолжить** нажмите клавишу **F5** или кнопку **Продолжить** на панели инструментов, чтобы продолжить выполнение программы тестирования. Так как возникло необработанное исключение, тест был завершен.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Добавьте следующий метод в файл теста:

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/unittest2.vb#3)]

1. При выполнении теста Live Unit Testing указывает, что произошел сбой метода `TestHasEmbeddedSpaces`, как показано на следующем рисунке:

   ![Обозреватель тестов сообщает о непройденном тесте.](media/lut-start/test-failure.png)

1. Выберите окно, где отображается код библиотеки. Обратите внимание, что для Live Unit Testing был расширен объем протестированного кода с захватом метода `HasEmbeddedSpaces`. Эта функция также сообщает о сбое теста, добавляя красные значки "🞩" для строк, охваченных непройденными тестами.

1. Наведите указатель мыши на строку с сигнатурой метода `HasEmbeddedSpaces`. Live Unit Testing отображает подсказку, сообщающую, что метод охвачен одним тестом, как показано на следующем рисунке:

   ![Информация Live Unit Testing о непройденном тесте.](media/lut-start/test-failure-info-vb.png)

1. Выберите непройденный тест **TestHasEmbeddedSpaces**. Обратите внимание, что Live Unit Testing предлагает вам ряд возможностей, включая выполнение всех тестов, выполнение выбранных тестов, отладка всех тестов и отладка выбранных тестов, как показано на этом рисунке:

   ![Параметры Live Unit Testing для непройденного теста.](media/lut-start/test-failure-options.png)

1. Выберите **Отладить выбранные**, чтобы отладить непройденный тест.

1. Visual Studio выполняет тест в режиме отладки. Наш тест присваивает каждую строку в массиве переменной с именем `phrase` и передает ее в метод `HasEmbeddedSpaces`. Когда выражение утверждения в первый раз принимает значение `false`, выполнение программы приостанавливается и вызывается отладчик. Диалоговое окно исключения, полученное в результате непредвиденного значения в вызове метода [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue), показано на следующем рисунке.

   ![Диалоговое окно исключения для Live Unit Testing.](media/lut-start/exception-dialog-vb.png)

   Кроме того, для диагностики непройденного теста мы можем использовать все предоставляемые Visual Studio средства отладки, как показано на следующем рисунке:

   ![Средства отладки в Visual Studio.](media/lut-start/debugging-tools-vb.png)

   Обратите внимание, что в окне **Видимые** переменная `phrase` имеет значение "Name" + vbTab + "tDescription", что соответствует второму элементу массива. Метод теста ожидает, что `HasEmbeddedSpaces` возвращает `true` при передаче данной строки; вместо этого он возвращает `false`. Очевидно, он не распознает символ табуляции как внедренный пробел.

1. Выберите **Отладка** > **Продолжить** нажмите клавишу **F5** или кнопку **Продолжить** на панели инструментов, чтобы продолжить выполнение программы тестирования. Так как возникло необработанное исключение, тест был завершен.

---

Это дает достаточно сведений для предварительного исследования ошибки. Либо подпрограмма тестирования `TestHasEmbeddedSpaces` сделала неверное допущение, либо `HasEmbeddedSpaces` неправильно распознает все внедренные пробелы. Чтобы выявить и устранить проблему, начните с метода `StringLibrary.HasEmbeddedSpaces`:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Посмотрите на сравнение в методе `HasEmbeddedSpaces`. В нем внедренный пробел считается равным U+0020. Однако в стандарте Юникод есть ряд других пробелов. Это дает основания полагать, что код библиотеки был неправильно протестирован на пробелы.

1. Замените сравнение на равенство вызовом метода <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName>:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/program2.cs#1)]

1. Live Unit Testing автоматически перезапускает метод непройденного теста и обновляет результаты в окне кода и **обозревателе тестов**, как показано на следующем рисунке:

    ![Успешный тест HasEmbeddedSpaces.](media/lut-start/test-success-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Посмотрите на сравнение в методе `HasEmbeddedSpaces`. В нем внедренный пробел считается равным U+0020. Однако в стандарте Юникод есть ряд других пробелов. Это дает основания полагать, что код библиотеки был неправильно протестирован на пробелы.

1. Замените сравнение на равенство вызовом метода <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName>:

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/class2.vb#1)]

1. Live Unit Testing автоматически перезапускает метод непройденного теста и обновляет результаты в окне кода и **обозревателе тестов**, как показано на следующем рисунке:

    ![Успешный тест HasEmbeddedSpaces.](media/lut-start/test-success-vb.png)

---

## <a name="see-also"></a>См. также
- [Функция Live Unit Testing в Visual Studio](live-unit-testing.md)
- [Часто задаваемые вопросы о функции Live Unit Testing](live-unit-testing-faq.md)
