---
title: 'Nasıl yapılır: program aracılığıyla Visio belgelerini açma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening Visio documents
- Visio [Office development in Visual Studio], opening Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a3a7d2a9855abef0415661798c8a213eb748e22f
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257858"
---
# <a name="how-to-programmatically-open-visio-documents"></a>Nasıl yapılır: program aracılığıyla Visio belgelerini açma
  Varolan Microsoft Office Visio belgelerini açma için iki yöntem vardır: açık ve OpenEx. Arayan belgenin nasıl açıldığını belirleyebileceği bağımsız sağlar ancak bu OpenEx yöntemi açık yönteme aynıdır.  
  
 Nesne modeli hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Document.Print](https://msdn.microsoft.com/library/office/ff765240.aspx) yöntemi ve [Microsoft.Office.Interop.Visio.Documents.OpenEx](https://msdn.microsoft.com/library/office/ff767229.aspx) yöntem.  
  
## <a name="open-a-visio-document"></a>Visio belgelerini açma  
  
### <a name="to-open-a-visio-document"></a>Visio belgelerini açma  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Documents.Open` yöntemi ve Visio belgesinin tam yolunu sağlayın.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="open-a-visio-document-with-specified-arguments"></a>Belirtilen bağımsız değişkenlerle Visio belgelerini açma  
  
### <a name="to-open-a-visio-document-as-read-only-and-docked"></a>Salt okunur ve yerleşik olarak Visio belgelerini açma  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Documents.OpenEx` yöntemi, Visio belgesinin tam yolunu sağlayın ve kullanmak istediğiniz bağımsız değişkenleri ekleyin — Bu örnek, yerleşik ve salt okunur.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#6)]  
  
## <a name="compile-the-code"></a>Kod derleme  
 Bu kod örneği için şunlar gerekir:  
  
-   Adlı Visio belgesine `myDrawing.vsd` adlı bir dizinde bulunan `Test` içinde *Belgelerim* klasörü (Windows XP ve önceki sürümler için) veya *belgeleri* klasöründe (Windows Vista).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini yazdırma](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  