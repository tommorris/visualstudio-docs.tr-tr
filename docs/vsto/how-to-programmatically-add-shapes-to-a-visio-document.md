---
title: 'Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 32fc1b61505711cbcf353819372bcd1452bf3716
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256675"
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme
  Bir şablon asıl alma ve etkin sayfada şekilleri bırakarak Microsoft Office Visio belgesine şekiller ekleyebilirsiniz.  
  
 Daha fazla bilgi için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) yöntemi, [Microsoft.Office.Interop.Visio.Application.ActivePage](http://msdn.microsoft.com/library/office/ff765484.aspx) özelliği ve [Microsoft.Office.Interop.Visio.Page.Drop](http://msdn.microsoft.com/library/office/ff765054.aspx) yöntemi.  
  
## <a name="add-shapes-to-a-visio-document"></a>Bir Visio belgesine şekilleri ekleme  
  
### <a name="to-add-shapes-to-a-visio-document"></a>Visio belgesine şekilleri ekleme  
  
-   Belge etkinken, asıl Documents.Masters koleksiyonundan almak ve şekiller etkin belgede bırakın. Dizin veya ana ad kullanarak bir ana alabilirsiniz.  
  
     Aşağıdaki kod örneğinde boş bir Visio belgesi oluşturur ve onunla açılır **temel şekillerin** kalıbı yuvalanmış. Kod birkaç şekiller alır ve bunları etkin sayfada bırakır.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)   
 [Nasıl yapılır: program aracılığıyla kopyalayıp Visio belgelerinde şekilleri yapıştırın](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  