---
title: Добавление веб-служб в системы проектов | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project systems, adding Web services
- Web services, adding to VSPackage project systems
ms.assetid: 8efa078b-68b2-45a2-9be2-44f807bc0d7f
caps.latest.revision: 8
manager: douge
ms.openlocfilehash: 88966ee17567970d0807792c57c2483cadb22f63
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49280323"
---
# <a name="adding-web-services-to-project-systems"></a>Добавление веб-служб в системы проектов
Веб-служб XML, как правило, URL-адрес-ресурсы, которые возвращают программные данные в систему проекта, с помощью протокола SOAP (Simple Object Access Protocol). Веб-службы можно интегрировать в систему проектов VSPackage с помощью <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddProjectItemDlg2> интерфейс.  
  
### <a name="to-add-a-web-service-to-your-project-system"></a>Чтобы добавить веб-службы в систему проекта  
  
1.  Вызовите `QueryService` для <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddProjectItemDlg2> интерфейс, с помощью <xref:Microsoft.VisualStudio.Shell.Interop.SVsAddWebReferenceDlg> службы.  
  
2.  Вызовите метод <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2.AddWebReferenceDlg%2A>. Если передать `pDiscoverySession` параметра в виде `NULL`, создается сеанс обнаружения и сеанс кэшируется, чтобы он был доступен для последующего использования, <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2> интерфейс. <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2.AddWebReferenceDlg%2A> метод возвращает указатель на <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoveryResult2>.  
  
3.  Вызовите метод <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoveryResult.AddWebReference%2A>. Передайте объект автоматизации для папки веб-службы ссылок как `pUnkWebReferenceFolder` параметр. Среда Visual Studio проверит, если веб-службы уже существует. Если веб-службы отсутствует, среде загружает и добавляет веб-службы для папки и всех дополнительных файлов (например, WSDL-файлы), к дочерним узлам папки.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoveryResult>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoverySession>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDiscoveryService>