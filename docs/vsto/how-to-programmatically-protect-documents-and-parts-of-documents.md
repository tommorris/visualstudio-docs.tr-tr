---
title: "Nasıl yapılır: program aracılığıyla belgeleri ve belge parçalarını koruma | Microsoft Docs"
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
- document protection
- documents [Office development in Visual Studio], document protection
- Word documents, protection
ms.assetid: af8390fc-c4c7-48c7-94b8-4fedbaac0757
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2d37fc65a094aa3f6733045ca6ba9380bc522741
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-protect-documents-and-parts-of-documents"></a>Nasıl yapılır: Program Aracılığıyla Belgeleri ve Belge Parçalarını Koruma
  Kullanıcılar belgeye düzenlemeler yapmasını önlemek için Microsoft Office Word belgelerini koruma ekleyebilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Belirtilen kullanıcılar yalnızca belgenin alanları düzenleyebilmeleri, belgenin belirli alanları özel durumlar olarak işaretleyebilirsiniz. Örneğin, belirli bir yer işareti dışında tüm belgeyi korumak isteyebilirsiniz. Böylece parolayı bilmiyorsanız kullanıcılar belge koruması kaldırılamıyor, isteğe bağlı olarak bir parola ekleyebilirsiniz.  
  
> [!NOTE]  
>  Aşağıdaki örnek, parola koruması kullanmaz; Ancak, bir parola belge koruması eklerken kullanmayı isteyebilirsiniz. Daha fazla bilgi için belge koruyucu örneğine bakın [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
 İçerik denetimleri, belge parçalarını korumak için de kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: koruma bölümleri belgeler içerik denetimlerini kullanarak tarafından](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md).  
  
## <a name="protecting-a-document-that-is-part-of-a-document-level-customization"></a>Belge düzeyi özelleştirme parçası olan bir belgeyi koruma  
  
#### <a name="to-protect-a-document-that-is-part-of-a-document-level-customization"></a>Belge düzeyi özelleştirme parçası olan bir belgeyi korumak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.Protect%2A> yöntemi `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#111)]
     [!code-csharp[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#111)]  
  
#### <a name="to-exclude-a-bookmark-control-from-document-protection"></a>Bir yer işareti denetimi belge korumadan dışlamak için  
  
1.  Kullanarak tüm belgeyi koruyun <xref:Microsoft.Office.Tools.Word.Document.Protect%2A> yöntemi.  
  
     [!code-vb[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#111)]
     [!code-csharp[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#111)]  
  
2.  Dışlama `Bookmark1` belge koruması.  
  
     [!code-vb[Trin_VstcoreWordAutomation#112](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#112)]
     [!code-csharp[Trin_VstcoreWordAutomation#112](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#112)]  
  
### <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örnekleri kullanmak için bunları çalıştırmak `ThisDocument` projenizdeki sınıfı. Bu kod örnekleri, varsayılır <xref:Microsoft.Office.Tools.Word.Bookmark> adlı Denetim `Bookmark1` bu kodu göründüğü belge üzerinde.  
  
## <a name="protecting-a-document-by-using-an-vsto-add-in"></a>Bir VSTO eklentisinin kullanarak belgeyi koruma  
  
#### <a name="to-protect-a-document-by-using-an-application-level-vsto-add-in"></a>Uygulama düzeyi VSTO eklenti kullanarak bir belgeyi korumak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.Protect%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> korumak istediğiniz.  
  
     Aşağıdaki kod örneğinde etkin belgeyi korur. Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#111](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#111)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#111](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#111)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge düzeyi çözümlerde belge koruması](../vsto/document-protection-in-document-level-solutions.md)   
 [Office belgelerinde parola koruması](../vsto/password-protection-on-office-documents.md)   
 [Nasıl yapılır: kodun kısıtlı izinle belgelerin arkasında çalışmasına izin verme](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Office Çözümleri Tasarlama ve Oluşturma](../vsto/designing-and-creating-office-solutions.md)  
  
  