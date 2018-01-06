---
title: "Nasıl yapılır: belgelerde metne program aracılığıyla açıklamaları ekleme | Microsoft Docs"
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
- comments, adding to documents
- documents [Office development in Visual Studio], adding comments
ms.assetid: 4e396e31-01bf-424c-be6b-9a1806bcd572
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 69f320ef3e7b3914d9d6eadb7466b3a216ef95d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-comments-to-text-in-documents"></a>Nasıl yapılır: Belgelerde Metne Program Aracılığıyla Açıklama Ekleme
  Belge sınıfı açıklamaları özelliğinin bir Microsoft Office Word belgesinde metin aralığı için bir açıklama ekler.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Aşağıdaki örnek belgede ilk paragrafa bir açıklama ekler.  
  
### <a name="to-add-a-new-comment-to-text-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde metin yeni bir açıklama eklemek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> yöntemi <xref:Microsoft.Office.Tools.Word.Document.Comments%2A> özelliği ve aralığı ve açıklama metni girin. Aşağıdaki kod örneğini kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#118](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#118)]
     [!code-csharp[Trin_VstcoreWordAutomation#118](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#118)]  
  
### <a name="to-add-a-new-comment-to-text-in-an-vsto-add-in"></a>Bir VSTO eklenti metinde yeni bir açıklama eklemek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Word._Document.Comments%2A> özelliği ve aralığı ve açıklama metni girin.  
  
     Aşağıdaki kod örneğinde etkin belge için bir açıklama ekler. Bu örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#118](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#118)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#118](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#118)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Word açıklamalara eklediği kullanıcı baş harflerini değiştirmek için kullanın <xref:Microsoft.Office.Interop.Word._Application.UserInitials%2A> özelliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: belgelerden tüm açıklamaları program aracılığıyla kaldırma](../vsto/how-to-programmatically-remove-all-comments-from-documents.md)   
 [Belge Konak Öğesi](../vsto/document-host-item.md)  
  
  