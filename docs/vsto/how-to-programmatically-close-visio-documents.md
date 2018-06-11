---
title: 'Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], closing Visio documents
- Visio [Office development in Visual Studio], closing Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 153c9c3e32252f21dafd5b2d6bd6eb8ec1752161
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257871"
---
# <a name="how-to-programmatically-close-visio-documents"></a>Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma
  Etkin Microsoft Office Visio belgesini kullanarak kapatabilirsiniz `Microsoft.Office.Interop.Visio.Document.Close` yöntemi.  
  
 Bu yöntem hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Document.Close](http://msdn.microsoft.com/library/office/ff767415.aspx) yöntemi.  
  
## <a name="close-the-active-document"></a>Etkin belgeyi Kapat  
  
### <a name="to-close-the-active-document"></a>Etkin belgeyi kapatmak için  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Document.Close` yöntemi etkin belgeyi kapat.  
  
     Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisAddIn` Visio için VSTO eklenti projesindeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini açma](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini yazdırma](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  