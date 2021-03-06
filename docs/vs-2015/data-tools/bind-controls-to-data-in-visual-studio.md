---
title: Привязка элементов управления к данным в Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data, displaying
- data sources, displaying data
- Data Sources window
- dislaying data
ms.assetid: be8b6623-86a6-493e-ab7a-050de4661fd6
caps.latest.revision: 42
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3a4143777e51a03867e94f1d4ebdd9c8182a5401
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49291576"
---
# <a name="bind-controls-to-data-in-visual-studio"></a>Привязка элементов управления к данным в Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Для пользователей приложения данные можно отображать путем привязки данных к элементам управления. Можно создать эти элементы управления с привязкой к данным путем перетаскивания элементов из **источников данных** окна на рабочую область конструирования или элементов управления на поверхности в Visual Studio.  
  
 В этом разделе описываются источники данных, которые можно использовать для создания элементов управления с привязкой данных. Также здесь описываются некоторые общие задачи, относящиеся к привязке данных. Дополнительные сведения о том, как создавать элементы управления с привязкой к данным, см. в разделе [управляет привязки Windows Forms к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md) и [элементы управления WPF, привязка к данным в Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md).  
  
## <a name="data-sources"></a>Источники данных  
 В контексте привязки данных источник данных представляет данные в памяти, который можно привязать к интерфейсу пользователя. На практике источник данных может быть класс Entity Framework, набор данных, конечная точка службы, который инкапсулируется в прокси-объект .NET, LINQ to SQL class или любой объект .NET или коллекцию. Некоторые источники данных позволяют создавать элементы управления с привязкой к данным путем перетаскивания элементов из **источников данных** окна, тогда как другие источники данных нет. В следующей таблице приведены поддерживаемые источники данных.  
  
|Источник данных|Поддержка перетаскивания и вставки в **в конструкторе Windows Forms**|Поддержка перетаскивания и вставки в **конструкторе WPF**|Поддержка перетаскивания и вставки в **в конструктор Silverlight**|  
|-----------------|---------------------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------|  
|Набор данных|Да|Да|Нет|  
|EDM (модель данных с использованием сущностей)|Да<sup>1</sup>|Да|Да|  
|Классы LINQ-SQL|Нет <sup>2</sup>|Нет <sup>2</sup>|Нет <sup>2</sup>|  
|Службы (включая [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)], WCF и веб-службы)|Да|Да|Да|  
|Object|Да|Да|Да|  
|SharePoint|Да|Да|Да|  
  
 1. Создание модели с помощью **модели EDM** мастера, затем перетащить нужные объекты в конструктор.  
  
 2. Классы LINQ to SQL не отображаются в **источников данных** окна. Однако можно добавить новый источник данных объектов, основанный на классах LINQ to SQL, а затем перетащить нужные объекты в конструктор, чтобы создать элементы управления с привязкой к данным. Дополнительные сведения см. в разделе [Пошаговое руководство: создание классов LINQ to SQL (реляционный конструктор объектов)](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233).  
  
## <a name="data-sources-window"></a>Источники данных - окно  
 Источники данных доступны в проекте как элементы в **источников данных** окна. Это окно является видимым или доступен из **представление** меню, когда поверхность разработки формы является активным окном в проекте. Можно перетащить элементы из этого окна для создания элементов управления, привязанных к базовым данным и источники данных можно также настроить, щелкнув правой кнопкой мыши.  
  
 ![Окно "Источники данных"](../data-tools/media/raddata-data-sources-window.png "raddata окна \"Источники данных\"")  
  
 Для каждого типа данных, которое отображается в **источников данных** окна, элемент управления по умолчанию создается при перетаскивании элемента в конструктор. Прежде чем перетащить элемент из **источников данных** окно, можно изменить элемент управления, который будет создан. Дополнительные сведения см. в разделе [задать для элемента управления создается при перетаскивании из окна источников данных](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
## <a name="tasks-involved-in-binding-controls-to-data"></a>Задачи, решаемые в процессе привязки элементов управления к данным  
 В следующей таблице перечислены некоторые наиболее распространенные задачи необходимо выполнить для привязки элементов управления к данным.  
  
|Задача|Дополнительные сведения|  
|----------|----------------------|  
|Откройте **источников данных** окна.|Откройте рабочую область конструирования в редакторе и выберите **представление** > **источников данных**.|  
|Добавьте источник данных в проект.|[Добавление новых источников данных](../data-tools/add-new-data-sources.md)|  
|Задать элемент управления, который создается при перетаскивании элемента из **источников данных** окно в конструктор.|[Задание поведения, при котором элемент управления создается при перетаскивании из окна "Источники данных"](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)|  
|Измените список элементов управления, которые связаны с элементами в **источников данных** окна.|[Добавление пользовательских элементов управления в окно "Источники данных"](../data-tools/add-custom-controls-to-the-data-sources-window.md)|  
|Создайте элементы управления с привязкой к данным|[Привязка элементов управления Windows Forms к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)<br /><br /> [Привязка элементов управления WPF к данным в Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)|  
|Привязать к объекту или коллекции.|[Привязка объектов в Visual Studio](../data-tools/bind-objects-in-visual-studio.md)|  
|Фильтруйте данные, отображаемые в пользовательском Интерфейсе.|[Фильтрация и сортировка данных в приложении Windows Forms](../data-tools/filter-and-sort-data-in-a-windows-forms-application.md)|  
|Настройте заголовки для элементов управления.|[Настройка способа создания подписи для элемента управления с привязкой к данным в Visual Studio](../data-tools/customize-how-visual-studio-creates-captions-for-data-bound-controls.md)|  
  
## <a name="see-also"></a>См. также  
 [Visual Studio Data Tools для .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)   
 [Привязка данных Windows Forms](http://msdn.microsoft.com/library/c3826d8e-ea25-4ad4-a669-45bfb19192aa)

