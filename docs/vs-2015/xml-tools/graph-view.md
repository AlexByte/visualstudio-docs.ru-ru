---
title: Графическое представление | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5881afde-3f24-4eb9-bff8-6cb3fc8aade7
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 92192e36cc0acd33734974a2ddf723df7dfbc55a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47557578"
---
# <a name="graph-view"></a>Представление диаграммы
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [представление графика](https://docs.microsoft.com/visualstudio/xml-tools/graph-view).  
  
  
Представление графика обеспечивает графическое представление глобальных узлов схемы и связей между узлами. Заметьте, что представление графика не позволяет изменять расположение набора схем в области конструктора. Представление графика также содержит панель инструментов конструктора XML-схем и строка навигатора.  
  
 На приведенном ниже рисунке показано представление графика с шестью глобальными узлами в области конструктора:  
  
 ![Представление графика конструктора схемы XML](../xml-tools/media/xsddesigner-graphview.gif "XSDDesigner_GraphView")  
  
## <a name="design-surface"></a>Область конструктора  
 Области конструктора представления графика отображает содержимое [рабочей области конструктора схем XML](../xml-tools/xml-schema-designer-workspace.md). Если рабочая область содержит глобальные узлы из набора схем, узлы будут показаны в области конструктора представления графика, а узлы, связанные друг с другом, будут соединены стрелочками.  
  
 Двойное нажатие на узел в представлении графика открывает редактор XML.  
  
 Чтобы удалить выбранные узлы в рабочей области, используйте панель инструментов конструктора XSD или клавишу DELETE.  
  
 Если область конструктора пуста, редактор XML, обозреватель XML-схем и водяной знак не отображаются. *Водяного знака* приведен список ссылок на все представления конструктора XSD.  
  
 ![Конструктор XSD; Графическое представление](../xml-tools/media/xsdgraphviewwatermark.gif "XSDGraphViewWatermark")  
  
 Если набор схем содержит ошибки, в конце списка появится следующий текст: «Воспользуйтесь списком ошибок для просмотра и устранения ошибок в наборе».  
  
## <a name="breadcrumb-bar"></a>Строка навигатора  
 Строка навигатора внизу представления графика показывает месторасположение выбранного узла в наборе схем. Если выбрано несколько элементов, строка навигатора будет пустой.  
  
## <a name="context-menu"></a>Контекстное меню  
 В следующей таблице приведены параметры, доступные для всех узлов поверхности конструктора представления графика.  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Показать в обозревателе XML-схем**|Устанавливает фокус на обозревателе схем и выделяет узел набора схем.|  
|**Показать в представлении графика**|Переключается в представление графика (отображается серым цветом).|  
|**Создание образца XML**|Этот метод предусмотрен только для глобальных элементов. Создает образец XML-файла для глобального элемента.|  
|**Очистить рабочую область**|Очищает рабочую область и область конструктора.|  
|**Удалить из рабочей области**|Удаляет выбранные узлы из рабочей области и из области конструктора.|  
|**Удалите все, кроме выделенных в рабочей области**|Удаляет узлы, не выделенные в рабочей области и в области конструктора.|  
|**Экспортируйте схему как рисунок …**|Сохраняет область конструктора в XPS-файле.|  
|**Выбрать все**|Выбирает все узлы в области конструктора.|  
|**Просмотреть код**|Открывает в редакторе XML-файл, содержащий выбранный узел. Пункт, выбранный в обозревателе XML-схем, будет выбран и в редакторе XML.|  
|**Окно "Свойства"**|Открывает **свойства** окна (если он еще не открыт). В данном окне будут выведены сведения об узле.|  
  
 Помимо описанных выше общих параметров контекстное меню для глобальных элементов также имеет следующие параметры:  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Добавить определение типа**|Добавляет базовый тип в схему.|  
|**Добавить все ссылки**|Добавляет все узлы, связанные с элементом, и рисует стрелочки, обозначающие связи между ними.|  
|**Добавить элементы группы подстановок**|Добавляет все члены группы подстановки. Данный параметр появляется в представлении, если элемент является головным элементом или членом группы подстановки.|  
|**Создание образца XML**|Создает образец XML-файла для глобального элемента.|  
  
 Помимо описанных выше общих параметров контекстное меню для глобальных простых и глобальных сложных типов также имеет следующие параметры:  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Добавить базовый тип**|Если выбранный тип является производным от глобального типа, добавляет базовый тип выбранного типа.|  
|**Добавить все ссылки**|Добавляет все ссылки выбранного типа. Это относится ко всем элементам и атрибутам выбранного типа и типов, производных от выбранного.|  
|**Добавить все производные типы**|Добавляет все типы, прямо или косвенно являющиеся производными от выбранного типа.|  
|**Добавить всех предков**|Добавляет все родительские (базовые) типы.|  
  
 Помимо общих параметров, описанных выше, контекстное меню для глобальных групп и групп атрибутов также имеет следующие параметры:  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Добавить все ссылки**|Добавляет все узлы, связанные с группой, и рисует стрелочки, обозначающие связи между ними.|  
|**Добавляет всех членов**|Добавляет все члены группы и рисует стрелочки, обозначающие связи между ними.|  
  
 Помимо описанных выше общих параметров контекстное меню для глобальных атрибутов также имеет следующие параметры:  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Добавить все ссылки**|Добавляет все узлы, связанные с группой, и рисует стрелочки, обозначающие связи между ними.|  
  
## <a name="properties-window"></a>Окно свойств  
 Используйте контекстное меню, чтобы открыть **свойства** окна. По умолчанию **свойства** окно отображается в правом нижнем углу Visual Studio. Если щелкнуть узел, который отображается в представлении модели содержимого, свойств этого узла будет отображаться в **свойства** окна.  
  
## <a name="xsd-toolbar"></a>Панель инструментов XSD  
 Следующие кнопки панели инструментов XSD включены, если активно представление графика.  
  
 ![Панель инструментов конструктора схемы XML](../xml-tools/media/xsdgraphviewtoolbar.gif "XSDGraphViewToolbar")  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Показать начальное представление**|Переключается в [начальное представление](../xml-tools/start-view.md). Это представление может осуществляться с помощью сочетания клавиш: **CTRL + 1**.|  
|**Показать представление модели содержимого**|Переключается в [просмотра модели содержимого](../xml-tools/content-model-view.md). Это представление может осуществляться с помощью сочетания клавиш: **CTRL + 2**.|  
|**Показать представление графика**|Переключается в [графическое представление](../xml-tools/graph-view.md). Это представление может осуществляться с помощью сочетания клавиш: **CTRL + 3**.|  
|**Очистить рабочую область**|Очищает рабочую область и область конструктора.|  
|**Удалить из рабочей области**|Удаляет выбранные узлы из рабочей области и из области конструктора.|  
|**Удалите все, кроме выделенных в рабочей области**|Удаляет узлы, не выделенные в рабочей области и в области конструктора. Данный параметр включен в представлении модели содержимого и в представлении графика.|  
|**Слева направо**|Изменяет макет в представлении графика на иерархическое представление узлов слева направо. Этот параметр может осуществляться с помощью сочетания клавиш: **Alt + Стрелка вправо**.|  
|**Справа налево**|Изменяет макет в представлении графика на иерархическое представление узлов справа налево. Этот параметр может осуществляться с помощью сочетания клавиш: **Alt + Стрелка влево**.|  
|**Сверху вниз**|Изменяет макет в представлении графика на иерархическое представление узлов сверху вниз. Этот параметр может осуществляться с помощью сочетания клавиш: **Alt + Стрелка вниз**.|  
|**Снизу вверх**|Изменяет макет в представлении графика на иерархическое представление узлов снизу вверх. Этот параметр может осуществляться с помощью сочетания клавиш: **Alt + Стрелка вверх**.|  
  
## <a name="panscroll"></a>Панорамирование/Прокрутка  
 Можно панорамировать область конструктора с использованием полос прокрутки или удерживая нажатой клавишу CTRL при нажатии и перетаскивании мыши. При панорамировании области конструктора с использованием перетаскивания, курсор изменяет свой внешний вид на четыре перекрестные стрелочки, указывающие в четырех направлениях.  
  
## <a name="undoredo"></a>Отменить/Повторить  
 Функция отменить/повторить включена в представлении графика для следующих действий:  
  
-   Добавление одного узла посредством перетаскивания.  
  
-   Добавление нескольких узлов из окна результатов поиска в обозревателе схемы или запросов начального представления.  
  
-   Удаление одного или нескольких узлов.  
  
## <a name="zoom"></a>Масштаб  
 Масштабирование доступно в нижнем правом углу представления графика.  
  
 Масштабированием можно управлять следующими способами:  
  
-   Удерживая нажатой клавишу CTRL и прокручивая колесико мышки, когда мышь наведена на поверхность представления графика.  
  
-   Используя ползунковый элемент управления. Ползунок отображает текущий масштаб.  
  
 Ползунок масштаба является непрозрачным, если он выбран, если на него наведена мышка или если вы используете клавишу CTRL с колесиком мышки для увеличения масштаба; во всех остальных случаях он является прозрачным.  
  
## <a name="xml-editor-integration"></a>Интеграция редактора XML  
 Можно переключаться между представлением графика и редактором XML, нажимая на узел и используя контекстное меню «Перейти к коду».  
  
 Если изменить набор схем в редакторе XML, изменения будут синхронизированы в представлении графика. Дополнительные сведения см. в разделе [интеграции с помощью редактора XML](../xml-tools/integration-with-xml-editor.md).  
  
## <a name="see-also"></a>См. также  
 [Область конструктора](../xml-tools/xml-schema-designer-workspace.md)


