---
title: "Nasıl yapılır: program aracılığıyla belgeleri kapatma | Microsoft Docs"
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
- documents [Office development in Visual Studio], closing
- Word [Office development in Visual Studio], closing documents
ms.assetid: d5bee1dc-63d1-4307-828f-b7b077e20fb9
caps.latest.revision: "55"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0cc6b310e0c376afb7e0e9a7ade5b91cb4bbb77d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-close-documents"></a>Nasıl yapılır: Program Aracılığıyla Belgeleri Kapatma
  Etkin belgeyi Kapat veya kapatmak için bir belge belirtebilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="closing-the-active-document"></a>Etkin belgeyi kapatma  
 Etkin belgeyi kapatmak için iki yordam vardır: biri belge düzeyi özelleştirmeleri ve biri VSTO eklentileri için.  
  
#### <a name="to-close-the-active-document-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde etkin belgeyi kapatmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.Close%2A> yöntemi `ThisDocument` özelleştirme ile ilişkilendirilmiş belgeyi kapatmak için projenizdeki sınıfı. Aşağıdaki kod örneğini kullanmak için çalıştırın `ThisDocument` sınıfı.  
  
    > [!NOTE]  
    >  Bu örnek geçirir <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> değeri *SaveChanges* parametresi değişiklikleri kaydetmeden veya kullanıcıdan kapatın.  
  
     [!code-vb[Trin_VstcoreWordAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#3)]
     [!code-csharp[Trin_VstcoreWordAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#3)]  
  
#### <a name="to-close-the-active-document-in-a-vsto-add-in"></a>Bir VSTO eklenti etkin belgede kapatmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.Close%2A> yöntemi <xref:Microsoft.Office.Interop.Word._Application.ActiveDocument%2A> özelliği etkin belgeyi kapat. Aşağıdaki kod örneğini kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
    > [!NOTE]  
    >  Bu örnek geçirir <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> değeri *SaveChanges* parametresi değişiklikleri kaydetmeden veya kullanıcıdan kapatın.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#3)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#3](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#3)]  
  
## <a name="closing-a-document-that-you-specify-by-name"></a>Belirttiğiniz bir belgeyi ada göre kapatma  
 Ada göre belirttiğiniz bir belgeyi Kapat şekilde VSTO eklentileri ve belge düzeyi özelleştirmeleri ile aynıdır.  
  
#### <a name="to-close-a-document-that-you-specify-by-name"></a>Ada göre belirttiğiniz bir belgeyi kapatmak için  
  
1.  Bağımsız değişken olarak belge adı belirtin <xref:Microsoft.Office.Interop.Word._Application.Documents%2A> koleksiyonu ve ardından arama <xref:Microsoft.Office.Interop.Word._Document.Close%2A> yöntemi. Aşağıdaki kod örneği bir belge adlı varsayar **NewDocument** Word'de açıktır.  
  
    > [!NOTE]  
    >  Bu örnek geçirir <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> değeri *SaveChanges* parametresi değişiklikleri kaydetmeden veya kullanıcıdan kapatın.  
  
     [!code-vb[Trin_VstcoreWordAutomation#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#4)]
     [!code-csharp[Trin_VstcoreWordAutomation#4](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#4)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: varolan belgeleri program aracılığıyla açma](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Nasıl yapılır: program aracılığıyla belgeleri kaydetme](../vsto/how-to-programmatically-save-documents.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  