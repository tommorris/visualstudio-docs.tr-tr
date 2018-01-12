---
title: "Nasıl yapılır: program aracılığıyla Visio belgelerini açma | Microsoft Docs"
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
- documents [Office development in Visual Studio], opening Visio documents
- Visio [Office development in Visual Studio], opening Visio documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a558e0cd069c91a490f039198b59aa3a89c83662
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-open-visio-documents"></a>Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Açma
  Varolan Microsoft Office Visio belgelerini açma için iki yöntem vardır: açık ve OpenEx. Arayan belgenin nasıl açıldığını belirleyebileceği bağımsız sağlar ancak bu OpenEx yöntemi açık yönteme aynıdır.  
  
 Nesne modeli hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Document.Print](https://msdn.microsoft.com/library/office/ff765240.aspx) yöntemi ve [Microsoft.Office.Interop.Visio.Documents.OpenEx](https://msdn.microsoft.com/library/office/ff767229.aspx) yöntem.  
  
## <a name="opening-a-visio-document"></a>Visio belgelerini açma  
  
#### <a name="to-open-a-visio-document"></a>Visio belgelerini açma  
  
-   Microsoft.Office.Interop.Visio.Document.Print yöntemini çağırın ve Visio belgesinin tam yolunu sağlayın.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="opening-a-visio-document-with-specified-arguments"></a>Belirtilen bağımsız değişkenlerle Visio belgelerini açma  
  
#### <a name="to-open-a-visio-document-as-read-only-and-docked"></a>Salt okunur ve yerleşik olarak Visio belgelerini açma  
  
-   Microsoft.Office.Interop.Visio.Page.Print çağırın, Visio belgesinin tam yolunu sağlayın ve kullanmak istediğiniz bağımsız değişkenleri ekleyin — Bu örnek, yerleşik ve salt okunur.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#6)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği için şunlar gerekir:  
  
-   Adlı Visio belgesine `myDrawing.vsd` adlı bir dizinde bulunan `Test` Belgelerim klasörünü (Windows XP ve önceki sürümler için) ya da Belgeler klasöründe (Windows Vista).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Yazdırma](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  