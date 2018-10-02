---
title: Макет для Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c19e3022-047c-43b6-a046-a82717efed4f
caps.latest.revision: 3
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 25ba43a08bc2c886302894d891800ac1db87a18a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47563297"
---
# <a name="layout-for-visual-studio"></a>Макет для Visual Studio
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [макет для Visual Studio](https://docs.microsoft.com/visualstudio/extensibility/ux-guidelines/layout-for-visual-studio).  
  
Большинство диалоговых окон Visual Studio [макет диалогового окна программы](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_UtilityDialogLayout), которые представляют собой unthemed диалоговые окна этого стандарта выполните [принципы макет диалогового окна Windows Desktop](https://msdn.microsoft.com/library/windows/desktop/dn742499\(v=vs.85\).aspx). При перемещении Visual Studio для обновления его пользовательского интерфейса, более наглядными диалоговые окна есть новый дизайн, который устанавливает их возможности, как определение продукта. Эти [тематический макет диалогового окна](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_ThemedDialogLayout) имеют вид темы.  
  
##  <a name="BKMK_UtilityDialogLayout"></a> Макет диалогового окна служебной программы  
  
-   Все элементы управления в диалоговое окно программы должно начинаться в левый верхний и поток вниз.  
  
-   Никогда не center элементов управления в диалоговое окно для заполнения большие области.  
  
-   Используйте шрифт среды для всего текста диалогового окна. При написании visual спецификации, укажите шрифт среды разработки вместо выбора конкретного шрифта и размера. См. в разделе [шрифта среды](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).  
  
-   Интервал согласованное управление и размещения для поддержки цели качества в мастерства.  
  
-   Диалоговые окна может быть затруднено из большого числа элементов управления и уникальный juxtaposition элементов управления. Для таких сложных случаев позволяют достаточно свободного места между группы управления для предоставления пользователю в логической последовательности для синтаксического анализа.  
  
### <a name="utility-dialog-layout-examples"></a>Примеры макет диалогового окна служебной программы  
 Все размеры выражаются в виде пикселей.  
  
 ![Интервалы между диалоговыми окнами для меток над элементами управления](../../extensibility/ux-guidelines/media/0801-a-utilityspacingabove.png "0801 a_UtilitySpacingAbove")  
  
 **Рис 08.01-ответ Инструкции интервалы для диалоговых окон программы с помощью меток над элементами управления**  
  
 ![Интервалы между диалоговыми окнами для меток слева от элементов управления](../../extensibility/ux-guidelines/media/0801-b-utilityspacingleft.png "0801 b_UtilitySpacingLeft")  
  
 **Рис 08.01-b: Инструкции интервалы для диалоговых окон программы с метками слева от элементов управления**  
  
### <a name="layout-details"></a>Подробные сведения о макетах  
  
#### <a name="margins"></a>Поля  
  
-   Все диалоговые окна должны быть границы 12 пикселей на границе.  
  
-   Поля внутри рамки группы должно быть 9 пикселей от края рамки.  
  
-   Поля в элементе управления вкладка должен быть 6 пикселей от края элемента управления вкладки.  
  
#### <a name="command-buttons"></a>Кнопки команд  
  
-   Кнопки команд оперируют фрейм диалогового окна, не на содержимое. Они должны размещаться в нижней правой и должен иметь достаточно выше, чтобы установить кнопки обособленные пространство переменных.  
  
-   Если горизонтальные кнопки, которые работают в диалоговом окне, configuration кнопка альтернативный команда представляет собой вертикальной стек, в правом верхнем углу. См. в разделе [кнопки внутренних команд](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_InteriorCommandButtons) ниже.  
  
-   Пространство слева от кнопки команд (влево/центральной нижней части диалогового окна) считается частью «диапазон» элементы управления диалоговых окон операции. Единственное, что следует вторгаться в этой области представляет собой ссылку справки, которые относятся к общей задачи или диалоговое окно.  
  
-   Кнопки команд должны иметь 75 x 23.  
  
-   Кнопки команд должен быть 6 пикселей друг от друга.  
  
 ![Выравнивание основных кнопок](../../extensibility/ux-guidelines/media/0801-c-buttonalign.png "0801 c_ButtonAlign")  
  
 **Рис 08.01-c: Выравнивание основных кнопок**  
  
#### <a name="labels"></a>Подписи  
  
-   Выровнять по левому краю все метки.  
  
-   Для меток, которые расположены над элемент управления они должны по левому краю точно с элементом управления под ним и нижней метки должны быть 5 пикселов над верхней границей другого элемента управления (например, поле со списком).  
  
-   Для меток, расположенные слева от элементов управления минимальную ширину между элементами label и элемент управления для ввода — 10 пикселей. Для выравнивания текстовые поля, поля со списком или других элементов управления, нужно установить предполагаемого второго столбца.  
  
-   Метки — прописная и за которым следует двоеточие. См. в разделе [стиль текста](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).  
  
#### <a name="distance-between-controls"></a>Расстояние между элементами управления  
 Размещение элементов управления достаточно. Нет не абсолютный Ориентировочная расстояние между элементами управления с накоплением. Tightness между элементами управления могут незначительно различаться между диалоговые окна. Рекомендуемый интервал — 20 пикселей для пар метка/элемента управления по вертикали, а 9 пикселей по горизонтали метка пар. Интервалы минимальный элемент управления для пары "по горизонтали" — 6 пикселей.  
  
 ![Рекомендуемое расстояние между элементами управления](../../extensibility/ux-guidelines/media/0801-d-controldistance.png "0801 d_ControlDistance")  
  
 **Рис 08.01-d: Рекомендации для расстояния между элементами управления**  
  
#### <a name="control-indentation"></a>Отступ элемента управления  
 Если элементы управления являются вложенными, выравниваться внутренние элементы управления по горизонтали относительно левого края элемента управления выше, обычно метки.  
  
 ![Вложенные исправить выравнивание элемента управления](../../extensibility/ux-guidelines/media/0801-e-controlalign.png "0801 e_ControlAlign")  
  
 **Рис 08.01 — e: Выравнивание элемента управления Nested**  
  
#### <a name="control-width"></a>Ширина элемента управления  
 Ширина текстового поля или другие аналогичные элементы управления не должен превышать среднее входных данных для поля. Среднее английского слова составляет 5 символов. Например, текстовое поле, которое требуется длинным именем пути должно быть условии, что позволяет горизонтальном расположении, хотя раскрывающийся список, для имен платформ, следует только, длина которых позволяет самая длинная запись.  
  
#### <a name="helper-text"></a>Текст подсказки  
  
-   Диалоговое окно можно отобразить текст подсказки, предоставляющий дополнительные сведения о назначении диалогового окна. Это обычно расположена в верхней и может быть предложения 1 – 2.  
  
-   Длина строки должна быть уверенно ширины для пользователя для синтаксического анализа и чтения. Средний диалоговое окно должно быть не более чем 550 пикселей в ширину.  
  
####  <a name="BKMK_InteriorCommandButtons"></a> Кнопки внутренних команд  
 В более сложных диалоговых окон внутреннего элемента управления может иметь свой собственный связанных кнопок, что может повлиять на, где находятся кнопки фиксации диалогового окна.  
  
-   Используйте вертикальное выравнивание (столбец) внутренней части кнопки **ОК**/**отменить** горизонтально располагается в нижнем правом углу.  
  
-   Используйте горизонтальное выравнивание (строка) внутренней части кнопки **ОК**/**отменить** ориентированы вертикально в правом верхнем углу. Эта ситуация менее типична.  
  
-   Размер внутренних кнопки должны быть нацелены на размер стандартной кнопки 75 x 23 пикселях соответствия размера **ОК**/**отменить** кнопки, когда это возможно. Если надпись на кнопке делает кнопку превышает размер стандартной кнопки, другие кнопки в этом наборе должны быть выровнены с широкого размера.  
  
 ![Кнопки по горизонтали OK и Отмена](../../extensibility/ux-guidelines/media/0801-f-horizokcan.png "0801 f_HorizOKCan")  
  
 **Рис 08.01-f: Вертикальной внутренней части кнопки с горизонтальной ОК, Отмена**  
  
 ![Кнопки на вертикальной OK и Отмена](../../extensibility/ux-guidelines/media/0801-g-vertokcan.png "0801 g_VertOKCan")  
  
 **Рис 08.01-g: Горизонтальные кнопки внутренних с вертикальной ОК, Отмена**  
  
#### <a name="browse-button"></a>[Обзор...] Кнопка  
 **[Обзор...]**  должна описывать кнопки, выполните текстовое поле «Обзор...» в полном объеме, включая кнопку с многоточием. Если не хватает места, или существует несколько **[Обзор...]**  кнопок на экране кнопки может быть сокращен до просто кнопку с многоточием.  
  
##  <a name="BKMK_ThemedDialogLayout"></a> Тематический макет диалогового окна  
 Тематические диалоговых окон в Visual Studio имеют вид, более светлый оттенок и предоставлять дополнительные пробелы. Оформление предоставляет дополнительные выделения сумму и проценты, предлагая более открытую междустрочный интервал и разновидность размеры шрифтов и значений веса. Если это возможно, chrome и строки состояния были ограниченной или удалены. Макет эти диалоговые окна должны следовать этому простому шаблону:  
  
1.  Фон окна будет белый.  
  
2.  Есть граница правило 1 пиксель серым цветом среднего значения.  
  
3.  Заголовок диалогового окна больше не находится в строке заголовка, но также предоставляет визуальные эффекты и выделения в большего размера точки. (См. в разделе размер шрифта в [стиль текста](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).)  
  
4.  В сочетании с дополнительным текстом, например, описание метки должны быть **шрифта среды + жирный**.  
  
5.  Внутренний столбцы разделяются правила 1 пиксель в светло-серый цвет.  
  
6.  Ссылки по умолчанию иметь без подчеркивания. При наведении указателя мыши и нажата состояния имеют изменение цвета, а также символ подчеркивания.  
  
7.  Зафиксировать кнопок (например **ОК**/**отменить**) расположен в правом нижнем углу.  
  
### <a name="themed-dialog-layout-examples"></a>Примеры макета тематические диалоговое окно  
 ![Тематический макет диалогового окна](../../extensibility/ux-guidelines/media/0801-h-themeddialog.png "0801 h_ThemedDialog")  
  
 **Рис 08.01-h: Диалоговое окно тематические**  
  
 ![Тематические размеры диалогового окна](../../extensibility/ux-guidelines/media/0801-i-themeddialogdimensions.png "0801 i_ThemedDialogDimensions")  
  
 **Рис 08.01-i: Тематические диалоговое окно — измерений**  
  
 ![Тематические шрифты диалогового окна](../../extensibility/ux-guidelines/media/0801-j-themeddialogfonts.png "0801 j_ThemedDialogFonts")  
  
 **Рис 08.01-j: Тематические диалоговое окно — шрифты**  
  
 ![Тематические цвета диалогового окна](../../extensibility/ux-guidelines/media/0801-k-themeddialogcolors.png "0801 k_ThemedDialogColors")  
  
 **Рис 08.01-k: Тематические диалоговое окно — цветов**  
  
## <a name="see-also"></a>См. также  
 [Шаблоны приложений для Visual Studio](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)   
 [Элементы управления (Windows)](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx)   
 [Диалоговые окна (Windows)](https://msdn.microsoft.com/library/windows/desktop/dn742499\(v=vs.85\).aspx)
