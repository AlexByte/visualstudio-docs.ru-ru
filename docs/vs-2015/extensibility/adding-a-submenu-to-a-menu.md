---
title: Добавление подменю в меню | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- context menus
- submenus, cascading
- cascading submenus
- menus, creating cascading submenus
ms.assetid: 692600cb-d052-40e2-bdae-4354ae7c6c84
caps.latest.revision: 44
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 14ad9d2daf603dd2ca80a784251f19503fee1cba
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51738319"
---
# <a name="adding-a-submenu-to-a-menu"></a>Добавление подменю в меню
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Это пошаговое руководство построено на демонстрацию в [добавлению меню в строке меню Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) , показывая, как добавить подменю в **TestMenu** меню.  
  
 Подменю является вторичной меню, которое отображается в другом меню. Подменю можно идентифицировать по стрелке, которая следует за его имя. Если щелкнуть имя вызывает подменю и соответствующие команды для отображения.  
  
 В этом пошаговом руководстве создается подменю в меню в строке меню Visual Studio и помещает новую команду в подменю. Пошаговое руководство также реализует новой команды.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Начиная с Visual Studio 2015, не следует устанавливать пакет SDK для Visual Studio из центра загрузки. Она будет включена в качестве дополнительного компонента в программе установки Visual Studio. VS SDK также можно установить позже. Дополнительные сведения см. в разделе [установка Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="adding-a-submenu-to-a-menu"></a>Добавление подменю в меню  
  
1.  Выполните действия, описанные в [добавлению меню в строке меню Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) Создание элемента проекта и меню. В этом пошаговом руководстве предполагается, что имя проекта VSIX — `TopLevelMenu`.  
  
2.  Откройте TestCommandPackage.vsct. В `<Symbols>` добавьте `<IDSymbol>` элемент для подменю, один для подменю группы и одна для команды, все это в `<GuidSymbol>` узел с именем «guidTopLevelMenuCmdSet.» Это связано с тем же узел, содержащий `<IDSymbol>` элемент для меню верхнего уровня.  
  
    ```xml  
    <IDSymbol name="SubMenu" value="0x1100"/>  
    <IDSymbol name="SubMenuGroup" value="0x1150"/>  
    <IDSymbol name="cmdidTestSubCommand" value="0x0105"/>  
    ```  
  
3.  Добавление в только что созданный подменю для `<Menus>` раздел.  
  
    ```xml  
    <Menu guid="guidTestCommandPackageCmdSet" id="SubMenu" priority="0x0100" type="Menu">  
        <Parent guid="guidTestCommandPackageCmdSet" id="MyMenuGroup"/>  
        <Strings>  
            <ButtonText>Sub Menu</ButtonText>  
            <CommandName>Sub Menu</CommandName>  
        </Strings>  
    </Menu>  
    ```  
  
     Пара GUID и идентификатора родительского указывает группы меню, который был создан в [добавлению меню в строке меню Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md), и является дочерним элементом меню верхнего уровня.  
  
4.  Добавление группы меню, определенных на шаге 2, чтобы `<Groups>` раздела и сделайте его дочерним подменю.  
  
    ```xml  
    <Group guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" priority="0x0000">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenu"/>  
    </Group>  
    ```  
  
5.  Добавьте новый `<Button>` элемент `<Buttons>` разделе для определения команды, созданный на шаге 2, как элемент подменю.  
  
    ```xml  
    <Button guid="guidTestCommandPackageCmdSet" id="cmdidTestSubCommand" priority="0x0000" type="Button">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic2" />  
        <Strings>  
           <CommandName>cmdidTestSubCommand</CommandName>  
           <ButtonText>Test Sub Command</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
6.  Постройте решение и запустите отладку. Вы должны увидеть экспериментальный экземпляр.  
  
7.  Нажмите кнопку **TestMenu** для просмотра с именем подменю **подменю**. Нажмите кнопку **подменю** откройте подменю и новой команды, см. в разделе **теста подкоманда**. Обратите внимание, что нажатие кнопки **теста подкоманда** не выполняет никаких действий.  
  
## <a name="adding-a-command"></a>Добавление команды  
  
1.  Откройте TestCommand.cs и добавьте следующий идентификатор команды после существующий идентификатор команды.  
  
    ```csharp  
    public const int cmdidTestSubCmd = 0x105;  
    ```  
  
2.  Добавление вложенной команды. Найти команду конструктора. Добавьте следующие строки сразу после вызова `AddCommand` метод.  
  
    ```csharp  
    CommandID subCommandID = new CommandID(CommandSet, (int)TestCommandPackageGuids.cmdidTestSubCmd);  
    MenuCommand subItem = new MenuCommand(  
        new EventHandler(SubItemCallback), subCommandID);  
    commandService.AddCommand(subItem);  
  
    ```  
  
     `SubItemCallback` Обработчик команд будут определены в дальнейшем. Конструктор теперь должен выглядеть следующим образом:  
  
    ```csharp  
    private TestCommand(Package package)  
            {  
                if (package == null)  
                {  
                    throw new ArgumentNullException("package");  
                }  
  
                this.package = package;  
  
                OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
                if (commandService != null)  
                {  
                    var menuCommandID = new CommandID(CommandSet, CommandId);  
                    var menuItem = new MenuCommand(this.MenuItemCallback, menuCommandID);  
                    commandService.AddCommand(menuItem);  
                    CommandID subCommandID = new CommandID(CommandSet, cmdidTestSubCmd);  
                    MenuCommand subItem = new MenuCommand(  
                        new EventHandler(SubItemCallback), subCommandID);  
                    commandService.AddCommand(subItem);  
                }  
    ```  
  
3.  Добавьте SubItemCallback(). Это метод, который вызывается при нажатии новой команды в подменю.  
  
    ```csharp  
    private void SubItemCallback(object sender, EventArgs e)  
    {  
        IVsUIShell uiShell = (IVsUIShell)this.ServiceProvider.GetService(  
            typeof(SVsUIShell));  
        Guid clsid = Guid.Empty;  
        int result;  
        uiShell.ShowMessageBox(  
            0,  
            ref clsid,  
            "TestCommand",  
            string.Format(CultureInfo.CurrentCulture,  
            "Inside TestCommand.SubItemCallback()",  
            this.ToString()),  
            string.Empty,  
            0,  
            OLEMSGBUTTON.OLEMSGBUTTON_OK,  
            OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
            OLEMSGICON.OLEMSGICON_INFO,  
            0,  
            out result);  
    }  
    ```  
  
4.  Выполните сборку решения и запустите отладку. Откроется экспериментальный экземпляр.  
  
5.  На **TestMenu** меню, щелкните **подменю** и нажмите кнопку **теста подкоманда**. Появится окно сообщения с отображения текста «Тестирования команду внутри TestCommand.SubItemCallback()».  
  
## <a name="see-also"></a>См. также  
 [Добавление меню в строке меню Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)   
 [Команды, меню и панели инструментов](../extensibility/internals/commands-menus-and-toolbars.md)

