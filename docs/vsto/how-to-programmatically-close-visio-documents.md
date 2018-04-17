---
title: 'Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma | Microsoft Docs'
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
ms.openlocfilehash: 314d8e5bfd40e1e45d4795a6e4523db19124741a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-close-visio-documents"></a>Nasıl yapılır: Visio Belgelerini Program Aracılığıyla Kapatma
  Etkin Microsoft Office Visio belgesini Microsoft.Office.Interop.Visio.Document.Close metodunu kullanarak kapatabilirsiniz.  
  
 Bu yöntem hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Document.Close](http://msdn.microsoft.com/library/office/ff767415.aspx) yöntemi.  
  
## <a name="closing-the-active-document"></a>Etkin belgeyi kapatma  
  
#### <a name="to-close-the-active-document"></a>Etkin belgeyi kapatmak için  
  
-   Etkin belgeyi Kapat için Microsoft.Office.Interop.Visio.Document.Close yöntemini çağırın.  
  
     Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisAddIn` Visio için VSTO eklenti projesindeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini açma](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Yazdırma](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  