---
title: 'Nasıl yapılır: program aracılığıyla kopyalama ve yapıştırma şekiller Visio belgelerinde | Microsoft Docs'
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
ms.openlocfilehash: 488cda5519a211754498b50a88995de64a8ed366
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-copy-and-paste-shapes-in-a-visio-document"></a>Nasıl yapılır: Visio Belgelerinde Program Aracılığıyla Şekilleri Kopyalama ve Yapıştırma
  Program aracılığıyla şekilleri belgenin bir sayfaya kopyalayın ve yeni bir sayfa aynı belgedeki yapıştırın. Özgün sayfasında sahip oldukları gibi varsayılan konuma (Etkin pencereyi Merkezi) veya aynı koordinat konumlarına bunları yapıştırmak seçebilirsiniz.  
  
## <a name="copying-and-pasting-shapes"></a>Şekilleri kopyalama ve yapıştırma  
 Nesne modeli hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [ Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), ve [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) yöntemleri ve [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNormal](https://msdn.microsoft.com/library/office/ff765187.aspx) bayrağı.  
  
#### <a name="to-copy-shapes-to-the-center-of-another-page"></a>Başka bir sayfaya merkezine şekiller kopyalamak için  
  
-   Aşağıdaki örnek, şekillerin ilk sayfadan kopyalayın ve ikinci sayfasında merkezine yapıştırın gösterilmiştir.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#14)]  
  
## <a name="copying-and-pasting-shapes-with-the-same-positions"></a>Aynı konumlarla şekilleri kopyalama ve yapıştırma  
 Nesne modeli hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [ Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), ve [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) yöntemleri ve [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNoTranslate](https://msdn.microsoft.com/library/office/ff765187.aspx) bayrağı.  
  
 Yapıştırılan bilgilerin biçimini denetlemek ve (isteğe bağlı) kaynak dosyaya (örneğin, Microsoft Office Word belgesi) bir bağlantı kurmak gerekiyorsa, denetlemeye yöntemini kullanın.  
  
#### <a name="to-copy-shapes-and-shape-locations-to-another-page"></a>Şekiller ve Şekil konumları başka bir sayfaya kopyalamak için  
  
-   Aşağıdaki örnekte, ilk sayfadan şekilleri kopyalama ve bunları özgün koordinat konumlarına ikinci sayfasıyla yapıştırın gösterilmiştir.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)   
 [Nasıl yapılır: Visio Belgesine Program Aracılığıyla Şekiller Ekleme](../vsto/how-to-programmatically-add-shapes-to-a-visio-document.md)  
  
  