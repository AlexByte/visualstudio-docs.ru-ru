---
title: Модель автоматизации для объектов конфигурации и SelectedItem | Документация Майкрософт
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
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 612916da7922900a1054d785dad86ed448aa1f12
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733473"
---
# <a name="automation-for-configuration-and-selecteditem-objects"></a>Автоматизация для объектов конфигурации и SelectedItem
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Можно автоматизировать сборки и процессы выбранного элемента в [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="automation-for-builds"></a>Автоматизация сборки  
 Сборки или конфигурации имеет модель автоматизации, которая предоставляется при реализации <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider>. Дополнительные сведения см. в разделе [Общие сведения о конфигурациях построения](../../ide/understanding-build-configurations.md).  
  
 Если вы создаете VSPackage и хотите контролировать параметры конфигурации, необходимо использовать модель автоматизации.  
  
## <a name="automation-for-selecteditem"></a>Модель автоматизации для SelectedItem  
 Необходимо обеспечить реализацию для `SelectedItem` объекта, так как Visual Studio содержит стандартную реализацию. Тем не менее, можно реализовать `SelectedItem` объекта, если вы предпочитаете. Необходимо реализовать объект, содержащий `SelectedItem` интерфейс и возврат ответа на вызов <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> метод с VSITEMID <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>   
 [Дополнение к модели автоматизации](../../extensibility/internals/contributing-to-the-automation-model.md)   
 [Общие сведения о конфигурациях построения](../../ide/understanding-build-configurations.md)

