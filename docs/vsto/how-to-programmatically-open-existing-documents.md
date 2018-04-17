---
title: 'Nasıl yapılır: varolan belgeleri program aracılığıyla açma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening
- Word [Office development in Visual Studio], opening documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0c7542b2222839afc75b3b5b1b84fc5afe56f523
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  