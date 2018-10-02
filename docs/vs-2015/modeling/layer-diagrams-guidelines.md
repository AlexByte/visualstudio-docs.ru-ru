---
title: 'Схемы слоев: Рекомендации | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, layer diagrams
- layer diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: 2903bec7-a93b-46a6-aac6-994ac4f3f1a7
caps.latest.revision: 57
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: bd0115021ba00d8e727f67260f5bcdb00464dd2b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47558671"
---
# <a name="layer-diagrams-guidelines"></a>Схемы слоев: рекомендации
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [схемы зависимостей: рекомендации по](https://docs.microsoft.com/visualstudio/modeling/layer-diagrams-guidelines).  
  
Описание архитектуры приложения на высоком уровне путем создания *схемы слоев* в Visual Studio. Чтобы убедиться в том, что код соответствует этой структуре, проверьте его с помощью схемы слоев. В процесс сборки также можно включить проверку слоев. См. в разделе [видео Channel 9: проектирования и проверки архитектуры с использованием схем слоев](http://go.microsoft.com/fwlink/?LinkID=252073).  
  
 Чтобы узнать, какие версии Visual Studio поддерживают эту функцию, см. раздел [Поддержка версий для инструментов моделирования и архитектуры](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="what-is-a-layer-diagram"></a>Что такое схема слоев?  
 Как и в традиционной схеме архитектуры, схема слоев определяет основные компоненты или функциональные единицы разработки, а также их взаимозависимости. Каждый узел на схеме называется *слой*, представляет собой логическую группу пространств имен, проекты или другие артефакты. Можно нарисовать зависимости для своей разработки. В отличие от традиционной схемы архитектуры, можно проверить, соответствуют ли действительные зависимости заданным вами предполагаемым зависимостям. Делая проверку частью стандартного построения в [!INCLUDE[esprtfs](../includes/esprtfs-md.md)], можно добиться того, чтобы программный код продолжал придерживаться архитектуры системы при дальнейших изменениях. См. в разделе [схемы слоев: ссылка](../modeling/layer-diagrams-reference.md).  
  
##  <a name="Update"></a> Разработка или обновление приложения с помощью схем слоев  
 Следующие шаги показывают как использовать схемы слоев при разработке. Каждый шаг более подробно описан в последующих подразделах данного раздела. Если ведется разработка нового проекта, можно пропустить шаги, которые относятся к существующему коду.  
  
> [!NOTE]
>  Эти шаги приведены в примерном порядке. Возможно, понадобится перекрыть задачи, заново упорядочить их, чтобы они подходили по ситуации, а также возвратиться к ним в начале каждой итерации в проекте.  
  
1.  [Создайте схему слоев](#Create) для всего приложения или для слоя внутри него.  
  
2.  [Определите слои для представления первичных функциональных областей или компонентов](#CreateLayers) приложения. Дайте этим слоям имена согласно их функциям, например "Презентация" или "Службы". Если у вас есть [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] решение, можно связать каждый слой с коллекцией *артефакты*, таких как проекты, пространства имен, файлы и т. д.  
  
3.  [Обнаружение существующих зависимостей](#Generate) между слоями.  
  
4.  [Изменение слоев и зависимостей](#EditArchitecture) для отображения обновленной разработки, соответствующей необходимому коду.  
  
5.  [Разработка новых областей приложения](#NewAreas) путем создания слоев, представляющих принципиальные архитектурные блоки или компоненты и определения зависимостей для отображения, как каждый слой использует другие.  
  
6.  [Измените структуру и внешний вид схемы](#EditLayout) чтобы обсудить ее с коллегами.  
  
7.  [Проверка кода по схеме слоев](#Validate) чтобы выявить конфликты между кодом и требуемой архитектурой.  
  
8.  [Обновите код, чтобы он соответствовал новой архитектуре](#UpdateCode). Итерационно разрабатывайте и оптимизируйте код до тех пор, пока проверка не укажет, что конфликты отсутствуют.  
  
9. [Включите проверку слоев в процесс построения](#BuildValidation) чтобы обеспечить соответствие кода проекту.  
  
##  <a name="Create"></a> Создание схемы слоев  
 Схема слоев должна создаваться внутри проекта моделирования. Можно добавить новую схему слоя в существующий проект моделирования, создайте новый проект моделирования для схемы слоя или скопируйте схему слоя в том же проекте моделирования.  
  
> [!IMPORTANT]
>  Не следует добавлять, перетаскивать или копировать существующую схему слоев из одного проекта моделирования в другой или в другое местоположение в решении. Скопированные таким образом схемы слоев содержат те же ссылки, что и исходная схема, даже если вы ее измените. Это может привести к тому, что проверка схемы будет работать неправильно, а также к другим потенциальным проблемам, таким как отсутствующие элементы или другие ошибки при попытке открыть схему.  
  
 См. в разделе [Создание схем слоев из кода](../modeling/create-layer-diagrams-from-your-code.md).  
  
##  <a name="CreateLayers"></a> Определите слои для представления функциональных областей или компонентов  
 Слои представляют собой логические группы *артефакты*, таких как проекты, файлы кода, пространства имен, классы и методы. Можно создать слои из артефактов из проектов Visual C# .NET и Visual Basic .NET, или же можно привязать спецификации или планы к слою путем связывания документов, таких как файлы Word или презентации PowerPoint. Каждый слой представляет собой прямоугольник на схеме и показывает количество артефактов, связанных с ним. Слой может содержать вложенные слои, описывающие более конкретные задачи.  
  
 Рекомендуется называть слои согласно их функциям, например "Презентация" или "Службы". Если артефакты тесно взаимосвязаны, поместите их в один слой. Если артефакты могут быть обновлены отдельно или использованы в разных приложениях, поместите их на разные слои. Дополнительные сведения о шаблонах слоев, посетите на сайте Patterns & Practices по адресу [ http://go.microsoft.com/fwlink/?LinkId=145794 ](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
> [!TIP]
>  Существуют некоторые типы артефактов, которые можно связать со слоями, но при этом поддержки проверки схемы слоев не будет. Чтобы узнать, поддерживает ли артефакт проверку, откройте **обозреватель слоев** изучаемый **поддерживает проверку** свойство ссылки на артефакт. См. в разделе [обнаружение существующих зависимостей между слоями](#Generate).  
  
 При обновлении незнакомого приложения можно также создать карты кода. Они помогают обнаружить закономерности и зависимости при анализе кода. Воспользуйтесь обозревателем решений, чтобы изучить пространства имен и классы, которые часто находятся в точном соответствии с существующими слоями. Назначьте эти артефакты кода слоям, перетащив их из обозревателя решений на схемы слоев. Затем схемы слоев можно использовать для обновления кода и обеспечения его соответствия проекту.  
  
 Пример  
  
-   [Создание схем слоев на основе кода](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Использование карт кода для отладки приложений](../modeling/use-code-maps-to-debug-your-applications.md)  
  
-   [Сопоставление зависимостей во всех решениях](../modeling/map-dependencies-across-your-solutions.md)  
  
##  <a name="Generate"></a> Обнаружение существующих зависимостей между слоями  
 Зависимости существуют там, где артефакт, связанный с одним слоем, ссылается на артефакт, связанный с другим слоем. Например, класс в одном слое объявляет переменную, которая имеет класс в другом слое. Существующие зависимости можно обнаружить путем их реконструирования.  
  
> [!NOTE]
>  Для определенных видов артефактов реконструировать зависимости невозможно. Например, зависимости не могут быть реконструированы из или в слой, связанный с текстовым файлом. Чтобы увидеть, какие артефакты имеют зависимости, которые можно реконструировать, щелкните правой кнопкой мыши один или несколько слоев и нажмите кнопку **Просмотр ссылок**. В **обозреватель слоев**, изучите **поддержка проверки** столбца. Зависимости не будут реконструированы для артефактов, для которых в этом столбце отображается **False**.  
  
#### <a name="to-reverse-engineer-existing-dependencies-between-layers"></a>Чтобы выполнить реконструирование существующих зависимостей между слоями  
  
-   Выберите один или несколько слоев, щелкните правой кнопкой мыши выделенные и нажмите кнопку **создать зависимости**.  
  
 Как правило, на этом этапе можно увидеть некоторые зависимости, которых быть не должно. Эти зависимости можно изменить для соответствия предполагаемой структуре.  
  
##  <a name="EditArchitecture"></a> Изменение слоев и зависимостей для отображения предполагаемой структуры  
 Чтобы описать изменения, которые планируется внести в систему или предполагаемую архитектуру, осуществите следующие шаги для изменения схемы слоев. Можно также сделать некоторые оптимизационные изменения для улучшения структуры кода перед его расширением. См. в разделе [Совершенствование структуры кода](#Improving).  
  
|**Задача**|**Выполните следующие действия**|  
|------------|-----------------------------|  
|Удаление зависимости, которой не должно существовать|Выделите зависимость и нажмите клавишу **удалить**.|  
|Изменить или ограничить направление зависимости|Задайте его **направление** свойство.|  
|Создать новые зависимости|Используйте **зависимостей** и **Двунаправленная зависимость** средства.<br /><br /> Чтобы нарисовать несколько зависимостей, дважды щелкните средство. Когда вы закончите, нажмите кнопку **указатель** средство или нажмите клавишу **ESC** ключ.|  
|Указание, что артефакт, связанный со слоем, не может зависеть от указанного пространства имен|Введите пространства имен в свойстве слоя **Запрещенные зависимости пространства имен** свойство. Используйте точку с запятой (**;**) для разделения пространства имен.|  
|Указание, что артефакт, связанный со слоем, не должен более принадлежать указанному пространству имен|Введите пространства имен в свойстве слоя **Запрещенные пространства имен** свойство. Используйте точку с запятой (**;**) для разделения пространства имен.|  
|Указание, что артефакт, связанный со слоем, должен принадлежать одному из указанных пространств имен|Введите пространство имен в свойстве слоя **обязательные пространства имен** свойство. Используйте точку с запятой (**;**) для разделения пространства имен.|  
  
###  <a name="Improving"></a> Совершенствование структуры кода  
 Оптимизация изменений — это улучшения, которые не влияют на поведение приложения, но помогают сделать код более легким для изменения или расширения в будущем. Хорошо структурированный код имеет такой вид, который потом легко можно поместить в схему слоев.  
  
 Например, если создается слой для каждого пространства имен в коде и затем разбираются зависимости, то необходимо, чтобы был минимальный набор односторонних зависимостей между слоями. Если создается более детальная схема с использованием классов или методов в качестве слоев, то результат должен иметь такие же характеристики.  
  
 Если это не так, то код будет более сложным для изменения в течение всего времени и менее подходящим для проверки с использованием схем слоев.  
  
##  <a name="NewAreas"></a> Разработка новых областей приложения  
 При начале разработки нового проекта или новой области в новом проекте, можно нарисовать слои и зависимости, чтобы облегчить определение основных компонентов перед началом разработки кода.  
  
-   **Отобразите определяемые архитектурные шаблоны** на схемах слоев, если это возможно. Например, схема слоев, которая описывает настольное приложение, может включать такие слои, как "Презентация", "Доменная логика" и "Хранилище данных". Схема слоев, которая относится к одному компоненту приложения, может иметь такие слои, как "Модель", "Вид" и "Контроллер". Дополнительные сведения об этих шаблонах см. в разделе [Patterns & Practices: архитектура приложения](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
     Если вы часто создаете похожие шаблоны, то можно создать пользовательский инструмент. См. в разделе [определение настраиваемого элемента панели элементов моделирования](../modeling/define-a-custom-modeling-toolbox-item.md).  
  
-   **Создайте артефакт кода для каждого слоя** например пространство имен, класс или компонент. Это облегчит отслеживание кода и поможет связывать артефакты кода со слоями. Сразу после создания артефакта свяжите его с соответствующим слоем.  
  
-   **У вас нет необходимости связывать большинство классов и другие артефакты со слоями** так, как они входят в более крупных артефактов, таких как пространства имен, которые вы уже связали со слоями.  
  
-   **Создайте новую схему для новой функции**. Обычно будет создана одна или несколько схем слоев, описывающих все приложение. Если вы разрабатываете новую функцию в приложении, то не добавляйте и не изменяйте существующие схемы. Вместо этого создайте свою схему, которая отражает новые части кода. Слои в новой схеме могут включать в себя презентацию, доменную логику и слои базы данных для новой функции.  
  
     При построении приложения код будет проверяться как в отношении всей схемы , так и в отношении более детальной схемы возможности.  
  
##  <a name="EditLayout"></a> Изменение макета для представления и обсуждения  
 Чтобы облегчить определение слоев и зависимостей или обсудить их с членами команды, измените вид и разметку схемы следующим образом.  
  
-   Измените размеры, формы и положение слоев.  
  
-   Измените цвета слоев и зависимостей.  
  
    -   Выберите один или несколько слоев или зависимостей, щелкните правой кнопкой мыши и выберите команду **свойства**. В **свойства** окне редактирования **цвет** свойство.  
  
##  <a name="Validate"></a> Проверка кода по схеме  
 После изменения схемы можно проверить код вручную в любое время или автоматически при каждом запуске локального построения или [!INCLUDE[esprbuild](../includes/esprbuild-md.md)].  
  
 Пример  
  
-   [Проверка кода по схемам слоев](../modeling/validate-code-with-layer-diagrams.md)  
  
-   [Включите проверку слоев в процесс построения](#BuildValidation)  
  
##  <a name="UpdateCode"></a> Обновите код, чтобы он соответствовал новой архитектуре  
 Обычно ошибки появляются при первой проверке кода в обновленной схеме слоя. Ошибки могут возникать вследствие нескольких причин.  
  
-   Артефакт назначен неправильному слою. В этом случае следует переместить артефакт.  
  
-   Способ использования артефактом (например, классом) другого класса конфликтует с имеющейся архитектурой. В этом случае необходимо выполнить рефакторинг кода, чтобы устранить зависимость.  
  
 Для устранения этих ошибок следует обновлять код до тех пор, пока в процессе проверки не перестанут происходить ошибки. Обычно это итерационный процесс. Дополнительные сведения об этих ошибках см. в разделе [проверка кода по схемам слоев](../modeling/validate-code-with-layer-diagrams.md).  
  
> [!NOTE]
>  Возможно, во время разработки или оптимизации кода понадобится связать новые артефакты со схемой слоев. Однако это может не потребоваться, например, когда слои представляют собой существующие пространства имен, а новый код только добавляет больше материала для них.  
  
 В процессе разработки может понадобиться подавить некоторые конфликты, выявленные в ходе проверки. Например, можно подавлять ошибки, над которыми уже ведется работа, а также ошибки, не имеющие отношения к конкретному сценарию. При подавлении ошибки рекомендуется фиксировать рабочий элемент в журнале в [!INCLUDE[esprfound](../includes/esprfound-md.md)]. Для выполнения этой задачи, см. в разделе [проверка кода по схемам слоев](../modeling/validate-code-with-layer-diagrams.md).  
  
##  <a name="BuildValidation"></a> Включите проверку слоев в процесс построения  
 Чтобы убедиться, что будущие изменения в коде соответствуют схеме слоев, включите проверку слоев в стандартный процесс построения решения. Всякий раз, когда другая команда начинает построение решения, любые изменения между зависимостями в коде и в схеме слоев будут отображаться как ошибки построения. Дополнительные сведения о включении проверки слоев в процесс сборки, см. в разделе [проверка кода по схемам слоев](../modeling/validate-code-with-layer-diagrams.md).  
  
## <a name="see-also"></a>См. также  
 [Схемы слоев: ссылка](../modeling/layer-diagrams-reference.md)   
 [Создание схем слоев на основе кода](../modeling/create-layer-diagrams-from-your-code.md)


