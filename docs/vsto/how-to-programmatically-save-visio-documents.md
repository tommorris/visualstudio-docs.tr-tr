---
title: "Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme | Microsoft Docs"
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
- documents [Office development in Visual Studio], saving Visio documents
- Visio [Office development in Visual Studio], saving Visio documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c255c481123ef4159d63ad87d9c8fa2ac97cbdae
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-save-visio-documents"></a>Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Kaydetme
  Microsoft Office Visio belgeleri kaydetmek için birkaç yolu vardır:  
  
-   Varolan bir belgedeki değişiklikleri kaydedin.  
  
-   Yeni bir belge kaydetme veya bir belgeyi yeni adla kaydet.  
  
-   Belirtilen bağımsız değişkenlerle bir belgeyi kaydedin.  
  
 Daha fazla bilgi için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Document.Save](https://msdn.microsoft.com/library/office/ff766478.aspx) yöntemi, [Microsoft.Office.Interop.Visio.Document.SaveAs](https://msdn.microsoft.com/library/office/ff765824.aspx) yöntemi ve [ Microsoft.Office.Interop.Visio.Document.SaveAsEx](https://msdn.microsoft.com/library/office/ff768149.aspx) yöntemi.  
  
## <a name="saving-an-existing-document"></a>Varolan bir belgeyi kaydetme  
  
#### <a name="to-save-a-document"></a>Bir belgeyi kaydetmek için  
  
-   Daha önce kaydedilmiş bir belgenin Microsoft.Office.Interop.Visio.Document.Save sınıfının yöntemini çağırın.  
  
     Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
    > [!NOTE]  
    >  Yeni bir Visio belgesi henüz kaydedilmedi olursa yöntemini bir özel durum oluşturur.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#11)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#11)]  
  
## <a name="saving-a-document-with-a-new-name"></a>Belgeye yeni bir adla kaydetme  
 Yeni bir belge veya yeni bir adı olan bir belgeyi kaydetmek için Microsoft.Office.Interop.Visio.Document.SaveAs yöntemini kullanın. Bu yöntem, yeni dosya adı belirtin gerektirir.  
  
#### <a name="to-save-the-active-visio-document-with-a-new-name"></a>Yeni bir adla etkin Visio belgesini kaydetmek için  
  
-   Dosya adını içeren tam bir yol kullanarak kaydetmek istediğiniz Microsoft.Office.Interop.Visio.Document.SaveAsEx Microsoft.Office.Interop.Visio.Document.SaveAs yöntemini çağırın. Bu klasörde aynı adı taşıyan bir dosya zaten varsa, sessiz bir şekilde üzerine yazılır.  
  
     Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#10)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#10)]  
  
## <a name="saving-a-document-with-a-new-name-and-specified-arguments"></a>Belgeye yeni bir ad ve belirtilen bağımsız değişkenlerle kaydetme  
 Belgeye uygulamak için geçerli tüm bağımsız değişkenleri belirtin ve bir belgeyi yeni adla kaydet için yöntemini kullanın.  
  
#### <a name="to-save-document-with-a-new-name-and-specified-arguments"></a>Yeni bir ad ve belirtilen bağımsız değişkenlerle belgeyi kaydetmek için  
  
-   Dosya adını içeren tam bir yol kullanarak kaydetmek istediğiniz Microsoft.Office.Interop.Visio.Document.SaveAsEx, yöntemini çağırın. Bu klasörde aynı adı taşıyan bir dosya zaten varsa, özel durum oluşur.  
  
     Aşağıdaki kod örneğinde etkin belgeyi yeni adla kaydeder, belgeyi salt okunur olarak işaretler ve belge belgelerin en son kullanılan listesini gösterir. Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#12)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği için şunlar gerekir:  
  
-   Yeni bir adı olan bir belgeyi kaydetmek için bir dizin adlı `Test` Belgelerim klasörünü (Windows XP ve önceki sürümler için) veya belgeler klasöründe (Windows Vista için) bulunması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini açma](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Yazdırma](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  