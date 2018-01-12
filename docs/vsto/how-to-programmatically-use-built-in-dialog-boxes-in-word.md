---
title: "Nasıl yapılır: program aracılığıyla Word yerleşik iletişim kutularını kullanın | Microsoft Docs"
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
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, Word
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 961f6ac2aa9852170ecce35aa18ce4c39d7a9983
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-use-built-in-dialog-boxes-in-word"></a>Nasıl Yapılır: Yerleşik Word İletişim Kutularını Program Aracılığıyla Kullanma
  Microsoft Office Word ile çalışırken, kullanıcı girişi için iletişim kutularını görüntüleme gerektiğinde zamanlar vardır. Kendi oluşturabilirsiniz, ancak, aynı zamanda sunulan yerleşik Word iletişim kutularını, kullanarak yaklaşımı isteyebilirsiniz <xref:Microsoft.Office.Interop.Word.Dialogs> koleksiyonu <xref:Microsoft.Office.Interop.Word.Application> nesnesi. Bu, 200'den fazla numaralandırmalar temsil edilir yerleşik iletişim kutularını erişmenize olanak tanır.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="displaying-dialog-boxes"></a>İletişim kutularını görüntüleme  
 Bir iletişim kutusu görüntülemek için değerlerden birini kullanın <xref:Microsoft.Office.Interop.Word.WdWordDialog> oluşturmak için sabit bir <xref:Microsoft.Office.Interop.Word.Dialog> görüntülemek istediğiniz iletişim kutusunu temsil eden nesne. Ardından, çağıran <xref:Microsoft.Office.Interop.Word.Dialog.Show%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Dialog> nesnesi.  
  
 Aşağıdaki kod örneğinde nasıl görüntüleneceğini gösterir **Dosya Aç** iletişim kutusu. Bu örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#100)]
 [!code-csharp[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#100)]  
  
### <a name="accessing-dialog-box-members-that-are-available-through-late-binding"></a>Geç bağlama aracılığıyla kullanılabilen iletişim kutusu üyelerine erişme  
 Bazı özellikleri ve yöntemleri Word iletişim kutularını, sadece geç bağlama aracılığıyla kullanılabilir. Visual Basic projeleri **Option Strict** olduğundan, bu üyeler erişmek için yansıma kullanmalısınız. Daha fazla bilgi için bkz: [Office çözümlerinde geç bağlama](../vsto/late-binding-in-office-solutions.md).  
  
 Aşağıdaki kod örneğinde nasıl kullanılacağı gösterilmektedir **adı** özelliği **Dosya Aç** iletişim kutusu Visual Basic projeleri **Option Strict** devre dışı veya Visual C# içinde hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Bu örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#122)]
 [!code-csharp[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#122)]  
  
 Aşağıdaki kod örneğinde yansıma erişmek için nasıl kullanılacağı gösterilmektedir **adı** özelliği **Dosya Aç** iletişim kutusu Visual Basic projeleri **Option Strict** olduğu . Bu örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#102)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla Word iletişim kutularını gizli modda kullanma](../vsto/how-to-programmatically-use-word-dialog-boxes-in-hidden-mode.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Option Strict deyimi](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Yansıma (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [Yansıma (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  