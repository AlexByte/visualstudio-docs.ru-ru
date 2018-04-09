---
title: Создание подключаемого модуля веб-теста производительности в Visual Studio | Документы Майкрософт
ms.date: 10/03/2016
ms.topic: article
f1_keywords:
- vs.test.web.webtestplugin
helpviewer_keywords:
- Web performance tests, creating plug-ins
- plug-ins, creating in Web performance tests
ms.assetid: a612f2d2-9806-477d-a126-12842f07da6e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 52f6ae448ffb9b3a416db3dfe1a89ca8932ddb62
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-web-performance-test-plug-in"></a>Практическое руководство. Создание подключаемого модуля веб-теста производительности

Подключаемые модули веб-тестов производительности позволяют изолировать и повторно использовать код вне основных декларативных операторов веб-теста производительности. Пользовательский подключаемый модуль веб-теста производительности предлагает способ для вызова того же кода при выполнении веб-теста производительности. Подключаемый модуль веб-теста производительности выполняется один раз для каждой итерации теста. Кроме того, при переопределении методов PreRequest и PostRequest в подключаемом модуле теста эти модули запросов будут выполняться до и после каждого запроса соответственно.

Пользовательские подключаемые модули веб-теста производительности можно создать с помощью пользовательского класса, производного от базового класса <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>.

Использование пользовательских подключаемых модулей веб-тестов производительности с записанными веб-тестами производительности позволяет сократить до минимума объем создаваемого пользователем кода для достижения более высокого уровня управления веб-тестами производительности. Также они используются с закодированными веб-тестами производительности. Дополнительные сведения см. в статье [Создание и выполнение закодированного веб-теста производительности](../test/generate-and-run-a-coded-web-performance-test.md).

> [!NOTE]
> Возможно также создание подключаемых модулей нагрузочных тестов. См. статью [Практическое руководство. Создание подключаемого модуля нагрузочных тестов](../test/how-to-create-a-load-test-plug-in.md).

## <a name="to-create-a-custom-web-performance-test-plug-in"></a>Создание пользовательского подключаемого модуля веб-теста производительности

1.  Откройте проект веб-тестов производительности и нагрузочных тестов, содержащий веб-тест производительности.

2.  В обозревателе решений щелкните правой кнопкой мыши решение, выберите команду **Добавить** и пункт **Новый проект**.

     Откроется диалоговое окно **Добавление нового проекта**.

3.  В области **Установленные шаблоны** выберите **Visual C#**.

4.  В списке шаблонов выберите элемент **Библиотека классов**.

5.  В текстовое поле **Имя** введите имя класса.

6.  Нажмите кнопку **ОК**.

7.  Новый проект библиотеки классов будет добавлен в обозреватель решений, а новый класс появится в редакторе кода.

8.  В обозревателе решений щелкните правой кнопкой мыши папку **Ссылки** в новой библиотеке классов и выберите команду **Добавить ссылку**.

9. Появится диалоговое окно **Добавление ссылки**.

10. Перейдите на вкладку **.NET**, прокрутите содержимое вниз и выберите пункт **Microsoft.VisualStudio.QualityTools.WebTestFramework**.

11. Нажмите кнопку **ОК**.

     Ссылка на **Microsoft.VisualStudio.QualityTools.WebTestFramework** будет добавлена в папку **Ссылки** в обозревателе решений.

12. В обозревателе решений щелкните правой кнопкой мыши верхний узел проекта веб-тестов производительности и нагрузочных тестов, в который требуется добавить подключаемый модуль веб-теста производительности, и выберите команду **Добавить ссылку**.

13. Появится диалоговое окно **Добавление ссылки**.

14. Перейдите на вкладку **Проекты** и выберите проект библиотеки классов.

15. Нажмите кнопку **ОК**.

16. Напишите код подключаемого модуля в редакторе кода. Сначала создайте открытый класс, производный от класса <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>.

17. Реализуйте код внутри одного или нескольких обработчиков событий. Образец реализации см. в приведенном ниже разделе "Пример".

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestRecordingEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PreRequestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostRequestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PrePageEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostPageEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PreTransactionEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostTransactionEventArgs>

18. После написания кода выполните построение нового проекта.

19. Откройте веб-тест производительности.

20. Чтобы добавить подключаемый модуль веб-теста производительности, выберите команду **Добавить подключаемый модуль веб-тестов** на панели инструментов.

     Откроется диалоговое окно **Добавить подключаемый модуль веб-тестов**.

21. В области **Выберите подключаемый модуль** выберите класс подключаемого модуля веб-теста производительности.

22. В области **Свойства выбранного подключаемого модуля** задайте начальные значения для подключаемого модуля, которые будут использоваться во время выполнения.

    > [!NOTE]
    > С помощью подключаемых модулей можно предоставить доступ к произвольному количеству свойств; их необходимо сделать общедоступными, задаваемыми и относящимися к базовому типу, например к целочисленному, логическому или строковому. Кроме того, свойства подключаемого модуля веб-теста производительности можно изменить позже в окне "Свойства".

23. Нажмите кнопку **ОК**.

     Подключаемый модуль будет добавлен в папку **Подключаемые модули веб-тестов**.

    > [!WARNING]
    > При запуске веб-теста производительности или нагрузочного теста, использующего данный подключаемый модуль, может появиться ошибка примерно следующего вида:
    >
    > **Сбой запроса. Исключение в событии \<подключаемый модуль>: не удалось загрузить файл или сборку "Файл \<"Имя подключаемого модуля".dll>, Version=\<n.n.n.n>, Culture=neutral, PublicKeyToken=null" или одну из зависимостей. Не удается найти указанный файл.**
    >
    > Это происходит, если в один из подключаемых модулей внесены изменения кода и создана новая версия библиотеки DLL **(Version=0.0.0.0)**, однако подключаемый модуль по-прежнему ссылается на исходную версию подключаемого модуля. Чтобы устранить эту проблему, выполните следующие действия.
    >
    > 1.  В ссылках проекта веб-тестов производительности и нагрузочных тестов появится предупреждение. Удалите и вновь добавьте ссылку на библиотеку DLL подключаемого модуля.
    > 2.  Удалите подключаемый модуль из теста или соответствующего расположения, а затем снова добавьте его.

## <a name="example"></a>Пример

В следующем коде создается пользовательский подключаемый модуль веб-теста производительности, который добавляет элемент к <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestContext>, представляющему итерацию теста.

С помощью этого подключаемого модуля после запуска веб-теста производительности можно просмотреть добавленный элемент **TestIteratnionNumber** на вкладке **Контекст** средства просмотра результатов веб-тестов производительности.

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.ComponentModel;
using Microsoft.VisualStudio.TestTools.WebTesting;

namespace SampleRules
{
    [Description("This plugin can be used to set the ParseDependentsRequests property for each request")]
    public class SampleWebTestPlugin : WebTestPlugin
    {
        private bool m_parseDependents = true;

        public override void PreWebTest(object sender, PreWebTestEventArgs e)
        {
            // TODO: Add code to execute before the test.
        }

        public override void PostWebTest(object sender, PostWebTestEventArgs e)
        {
            // TODO: Add code to execute after the test.
        }

        public override void PreRequest(object sender, PreRequestEventArgs e)
        {
            // Code to execute before each request.
            // Set the ParseDependentsRequests value on the request
            e.Request.ParseDependentRequests = m_parseDependents;
        }

        // Properties for the plugin.
        [DefaultValue(true)]
        [Description("All requests will have their ParseDependentsRequests property set to this value")]
        public bool ParseDependents
        {
            get
            {
                return m_parseDependents;
            }
            set
            {
                m_parseDependents = value;
            }
        }
    }
}
```

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>
- [Создание пользовательского кода и подключаемых модулей для нагрузочных тестов](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Практическое руководство. Создание подключаемого модуля уровня запроса](../test/how-to-create-a-request-level-plug-in.md)
- [Кодирование пользовательского правила извлечения для веб-теста производительности](../test/code-a-custom-extraction-rule-for-a-web-performance-test.md)
- [Кодирование пользовательского правила проверки для веб-теста производительности](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)
- [Практическое руководство. Создание подключаемого модуля нагрузочных тестов](../test/how-to-create-a-load-test-plug-in.md)
- [Создание и запуск закодированного веб-теста производительности](../test/generate-and-run-a-coded-web-performance-test.md)