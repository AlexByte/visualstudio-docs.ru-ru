---
title: Настройка элементов и элементов | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.selectiondialog
- vs.dsltools.dsldesigner.selecticondialog
- vs.dsltools.dsldesigner.selectcursordialog
helpviewer_keywords:
- Domain-Specific Language, toolbox
ms.assetid: 2a0d03d7-ebc6-4458-b9f4-d2cb8418a62d
caps.latest.revision: 28
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 97682059e90bac38b0b8b00492ff9fd50a36ffab
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559289"
---
# <a name="customizing-tools-and-the-toolbox"></a>Настройка элементов и панели элементов
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [Настройка элементов и панели элементов](https://docs.microsoft.com/visualstudio/modeling/customizing-tools-and-the-toolbox).  
  
Для тех элементов, которые пользователи смогут добавлять в свои модели, необходимо определить содержание панели элементов. Панель элементов может содержать два вида средств: средства элемента и средства подключения. В созданном конструкторе пользователь может выбрать средство элемента, чтобы перетащить фигуры на схему, и средство подключения, чтобы протянуть связи между фигурами. В целом средства элемента позволяют пользователям добавлять в модели экземпляры классов доменов, а средства подключения — экземпляры доменных связей.  
  
 В этом разделе.  
  
-   [Определение панели элементов](#ToolboxDef)  
  
-   [Настройка средств элемента](#customizing)  
  
-   [Создание групп элементов с помощью средства](#groups)  
  
-   [Настройка средств подключения](#connections)  
  
##  <a name="ToolboxDef"></a> Определение панели элементов  
 В Обозревателе DSL разверните узел "Редактор" и узлы под ним. Обычно при этом отрывается иерархия следующего вида:  
  
```  
  
Editor  
     Toobox Tabs  
        MyDsl          //a tab  
           Tools  
               ExampleElement      // an element tool  
               ExampleRelationship // a connection tool  
  
```  
  
 В этой части Обозревателя DSL можно выполнять следующие действия.  
  
-   Создавать новые таблицы. Вкладки определяют заголовки разделов в панели элементов.  
  
-   Создавать новые средства.  
  
-   Копировать и вставлять средства.  
  
-   Перемещать средства вверх или вниз по списку.  
  
-   Удалять вкладки и средства.  
  
> [!IMPORTANT]
>  Чтобы добавить или вставить элементы в Обозреватель DSL, щелкните прародителя нового узла правой кнопкой мыши. Например, чтобы добавить средство, щелкните правой кнопкой мыши вкладку, а не **средства** узла. Чтобы добавить вкладку, щелкните правой кнопкой мыши **редактор** узла.  
  
 **Значок панели элементов** каждого средства ссылается на файл точечного рисунка 16 x 16. Эти файлы обычно хранятся в **Dsl\Resources** папки.  
  
 **Класс** свойство средства элемента ссылается на конкретный класс домена. По умолчанию средство будет создавать экземпляры данного класса. Тем не менее можно написать код, заставляющий средство создавать элементы или группы элементов другого типа.  
  
 **Построитель подключения** свойство средства подключения ссылается на построитель подключений, который определяет типы элементов, которые средство может подключать, и какие отношения он создает между ними. Построители подключений определяются в виде узлов в Обозревателе DSL. Построители подключений создаются автоматически при определении доменных связей, но могут также настраиваться с помощью кода.  
  
#### <a name="to-add-a-tool-to-the-toolbox"></a>Добавление средства в панель элементов  
  
1.  Средство элемента обычно создают после создания класса фигуры и его сопоставления с классом домена.  
  
     Средство подключения обычно создают после создания класса соединителя и его сопоставления со ссылочным отношением.  
  
2.  В обозревателе DSL разверните **редактор** узла и **вкладки панели элементов** узла.  
  
     Щелкните правой кнопкой мыши узел панели элементов, а затем нажмите кнопку **добавить новое средство элемента** или **добавить новое средство подключения**.  
  
3.  Задайте **значок панели элементов** свойство для ссылки точечного рисунка 16 x 16.  
  
     Если вы хотите определить новый значок, создайте файл точечного рисунка в обозревателе решений в **Dsl\Resources** папки. Файл должен содержать следующие значения свойств: **действие при построении** = **содержимого**; **Копировать в выходной каталог** = **не Копировать**.  
  
4.  **Для средства элемента:** задать **класс** средства для ссылки на конкретный класс домена, сопоставляемого с фигурой.  
  
     **Для средства подключения:** задать **построитель подключения** свойство средства на один из элементов, предлагаемых в раскрывающемся списке. Построители подключений автоматически создаются при сопоставлении соединителя с доменной связью. Сразу после создания соединителя, как правило, выбирается соответствующий построитель подключений.  
  
5.  Чтобы проверить DSL, нажмите клавишу F5 или сочетание клавиш CTRL + F5 и откройте в экспериментальном экземпляре [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] пример файла модели. На панели элементов должно появиться новое средство. Перетащите его на схему, чтобы проверить, создает ли оно новый элемент.  
  
     Если средство не появляется, остановите экспериментальный экземпляр [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. В Windows **запустить** меню **Сброс экспериментального экземпляра Microsoft Visual Studio 2010**. На [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] **построения** меню, щелкните **Перестроить решение**. Затем проверьте DSL еще раз.  
  
##  <a name="customizing"></a> Настройка средств элемента  
 По умолчанию средство создает один экземпляр указанного класса, но это можно изменять двумя описанными ниже способами.  
  
-   Определить директивы слияния элемента с другими классами, позволив им принимать новые экземпляры этого класса и создавать дополнительные ссылки при создании нового элемента. Например, можно разрешить пользователю оставить комментарий на другой элемент и тем самым создать между ними справочную ссылку.  
  
     Эти настройки также влияют на процесс вставки и перетаскивания элемента.  
  
     Дополнительные сведения см. в разделе [Настройка создания и перемещения элементов](../modeling/customizing-element-creation-and-movement.md).  
  
-   Написать код, чтобы настроить средство на возможность создания групп элементов. Средство запускается методами из файла ToolboxHelper.cs, которые можно переопределить. Дополнительные сведения см. в разделе [Создание групп элементов с помощью средства](#groups).  
  
##  <a name="groups"></a> Создание групп элементов с помощью средства  
 Каждое средство элемента содержит прототип элементов, которые оно должно создавать. По умолчанию, каждое средство элемента создает один элемент, но может также создавать группу объектов, связанных с одним средством. Для этого запустите средство с помощью класса <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>, который содержит связанные элементы.  
  
 Следующий пример взят из DSL, в котором есть тип "Транзистор". Каждый транзистор имеет три именованных контакта. Средство элемента для транзисторов хранит прототип, содержащий четыре элемента модели и три ссылки отношения. Когда пользователь перетаскивает средство на схему, создается экземпляр прототипа, который связывается с корнем модели.  
  
 Этот код переопределяет метод, который определен в **Dsl\GeneratedCode\ToolboxHelper.cs**.  
  
 Дополнительные сведения о настройке модели с помощью программного кода, см. в разделе [перехода и обновления модели в программном коде](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
  public partial class CircuitsToolboxHelper  
  {  
    /// <summary>  
    /// Toolbox initialization, called for each element tool on the toolbox.  
    /// This version deals with each Component subtype separately.  
    /// </summary>  
    /// <param name="store"></param>  
    /// <param name="domainClassId">Identifies the domain class this tool should instantiate.</param>  
    /// <returns>prototype of the object or group of objects to be created by tool</returns>  
    protected override ElementGroupPrototype CreateElementToolPrototype(Store store, Guid domainClassId)  
    {  
        if (domainClassId == Transistor.DomainClassId)  
        {  
            Transistor transistor = new Transistor(store);  
  
            transistor.Base = new ComponentTerminal(store);  
            transistor.Collector = new ComponentTerminal(store);  
            transistor.Emitter = new ComponentTerminal(store);  
  
            transistor.Base.Name = "base";  
            transistor.Collector.Name = "collector";  
            transistor.Emitter.Name = "emitter";  
  
            // Create an ElementGroup for the Toolbox.  
            ElementGroup elementGroup = new ElementGroup(store.DefaultPartition);  
            elementGroup.AddGraph(transistor, true);  
            // AddGraph includes the embedded parts  
  
            return elementGroup.CreatePrototype();  
        }  
        else  
        {  
            return base.CreateElementToolPrototype(store, domainClassId);  
}  }    }  
  
```  
  
##  <a name="connections"></a> Настройка средств подключения  
 Как правило, средство элемента создается при создании нового класса соединителя. Кроме того, можно переопределить одно средство, разрешив типам и обеих сторон определять тип отношения. Например, можно определить одно средство подключения, которое может создавать как отношения типа "человек — человек", так и отношения типа "человек — город".  
  
 Средства подключения вызывают построители подключения. Используйте построители подключения, чтобы указать, каким образом пользователи могут связывать элементы в сгенерированном конструкторе. Построители подключений указывают элементы, которые могут быть связаны, а также создаваемый между ними тип связи.  
  
 При создании ссылочного отношения между доменными классами автоматически создается построитель подключения, который можно использовать при сопоставлении средства подключения. Дополнительные сведения о создании средств подключения см. в разделе [Настройка панели элементов](../modeling/customizing-tools-and-the-toolbox.md).  
  
 Построитель подключения по умолчанию можно изменить так, чтобы он мог справляться с другим диапазоном исходных и целевых типов, а также создавать различные типы отношений.  
  
 Также, для построителей подключения можно написать пользовательский код, чтобы указать исходные и целевые классы для подключения, определить тип создаваемого подключения, и выполнить другие действия, связанные с созданием подключения.  
  
### <a name="the-structure-of-connection-builders"></a>Структура построителей подключения  
 Построители подключений содержат одну или несколько директив подключения связей, которые определяют доменные связи, а также исходные и целевые элементы. Например, вы увидите в шаблоне решения Task Flow, **CommentReferencesSubjectsBuilder** в **обозреватель DSL**. Этот построитель подключения содержит одну ссылку директиву с именем подключения **CommentReferencesSubjects**, который сопоставлен с доменной связью **CommentReferencesSubjects**. Эта директива подключения связи содержит директиву исходной роли, указывающую на класс домена `Comment`, и директиву целевой роли, указывающую на класс домена `FlowElement`.  
  
### <a name="using-connection-builders-to-restrict-source-and-target-roles"></a>Использование построителей подключений для ограничения ограниченным исходных и целевых ролей  
 Построители подключений можно использовать для ограничения вхождения некоторых классов в исходную или в целевую роль определенной доменной связи. Например, у вас есть базовый класс домена, имеющий доменную связь с другим классом домена, но вы не хотите, чтобы все производные этого базового класса получали в этой связи те же самые роли. В решении Task Flow есть четыре конкретных класса доменов (**StartPoint**, **конечной точки**, **MergeBranch**, и **синхронизации**), наследуемым непосредственно от абстрактного класса домена **FlowElement**, и две конкретные классы доменов (**задачи** и **ObjectInState**), косвенно наследовать от него. Имеется также **потока** ссылочное отношение, которое принимает **FlowElement** доменные классы в роли источника и целевой роли. Тем не менее экземпляр **конечной точки** доменного класса не должен быть источником экземпляра **потока** связи, и не должны экземпляр **StartPoint** класс быть целевой экземпляр **потока** связи. **FlowBuilder** у построителя подключений есть директивы с именем подключения связи **потока** , указывающий, какие классы домена может играть роль источника (**задачи**,  **MergeBranch**, **StartPoint**, и **синхронизации**) и который может играть роль целевого объекта (**MergeBranch**,  **Конечная точка**, и **синхронизации**).  
  
### <a name="connection-builders-with-multiple-link-connect-directives"></a>Построители подключений с несколькими директивами подключения связи  
 К построителю подключений можно добавить несколько директив подключения связи. Это может помочь скрыть некоторые сложности модели домена у пользователей и сохранить **элементов** предотвратить чрезмерное загромождение. К одному построителю подключений можно добавить директивы подключения связи для нескольких различных отношений домена. При этом доменные связи следует объединять в том случае, если они выполняют примерно одинаковую функцию.  
  
 В решении Task Flow **потока** средства подключения используется для рисования экземплярами **потока** и **ObjectFlow** доменных связей. **FlowBuilder** у построителя подключений есть, в дополнение к **потока** ранее описанной директиве подключения связи, две директивы добавления связей с именем **ObjectFlow**. Эти директивы указывают, что экземпляр **ObjectFlow** связь может быть протянут между экземплярами **ObjectInState** доменного класса или из экземпляра **ObjectInState**  к экземпляру **задачи**, но не между двумя экземплярами **задачи**, или из экземпляра **задачи** к экземпляру **ObjectInState**. Однако экземпляр **потока** связь может быть протянут между двумя экземплярами **задачи**. Если скомпилировать и запустить решение Task Flow, можно увидеть, что Рисование **потока** из экземпляра **ObjectInState** к экземпляру **задачи** создает экземпляр класса **ObjectFlow**, но рисования **потока** между двумя экземплярами **задачи** создает экземпляр класса **потока**.  
  
### <a name="custom-code-for-connection-builders"></a>Пользовательский код для построителей подключения  
 В пользовательском интерфейсе имеются четыре флажка, определяющие различные типы настройки построителей подключений:  
  
-   **настраиваемое принятие** "флажок" в директиве исходной или целевой роли  
  
-   **настраиваемое подключение** "флажок" в директиве исходной или целевой роли  
  
-   **использует настраиваемое подключение** "флажок" в директиве подключения  
  
-   **является настраиваемым** свойство построителя подключений  
  
 Чтобы указать эти настройки, необходимо предоставить определенный программный код. Чтобы узнать, какой код необходимо предоставить, установите один их этих флажков, нажмите кнопку "Преобразовать все шаблоны" и постройте собственное решение. В результате будет получено сообщение об ошибке. Дважды щелкните сообщение об ошибке, чтобы увидеть комментарий с описанием кода, который необходимо добавить.  
  
> [!NOTE]
>  Чтобы добавить пользовательский код, создайте определение разделяемого класса в файле кода отдельно от файлов кода, находящихся в папках GeneratedCode. Чтобы не потерять свою работу, не изменяйте созданные файлы кода. Дополнительные сведения см. в разделе [переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).  
  
#### <a name="creating-custom-connection-code"></a>Создание пользовательского кода подключения  
 В каждой связи директиве подключения **источника директивы роли** определяет вкладку из типы, из которых можно перетаскивать. Аналогичным образом **целевые директивы роли** вкладке определяет типы, из которых можно перетаскивать. Для каждого типа, можно уточнить запрос на разрешение соединения (для этой директивы подключения связи), задав **настраиваемое принятие** флаг и предоставьте дополнительный код.  
  
 Также можно настроить действия, происходящие после выполнения подключения. Например, можно настроить только случай перетаскивания в определенный класс, все случаи, когда приоритетное значение имеет одна директива подключения связи, или весь построитель подключения FlowBuilder. Для каждого из этих вариантов можно установить пользовательские флажки на соответствующем уровне. При преобразовании всех шаблонов и попытке построить решение вы получите сообщения об ошибках с комментариями к созданному коду. В этих комментариях указывается, что необходимо предоставить.  
  
 В примере "Схема компонентов" построитель подключения для доменной связи "Подключение" ограничивает подключения, которые могут быть установлены между портами. На следующей иллюстрации показано, что подключения можно установить только от элементов `OutPort` к элементам `InPort`, но компоненты можно вкладывать друг в друга.  
  
 **Подключение, поступающих OutPort вложенного компонента**  
  
 ![Построитель подключения](../modeling/media/connectionbuilder-3.png "ConnectionBuilder_3")  
  
 В связи с этим необходимо указать, что подключение может идти от вложенного компонента к типу OutPort. Чтобы указать такое подключение, необходимо задать **использует настраиваемое принятие** на **InPort** качестве исходной роли и **OutPort** типа, что и целевой роли в **подробные сведения о DSL**  окна, как показано на следующем рисунке:  
  
 **Директива подключения связи в обозревателе DSL**  
  
 ![Изображение мастера подключения](../modeling/media/connectionbuilder-4a.png "ConnectionBuilder_4a")  
  
 **Директива подключения связи в окно сведений DSL**  
  
 ![](../modeling/media/connectionbuilder-4b.png "ConnectionBuilder_4b")  
  
 После этого в класс ConnectionBuilder необходимо предоставить методы:  
  
```  
  public partial class ConnectionBuilder  
  {  
    /// <summary>  
    /// OK if this component has children  
    /// </summary>  
    private static bool CanAcceptInPortAsSource(InPort candidate)  
    {  
       return candidate.Component.Children.Count > 0;  
    }  
  
    /// <summary>  
    /// Only if source is on parent of target.  
    /// </summary>  
    private static bool CanAcceptInPortAndInPortAsSourceAndTarget                (InPort sourceInPort, InPort targetInPort)  
    {  
      return sourceInPort.Component == targetInPort.Component.Parent;  
    }  
// And similar for OutPorts…  
```  
  
 Дополнительные сведения о настройке модели с помощью программного кода, см. в разделе [перехода и обновления модели в программном коде](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 Подобный код можно использовать, например, для того, чтобы запретить пользователям создавать циклы со связями между родительскими и дочерними объектами. Эти ограничения считаются жесткими, потому что пользователи не смогут их нарушать. Можно создавать мягкие проверки достоверности, которые пользователи смогут временно обходить, создавая недопустимые конфигурации без возможности сохранения.  
  
### <a name="good-practice-in-defining-connection-builders"></a>Рекомендации по определению построителей подключений  
 Чтобы создаваемые типы отношений были концептуально связаны, настраивайте только один построитель подключений. В примере с задачей потока (Task Flow) для создания потоков между задачами, а также между задачами и объектами используется один и тот же построитель. В то же время использование одного и того же построителя для создания отношений между комментариями и задачами может создавать путаницу.  
  
 Определяя построитель подключений для нескольких типов отношений, обязательно убедитесь, что он не может сопоставить больше одного типа из одной той же пары исходных и целевых объектов. В противном случае результаты будут непредсказуемы.  
  
 Пользовательский код используется для применения жестких ограничений. Подумайте, не стоит ли разрешить пользователям временное создание недопустимых подключений. Если такую возможность необходимо предоставить, ограничения можно изменить таким образом, чтобы эти подключения не проверялись до тех пор, пока пользователи не попытаются сохранить изменения.  
  
## <a name="see-also"></a>См. также  
 [Настройка создания и перемещения элементов](../modeling/customizing-element-creation-and-movement.md)   
 [Настройка функции копирования](../modeling/customizing-copy-behavior.md)   
 [Практическое: Добавление обработчика перетаскивания и вставки](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Переход и обновление модели в программном коде](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Пример схемы канала DSL](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)


