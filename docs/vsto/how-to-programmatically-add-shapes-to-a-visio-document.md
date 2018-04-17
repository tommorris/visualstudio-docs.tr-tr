---
title: 'Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme | Microsoft Docs'
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
ms.openlocfilehash: 1cc4369977e1989960fe9448d4dd7d56e67ed7a9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Nasıl yapılır: Visio Belgesine Program Aracılığıyla Şekiller Ekleme
  Bir şablon asıl alma ve etkin sayfada şekilleri bırakarak Microsoft Office Visio belgesine şekiller ekleyebilirsiniz.  
  
 Daha fazla bilgi için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) yöntemi, [Microsoft.Office.Interop.Visio.Application.ActivePage](http://msdn.microsoft.com/library/office/ff765484.aspx) özelliği ve [Microsoft.Office.Interop.Visio.Page.Drop](http://msdn.microsoft.com/library/office/ff765054.aspx) yöntemi.  
  
## <a name="adding-shapes-to-a-visio-document"></a>Visio belgesine şekilleri ekleme  
  
#### <a name="to-add-shapes-to-a-visio-document"></a>Visio belgesine şekilleri ekleme  
  
-   Belge etkinken, asıl Documents.Masters koleksiyonundan almak ve şekiller etkin belgede bırakın. Dizin veya ana ad kullanarak bir ana alabilirsiniz.  
  
     Aşağıdaki kod örneğinde boş bir Visio belgesi oluşturur ve onunla açılır **temel şekillerin** kalıbı yuvalanmış. Kod birkaç şekiller alır ve bunları etkin sayfada bırakır.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)   
 [Nasıl yapılır: Visio Belgelerinde Program Aracılığıyla Şekilleri Kopyalama ve Yapıştırma](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  