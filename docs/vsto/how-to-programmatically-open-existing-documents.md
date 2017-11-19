---
title: "Nasıl yapılır: varolan belgeleri program aracılığıyla açma | Microsoft Docs"
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
- documents [Office development in Visual Studio], opening
- Word [Office development in Visual Studio], opening documents
ms.assetid: 08f7fe4b-d96d-4a0c-b32a-aa7fd7992316
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 528245e33f3157bf42f70b3918ee9f8fc9539f9a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-open-existing-documents"></a>Nasıl yapılır: Varolan Belgeleri Program Aracılığıyla Açma
  <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> Yöntemi bir tam yol ve dosya adıyla belirtilen var olan Microsoft Office Word belgesini açar. Bu yöntem bir <xref:Microsoft.Office.Interop.Word.Document> açılan belgeyi temsil eden.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-open-a-document"></a>Bir belgeyi açmak için  
  
-   Çağrı <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Documents> koleksiyon ve belge yolunu belirtin.  
  
     [!code-vb[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#5)]  
  
### <a name="to-open-a-document-as-read-only"></a>Bir belgeyi salt okunur olarak açmak için  
  
-   Çağrı <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> yöntemi, belge için bir yol sağlayın ve ayarlama *ReadOnly* bağımsız değişkeni **True** yöntemini çağırın.  
  
     [!code-vb[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#6)]
     [!code-csharp[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#6)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği için şunlar gerekir:  
  
-   NewDocument.doc isimli bir belge c sürücüsünde Test adlı bir dizinde olması gerekir  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla yeni belgeler oluşturma](../vsto/how-to-programmatically-create-new-documents.md)   
 [Nasıl yapılır: program aracılığıyla belgeleri kapatma](../vsto/how-to-programmatically-close-documents.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  