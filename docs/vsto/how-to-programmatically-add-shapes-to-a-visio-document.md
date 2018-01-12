---
title: "Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4d73c59ac9ba89a5814a264bb8e8fe3c83b9789e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
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
  
  