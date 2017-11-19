---
title: "Nasıl yapılır: program aracılığıyla belgeleri yazdırma | Microsoft Docs"
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
- Word [Office development in Visual Studio], printing documents
- documents [Office development in Visual Studio], printing
ms.assetid: 99285d98-1bb7-4ccb-83d9-e917b0a9ea42
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9e967ae840486126f5f5fb457e2b1ef8eda57881
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-print-documents"></a>Nasıl yapılır: Program Aracılığıyla Belgeleri Yazdırma
  Tüm yazdırma Microsoft Office Word belgesine veya varsayılan yazıcı için bir belge bölümü.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="printing-a-document-that-is-part-of-a-document-level-customization"></a>Belge düzeyi özelleştirme parçası olan belge yazdırma  
  
#### <a name="to-print-the-entire-document"></a>Tüm belgeyi yazdırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> yöntemi `ThisDocument` tüm belgeyi yazdırmak için projenizdeki sınıfı. Bu örneği kullanmak için kodu çalıştırın `ThisDocument` sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#11)]  
  
#### <a name="to-print-the-current-page-of-the-document"></a>Belge geçerli sayfa yazdırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> yöntemi `ThisDocument` sınıf projenizde ve geçerli sayfanın bir kopyasını yazdırılması gerektiğini belirtin. Bu örneği kullanmak için kodu çalıştırın `ThisDocument` sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#12)]  
  
## <a name="printing-a-document-by-using-an-vsto-add-in"></a>Bir VSTO eklentisinin kullanarak belge yazdırma  
  
#### <a name="to-print-an-entire-document"></a>Belgenin tümünü yazdırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> yazdırmak istediğiniz nesne. Aşağıdaki kod örneğinde etkin belgeyi yazdırır. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#11)]  
  
#### <a name="to-print-the-current-page-of-a-document"></a>Bir belge geçerli sayfa yazdırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> yazdırma ve geçerli sayfanın bir kopyasını yazdırılması gerektiğini belirtmek için istediğiniz nesne. Aşağıdaki kod örneğinde etkin belgeyi yazdırır. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#12)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  