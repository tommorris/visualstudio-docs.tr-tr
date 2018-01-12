---
title: "Nasıl yapılır: program aracılığıyla yeni belgeler oluşturma | Microsoft Docs"
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
- templates [Office development in Visual Studio], custom document
- Word [Office development in Visual Studio], creating documents
- documents [Office development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 09e6f9e0e2bc6a001f6a2b67c733f11bfb725563
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-create-new-documents"></a>Nasıl yapılır: Program Aracılığıyla Yeni Belgeler Oluşturma
  Bir belge programlı olarak oluşturduğunuzda, bir yerel yeni belgedir <xref:Microsoft.Office.Interop.Word.Document> nesnesi. Bu nesne ek olaylar ve veri bağlama yeteneklerine sahip değil bir <xref:Microsoft.Office.Tools.Word.Document> konak öğesi. Daha fazla bilgi için bkz: [programsal sınırlamalar, ana bilgisayar öğeleri ve ana bilgisayar denetimleri](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Belge düzeyi projesi geliştirdiğinizde, programlı olarak ekleyemezsiniz <xref:Microsoft.Office.Tools.Word.Document> konak öğelerini projenize. Herhangi bir dönüştürme bir VSTO eklenti projesinde <xref:Microsoft.Office.Interop.Word.Document> nesnesine bir <xref:Microsoft.Office.Tools.Word.Document> çalışma zamanında konak öğesi. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="to-create-a-new-document-based-on-the-normal-template"></a>Normal şablona dayalı yeni bir belge oluşturmak için  
  
-   Kullanım <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Documents> koleksiyonu yeni bir belge oluşturmak için Normal şablona dayalı. Bu kod örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#1)]
     [!code-csharp[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#1)]  
  
## <a name="using-custom-templates"></a>Özel şablonlar kullanma  
 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> Yöntemi sahip isteğe bağlı bir *şablonu* Normal şablon dışında bir şablonu temel değişkenini kullanarak bir yeni belge oluşturun. Şablonun tam yolunu ve dosya adı girmeniz gerekir.  
  
#### <a name="to-create-a-new-document-based-on-a-custom-template"></a>Özel bir şablonu temel alan yeni bir belge oluşturmak için  
  
-   Çağrı <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Documents> koleksiyonu ve şablonun yolunu belirtin. Bu kod örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#2)]
     [!code-csharp[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: varolan belgeleri program aracılığıyla açma](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  