---
title: Учебник. Начало работы с консольными приложениями C#
description: Ознакомьтесь с пошаговыми инструкциями по созданию консольного приложения на C# в Visual Studio.
ms.custom: seodec18, get-started
ms.date: 01/10/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-dev15
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6114910f8c4cbeebc0301cc0c2167a49742823a5
ms.sourcegitcommit: 59c48e1e42b48ad25a4e198af670faa4d8dae370
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2019
ms.locfileid: "54204435"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>Учебник. Начало работы с консольным приложением на C# в Visual Studio

В этом руководстве по C# вы создадите и запустите консольное приложение с помощью Visual Studio, а также ознакомитесь с некоторыми возможностями [интегрированной среды разработки (IDE) Visual Studio](../visual-studio-ide.md).

Установите Visual Studio бесплатно со страницы [скачиваемых материалов Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), если еще не сделали этого.

## <a name="create-a-project"></a>Создание проекта

Для начала мы создадим проект приложения C#. Для этого типа проекта уже имеются все нужные файлы шаблонов, что избавляет вас от лишней работы.

1. Откройте Visual Studio 2017.

2. В верхней строке меню выберите **Файл** > **Создать** > **Проект**.

3. В левой области диалогового окна **Новый проект** разверните узел **C#** и выберите **.NET Core**. На средней панели выберите **Консольное приложение (.NET Core)**. Назовите файл *Calculator*.

   ![Шаблон проекта "Консольное приложение (.NET Core)" в диалоговом окне "Новый проект" в интегрированной среде разработки Visual Studio](./media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>Добавление рабочей нагрузки (необязательно)

Если шаблон проекта **Консольное приложение (.NET Core)** отсутствует, его можно получить, добавив рабочую нагрузку **Кроссплатформенная разработка .NET Core**. Чтобы узнать, как это сделать, см. сведения о [рабочих нагрузках и их добавлении](#workload) в разделе вопросов и ответов.

## <a name="create-the-app"></a>Создание приложения

Сначала мы добавим код для создания простого калькулятора. Далее мы будем изменять этот код, постепенно добавляя функциональные возможности. После этого нам предстоит отладить приложение, чтобы найти и исправить ошибки. И в завершении мы оптимизируем код для повышения эффективности.

Давайте начнем с того, что добавим в проект код простого калькулятора.

1. В редакторе кода удалите созданный по умолчанию код Hello, World!.

    ![Удаление стандартного кода Hello World из нового приложения калькулятора](./media/csharp-console-calculator-deletehelloworld.png)

   По сути, просто удалите весь код, который отображается в редакторе кода.

1. Введите или вставьте в редактор кода следующий код:

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then initialize to zero
                int num1 = 0; int num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to choose an option
                Console.WriteLine("Choose an option from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                // Use a switch statement to do the math
                switch (Console.ReadLine())
                {
                    case "a":
                        Console.WriteLine($"Your result: {num1} + {num2} = " + (num1 + num2));
                        break;
                    case "s":
                        Console.WriteLine($"Your result: {num1} - {num2} = " + (num1 - num2));
                        break;
                    case "m":
                        Console.WriteLine($"Your result: {num1} * {num2} = " + (num1 * num2));
                        break;
                    case "d":
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```
1. Выберите **Calculator**, чтобы запустить программу, или нажмите клавишу **F5**.

   ![Нажмите кнопку Calculator, чтобы запустить приложение с панели инструментов](./media/csharp-console-calculator-button.png)

   Откроется окно консоли.

1. Просмотрите приложение в окне консоли и сложите числа **42** и **119**, пользуясь предложенными подсказками.

   Теперь приложение должно выглядеть как на следующем снимке экрана:

    ![Окно консоли с приложением "Калькулятор", в котором предоставляются подсказки по выбору действий](./media/csharp-console-calculator.png)

### <a name="add-decimals"></a>Обработка десятичных чисел

Пока наше приложение принимает и возвращает только целые числа. Вычисления можно сделать точнее, добавив код для обработки десятичных чисел.

Как показано на следующем снимке экрана, при делении числа 42 на число 119 вы получите результат 0, что для нас недостаточно точно.

![Окно консоли с приложением калькулятора, которое возвращает результат без цифр после запятой](./media/csharp-console-calculator-nodecimal.png)

Давайте исправим код, чтобы он обрабатывал десятичные числа.

1. Нажмите клавиши **CTRL** + **F**, чтобы открыть элемент управления **Поиск и замена**.

1. Измените каждый экземпляр переменной `int` на `float`.

    ![Анимация элемента управления "Поиск и замена", показывающая, как изменить переменную int на float](./media/find-replace-control-animation.gif)

1. Еще раз запустите приложение калькулятора и разделите число **42** на число **119**.

   Обратите внимание, что теперь приложение возвращает не просто ноль, а десятичное число.

    ![Окно консоли с приложением калькулятора, которое возвращает результат с десятичным числом](./media/csharp-console-calculator-decimal.png)

Но пока приложение только возвращает десятичные числа. Давайте изменим код так, чтобы приложение могло выполнять операции над десятичными числами.

1. Используйте элемент управления **Поиск и замена** (**CTRL** + **F**), чтобы изменить каждый экземпляр переменной `float` на `double` и каждый экземпляр метода `Convert.ToInt32` на `Convert.ToDouble`.

1. Запустите приложение калькулятора и разделите число **42,5** на число **119,75**.

   Обратите внимание на то, что теперь приложение принимает и возвращает значения десятичные числа.

    ![Окно консоли с приложением калькулятора, которое принимает и возвращает десятичные числа](./media/csharp-console-calculator-usedecimals.png)

    (Количество десятичных разрядов мы исправим с помощью инструкций по [пересмотру кода](#revise-the-code).)

## <a name="debug-the-app"></a>Отладка приложения

Мы уже улучшили наше простое приложение "Калькулятор", но пока оно не умеет обрабатывать исключения, включая ошибки во входных данных.

Например, при попытке разделить любое число на ноль или при вводе буквенного символа там, где приложение ожидает число (или наоборот), приложение перестает работать и возвращает ошибку.

Давайте рассмотрим несколько типичных ошибок во входных данных, найдем их с помощью [отладчика](../../debugger/debugger-feature-tour.md) и исправим код, чтобы устранить их.

### <a name="fix-the-divide-by-zero-error"></a>Исправление ошибки деления на ноль

При попытке деления числа на ноль консольное приложение перестает работать. Visual Studio отображает причину проблемы в редакторе кода.

   ![Редактор кода Visual Studio с отображением ошибки деления на ноль](./media/csharp-console-calculator-dividebyzero-error.png)

Давайте изменим код, чтобы он обрабатывал такую ошибку.

1. Удалите код между `case "d":` и комментарием с текстом `// Wait for the user to respond before closing`.

1. Замените его следующим кодом.

   ```csharp
            // Ask the user to enter a non-zero divisor until they do so
                while (num2 == 0)
                {
                    Console.WriteLine("Enter a non-zero divisor: ");
                    num2 = Convert.ToInt32(Console.ReadLine());
                }
                Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                break;
        }
    ```

   Когда вы добавите новый год, раздел с оператором `switch` будет выглядеть так, как показано на следующем снимке экрана:

   ![Доработанный раздел switch в редакторе кода Visual Studio](./media/csharp-console-calculator-switch-code.png)

Теперь при делении любого числа на ноль приложение предложит ввести другое число. Даже лучше: Оно будет снова и снова повторять этот запрос, пока не получит значение, отличающееся от нуля.

   ![Редактор кода Visual Studio с отображением ошибки деления на ноль](./media/csharp-console-calculator-dividebyzero.png)

### <a name="fix-the-format-error"></a>Исправление ошибки формата

Если вы введете буквенный символ там, где приложение ожидает цифру (или наоборот), приложение консоли перестает работать. Visual Studio отображает причину проблемы в редакторе кода.

   ![Редактор кода Visual Studio с отображением ошибки формата](./media/csharp-console-calculator-format-error.png)

Чтобы устранить эту ошибку, мы выполним рефакторинг введенного ранее кода.

#### <a name="revise-the-code"></a>Пересмотр кода

Чтобы не делегировать всю обработку кода классу `program`, мы разделим приложение на два класса: `calculator` и `program`.  

Класс `calculator` выполняет основную часть работы для вычислений, а класс `program` отвечает за пользовательский интерфейс и перехват ошибок.

Итак, начнем.

1. Удалите весь код *после* этого блока кода:

    ```csharp

    using System;

    namespace Calculator
    {

    ```

1. Теперь добавьте новый класс `calculator` со следующим содержимым:

    ```csharp
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    ```

1. Затем добавьте новый класс `program` со следующим содержимым:

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
    ```
1. Выберите **Calculator**, чтобы запустить программу, или нажмите клавишу **F5**.

1. Разделите число **42** на число **119**, следуя подсказкам на экране. Теперь приложение будет выглядеть следующим образом:

    ![Окно консоли с измененным приложением калькулятора, где отображаются подсказки по выполнению действий и обработка ошибок неправильных входных данных](./media/csharp-console-calculator-refactored.png)

    Обратите внимание на то, что вы можете ввести несколько выражений, не закрывая консольное приложение. Также мы сократили количество десятичных разрядов в результате.

## <a name="close-the-app"></a>Закрытие приложения

1. Закройте приложение калькулятора, если оно еще открыто.

1. Закройте область **вывода** в Visual Studio.

   ![Закрытие области вывода в Visual Studio](./media/csharp-calculator-close-output-pane.png)

1. В Visual Studio нажмите клавиши **CTRL**+**S**, чтобы сохранить приложение.

1. Закройте Visual Studio.

## <a name="code-complete"></a>Полный код

Во этом руководстве мы внесли много изменений в приложение "Калькулятор". Теперь оно более эффективно использует вычислительные ресурсы и обрабатывает большинство ошибок во входных данных.

Ниже мы собрали в один блок весь код:

```csharp

using System;

namespace Calculator
{
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
}

```

## <a name="quick-answers-faq"></a>Быстрые ответы на часто задаваемые вопросы

Ниже приведен краткий список вопросов и ответов, с помощью которого вы сможете ознакомиться с некоторыми основными понятиями. Раздел вопросов и ответов также содержит сведения, связанные с выполнением описанных здесь процедур.

### <a name="what-is-c"></a>Что такое C#?

C# — это типобезопасный язык программирования, который работает на базе .NET Framework и .NET Core. С помощью C# можно создавать приложения для Windows, клиент-серверные приложения, приложения для работы с базами данных, веб-службы XML, распределенные компоненты и многое другое.

### <a name="what-is-visual-studio"></a>Что такое Visual Studio?

Visual Studio — это интегрированный набор средств разработки. Его можно рассматривать как программу для создания приложений.

### <a name="what-is-a-console-app"></a>Что такое консольное приложение?

Консольное приложение принимает входные данные и выводит результаты в окне командной строки, также называемом консолью.

### <a name="what-is-net-core"></a>Что такое .NET Core?

.NET Core — это дальнейший этап развития платформы .NET Framework. В то время как платформа .NET Framework позволяла использовать один и тот же код в средах разных языков программирования, в .NET Core появилась возможность использовать один и тот же код на разных платформах. Более того, это платформа с открытым кодом.

(Как .NET Framework, так и .NET Core включают в себя библиотеки готовых функций. Также в них включена общеязыковая среда выполнения (CLR), которая выполняет роль виртуальной машины для запуска кода.)

### <a id="workload"></a>Что такое рабочая нагрузка и как ее добавить?

Рабочая нагрузка в Visual Studio представляет набор параметров и шаблонов, которые можно использовать для настройки установки Visual Studio. Рабочая нагрузка устанавливает только те инструменты, которые потребуются для выбранных вами языка программирования и платформы. Ниже описано, как их установить.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Вариант 1: использование диалогового окна "Новый проект"

1. Выберите ссылку **Открыть Visual Studio Installer** в левой области диалогового окна **Новый проект**.

   ![Выбор ссылки "Открыть Visual Studio Installer" в диалоговом окне "Новый проект"](./media/csharp-open-visual-studio-installer-generic-dark.png)

1. Запускается Visual Studio Installer. Выберите рабочую нагрузку **Кроссплатформенная разработка .NET Core** и затем элемент **Изменить**.

   ![Рабочая нагрузка "Кроссплатформенная разработка .NET Core" в Visual Studio Installer](./media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Вариант 2: использование меню "Сервис"

1. Закройте диалоговое окно **Новый проект** и в верхней строке меню выберите **Сервис** > **Получить средства и компоненты**.

1. Запускается Visual Studio Installer. Выберите рабочую нагрузку **Кроссплатформенная разработка .NET Core** и затем элемент **Изменить**.

## <a name="next-steps"></a>Следующие шаги

Поздравляем с завершением этого учебника! Для получения дополнительных сведений перейдите к следующим руководствам.

> [!div class="nextstepaction"]
> [Руководства по C#](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>См. также

* Видеокурс [C# Fundamentals for Absolute Beginners](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169) (Основы программирования на C# для начинающих)