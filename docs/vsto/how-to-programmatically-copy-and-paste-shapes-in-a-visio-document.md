---
title: 'Nasıl yapılır: program aracılığıyla kopyalayıp Visio belgelerinde şekilleri yapıştırın'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- shapes [Office development in Visual Studio], copying and pasting Visio shapes
- Visio [Office development in Visual Studio], copying and pasting Visio shapes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 29dada62bb1e51c9cafb41d4eae08ce10e9a930c
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257091"
---
# <a name="how-to-programmatically-copy-and-paste-shapes-in-a-visio-document"></a>Nasıl yapılır: program aracılığıyla kopyalayıp Visio belgelerinde şekilleri yapıştırın
  Program aracılığıyla şekilleri belgenin bir sayfaya kopyalayın ve yeni bir sayfa aynı belgedeki yapıştırın. Özgün sayfasında sahip oldukları gibi varsayılan konuma (Etkin pencereyi Merkezi) veya aynı koordinat konumlarına bunları yapıştırmak seçebilirsiniz.  
  
## <a name="copy-and-paste-shapes"></a>Kopyalama ve yapıştırma şekiller  
 Nesne modeli hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [ Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), ve [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) yöntemleri ve [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNormal](https://msdn.microsoft.com/library/office/ff765187.aspx) bayrağı.  
  
### <a name="to-copy-shapes-to-the-center-of-another-page"></a>Başka bir sayfaya merkezine şekiller kopyalamak için  
  
-   Aşağıdaki örnek, şekillerin ilk sayfadan kopyalayın ve ikinci sayfasında merkezine yapıştırın gösterilmiştir.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#14)]  
  
## <a name="copy-and-paste-shapes-with-the-same-positions"></a>Kopyalama ve yapıştırma aynı konumlarla şekiller  
 Nesne modeli hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [ Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), ve [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) yöntemleri ve [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNoTranslate](https://msdn.microsoft.com/library/office/ff765187.aspx) bayrağı.  
  
 Yapıştırılan bilgilerin biçimini denetlemek ve (isteğe bağlı) kaynak dosyaya (örneğin, Microsoft Office Word belgesi) bir bağlantı kurmak gerekiyorsa, denetlemeye yöntemini kullanın.  
  
### <a name="to-copy-shapes-and-shape-locations-to-another-page"></a>Şekiller ve Şekil konumları başka bir sayfaya kopyalamak için  
  
-   Aşağıdaki örnekte, ilk sayfadan şekilleri kopyalama ve bunları özgün koordinat konumlarına ikinci sayfasıyla yapıştırın gösterilmiştir.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)   
 [Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme](../vsto/how-to-programmatically-add-shapes-to-a-visio-document.md)  
  
  