---
title: Как выполнить Изменение конфигурации развертывания SharePoint | Документация Майкрософт
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.DeploymentConfig
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 98cdc452663fd32508496c1fc52a49033a0b4381
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870065"
---
# <a name="how-to-edit-a-sharepoint-deployment-configuration"></a>Как выполнить Изменение конфигурации развертывания SharePoint
  Можно создать конфигурацию развертывания или изменить существующую конфигурацию развертывания. Например можно выполнить за один шаг или изменить порядок действий, описанных в процесс развертывания. Вы можете для создания или изменения конфигураций развертывания, поскольку невозможно изменить конфигурации встроенные и добавленные программным способом.  
  
## <a name="create-a-sharepoint-deployment-configuration"></a>Создание конфигурации развертывания SharePoint  
  
#### <a name="to-create-a-sharepoint-deployment-configuration"></a>Для создания конфигурации развертывания SharePoint  
  
1.  В **обозревателе решений**, выберите проект SharePoint и затем в строке меню выберите **проекта**, _имя_проекта_**свойства**.  
  
2.  На **SharePoint** вкладке, выберите **New** кнопки.  
  
     **Добавьте новую конфигурацию развертывания** откроется диалоговое окно.  
  
3.  В **имя** текстовое поле, введите имя конфигурации развертывания.  
  
4.  В **действия при развертывании** панели выберите шаги, которые вы хотите добавить в конфигурацию развертывания, щелкните (**>**), а затем **ОК** кнопки.  
  
    > [!NOTE]  
    >  Если вы настроили команды до развертывания или команды после развертывания, эти шаги выполняются только в том случае, если добавить их в пользовательскую конфигурацию развертывания.  
  
## <a name="change-the-active-deployment-configuration"></a>Измените активную конфигурацию развертывания  
  
#### <a name="to-change-the-active-deployment-configuration"></a>Чтобы изменить активную конфигурацию развертывания  
  
1.  В **обозревателе решений**, выберите проект SharePoint и затем в строке меню выберите **проекта** > **\<*имя_проекта*> Свойства**.  
  
2.  Выберите **SharePoint** вкладки.  
  
3.  В **активная конфигурация развертывания** раскрывающегося списка, выберите имя конфигурации развертывания, который вы хотите использовать.  
  
## <a name="see-also"></a>См. также
 [Упаковка и развертывание решений SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
