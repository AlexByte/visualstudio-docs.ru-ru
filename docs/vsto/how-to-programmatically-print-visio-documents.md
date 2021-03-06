---
title: Как выполнить Программная печать документов Visio
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], printing Visio documents
- documents [Office development in Visual Studio], printing Visio documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2abcf439abfe240bace83ca7ecb88ef5b9940944
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54872486"
---
# <a name="how-to-programmatically-print-visio-documents"></a>Как выполнить Программная печать документов Visio
  Можно напечатать полный документ Microsoft Office Visio или только определенную страницу.  
  
 Подробные сведения о методах печати см. в справочной документации VBA для метода [Microsoft.Office.Interop.Visio.Document.Print](/office/vba/api/Visio.Document.Print) и метода [Microsoft.Office.Interop.Visio.Page.Print](/office/vba/api/Visio.Page.Print) .  
  
## <a name="print-a-visio-document"></a>Печать документа Visio  
  
### <a name="to-print-a-complete-document"></a>Печать всего документа  
  
-   Вызовите метод `Microsoft.Office.Interop.Visio.Document.Print` документа `Microsoft.Office.Interop.Visio.Document` , который требуется напечатать.  
  
     В следующем примере кода печатается активный документ. Чтобы использовать этот пример, запустите код из класса `ThisAddIn` в своем проекте.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#8)]  
  
## <a name="print-a-page-of-a-visio-document"></a>Печать страницы документа Visio  
  
### <a name="to-print-a-page-of-a-document"></a>Печать страницы документа  
  
-   Вызовите метод `Microsoft.Office.Interop.Visio.Pages.Print` документа `Microsoft.Office.Interop.Visio.Pages` , который требуется напечатать.  
  
     В следующем примере кода печатается первая страница активного документа. Чтобы использовать этот пример, запустите код из класса `ThisAddIn` в своем проекте.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>См. также  
 [Решения Visio](../vsto/visio-solutions.md)   
 [Обзор объектной модели Visio](../vsto/visio-object-model-overview.md)   
 [Практическое руководство. Программное создание документов Visio](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Практическое руководство. Открытие документов Visio](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Практическое руководство. Программное закрытие документов Visio](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Практическое руководство. Программное сохранение документов Visio](../vsto/how-to-programmatically-save-visio-documents.md)  
