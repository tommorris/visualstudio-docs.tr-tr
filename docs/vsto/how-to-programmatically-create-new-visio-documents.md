---
title: 'Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], creating Visio documents
- documents [Office development in Visual Studio], creating Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b5b66690d3856a2bf1fc6df417b60ab5e293127
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256750"
---
# <a name="how-to-programmatically-create-new-visio-documents"></a>Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma
  Yeni Microsoft Office Visio çizim belgesi oluşturduğunuzda, ona ekleyen `Microsoft.Office.Interop.Visio.Documents` açık Visio belgelerinin koleksiyonu. Sonuç olarak, `Microsoft.Office.Interop.Visio.Documents.Add` yöntemi, yeni bir Visio çizim belgesi oluşturur. Daha fazla bilgi için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) yöntemi.  
  
## <a name="create-new-blank-documents"></a>Yeni boş belgeler oluşturma  
  
### <a name="to-create-a-new-document"></a>Yeni bir belge oluşturmak için  
  
-   Kullanım `Microsoft.Office.Interop.Visio.Documents.Add` yöntemi bir şablona dayalı olmayan yeni bir boş belge oluşturulamadı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="create-documents-copied-from-existing-documents"></a>Varolan belgelerden kopyalanmış belgeler oluşturma  
 `Microsoft.Office.Interop.Visio.Documents.Add` Yöntemi, varolan Visio belgesinin kopyası olan yeni bir belge oluşturabilir. Diyagramın tam yol ve dosya adı girmeniz gerekir.  
  
### <a name="to-create-a-new-document-that-is-copied-from-an-existing-document"></a>Varolan bir belgeden kopyalanır yeni bir belge oluşturmak için  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Documents.Add` yöntemi ve Visio diyagramı yolunu belirtin.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="create-stencils-copied-from-existing-stencils"></a>Varolan örnekleri Kopyalanmış Kalıplar Oluşturma  
 [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) yöntemi, varolan bir Visio şablonu kopyası olan yeni bir şablon oluşturabilirsiniz. Şablon tam nitelenmiş yolunu ve dosya adı girmeniz gerekir.  
  
### <a name="to-create-a-new-stencil-that-is-copied-from-an-existing-stencil"></a>Varolan bir şablonu kopyalanır yeni bir şablon oluşturmak için  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Documents.Add` yöntemi ve şablon yolunu belirtin.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="create-documents-based-on-existing-templates"></a>Mevcut şablonlar temelinde belgeleri oluşturma  
 `Microsoft.Office.Interop.Visio.Documents.Add` Yöntemi yeni bir belge oluşturabilir (bir *.vsd* dosyası) varolan Visio şablonuna dayalı (bir *.vst* dosyası). Bu yöntem, şablonlar, stil ve şablon çalışma alanının parçası olan ayarları kopyalar. Şablonun tam yolunu ve dosya adı girmeniz gerekir.  
  
### <a name="to-create-a-new-document-that-is-based-on-an-existing-template"></a>Mevcut bir şablona dayalı yeni bir belge oluşturmak için  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Documents.Add` yöntemi ve şablonun yolunu belirtin.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="compile-the-code"></a>Kod derleme  
 Bu kod örneği için şunlar gerekir:  
  
-   Adlı Visio belgesine `myDrawing.vsd` adlı bir dizinde bulunan `Test` içinde *Belgelerim* klasörü (Windows XP ve önceki sürümler için) veya *belgeleri* klasöründe (Windows Vista).  
  
-   Adlı Visio belgesine `myStencil.vss` adlı bir dizinde bulunan `Test` içinde *Belgelerim* klasörü (Windows XP ve önceki sürümler için) veya *belgeleri* klasöründe (Windows Vista).  
  
-   Adlı Visio belgesine `myTemplate.vst` adlı bir dizinde bulunan `Test` içinde *Belgelerim* klasörü (Windows XP ve önceki sürümler için) veya *belgeleri* klasöründe (Windows Vista).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini açma](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini yazdırma](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  