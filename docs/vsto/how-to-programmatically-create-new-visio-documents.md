---
title: "Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma | Microsoft Docs"
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
- Visio [Office development in Visual Studio], creating Visio documents
- documents [Office development in Visual Studio], creating Visio documents
ms.assetid: a0294d4c-be49-4cd0-b22e-3ec7568f3ec7
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3f96738d9e553ede2b74ebc118a2769b32926cba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-create-new-visio-documents"></a>Nasıl yapılır: Program Aracılığıyla Yeni Visio Belgeleri Oluşturma
  Yeni Microsoft Office Visio çizim belgesi oluşturduğunuzda, açık Visio belgelerinin Microsoft.Office.Interop.Visio.Documents koleksiyonuna ekleyin. Sonuç olarak, Microsoft.Office.Interop.Visio.Documents.Add yöntemi yeni bir Visio çizim belgesi oluşturur. Daha fazla bilgi için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) yöntemi.  
  
## <a name="creating-new-blank-documents"></a>Yeni boş belgeler oluşturma  
  
#### <a name="to-create-a-new-document"></a>Yeni bir belge oluşturmak için  
  
-   Şablona dayalı olmayan yeni, boş bir belge oluşturmak için Microsoft.Office.Interop.Visio.Documents.Add yöntemini kullanın.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="creating-documents-copied-from-existing-documents"></a>Varolan belgelerden kopyalanmış belgeler oluşturma  
 Microsoft.Office.Interop.Visio.Documents.Add yöntemi varolan Visio belgesinin kopyası olan yeni bir belge oluşturabilirsiniz. Diyagramın tam yol ve dosya adı girmeniz gerekir.  
  
#### <a name="to-create-a-new-document-that-is-copied-from-an-existing-document"></a>Varolan bir belgeden kopyalanır yeni bir belge oluşturmak için  
  
-   Microsoft.Office.Interop.Visio.Documents.Add yöntemini çağırın ve Visio diyagramı yolunu belirtin.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="creating-stencils-copied-from-existing-stencils"></a>Varolan örnekleri Kopyalanmış Kalıplar Oluşturma  
 [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) yöntemi, varolan bir Visio şablonu kopyası olan yeni bir şablon oluşturabilirsiniz. Şablon tam nitelenmiş yolunu ve dosya adı girmeniz gerekir.  
  
#### <a name="to-create-a-new-stencil-that-is-copied-from-an-existing-stencil"></a>Varolan bir şablonu kopyalanır yeni bir şablon oluşturmak için  
  
-   Microsoft.Office.Interop.Visio.Documents.Add yöntemini çağırın ve şablon yolunu belirtin.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="creating-documents-based-on-existing-templates"></a>Var olan şablonları temel alan belgeler oluşturma  
 Microsoft.Office.Interop.Visio.Documents.Add yöntemi varolan Visio şablonuna (.vst dosyası) bağlı yeni bir belge (.vsd dosyası) oluşturabilirsiniz. Bu yöntem, şablonlar, stil ve şablon çalışma alanının parçası olan ayarları kopyalar. Şablonun tam yolunu ve dosya adı girmeniz gerekir.  
  
#### <a name="to-create-a-new-document-that-is-based-on-an-existing-template"></a>Mevcut bir şablona dayalı yeni bir belge oluşturmak için  
  
-   Microsoft.Office.Interop.Visio.Documents.Add yöntemini çağırın ve şablonun yolunu belirtin.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği için şunlar gerekir:  
  
-   Adlı Visio belgesine `myDrawing.vsd` adlı bir dizinde bulunan `Test` Belgelerim klasörünü (Windows XP ve önceki sürümler için) ya da Belgeler klasöründe (Windows Vista).  
  
-   Adlı Visio belgesine `myStencil.vss` adlı bir dizinde bulunan `Test` Belgelerim klasörünü (Windows XP ve önceki sürümler için) ya da Belgeler klasöründe (Windows Vista).  
  
-   Adlı Visio belgesine `myTemplate.vst` adlı bir dizinde bulunan `Test` Belgelerim klasörünü (Windows XP ve önceki sürümler için) ya da Belgeler klasöründe (Windows Vista).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini açma](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Yazdırma](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  