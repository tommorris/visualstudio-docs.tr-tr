---
title: "Nasıl yapılır: program aracılığıyla Word iletişim kutularını gizli modda kullanma | Microsoft Docs"
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
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
ms.assetid: a5619325-8b54-41f1-becb-3f6eae7e4a6b
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3d36bb9342c1db3fcf0fe007b87831b8c921af6d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>Nasıl Yapılır: Gizli Modda Program Aracılığıyla Word İletişim Kutuları Kullanma
  Microsoft Office Word yerleşik iletişim kutularında kullanıcıya görüntülemeden çağırarak bir yöntem çağrısıyla karmaşık işlemleri gerçekleştirebilir. Kullanarak bunu yapabilirsiniz <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Dialog> nesne çağırmadan <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A> yöntemi.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki kod örnekleri nasıl kullanılacağını gösteren **sayfa yapısı** birden çok sayfa kullanıcı girişi olmadan Kurulum özelliklerini ayarlamak için gizli modda iletişim kutusu. Örnekler bir <xref:Microsoft.Office.Interop.Word.Dialog> özel sayfa boyutunu yapılandırmak için nesne. Üst kenar boşluğu, alt kenar boşluğu ve vb. gibi sayfa kurulumu için özel ayarlar geç bağlama özellikleri olarak kullanılabilir <xref:Microsoft.Office.Interop.Word.Dialog> nesnesi. Bu özellikler, çalışma zamanında Word tarafından dinamik olarak oluşturulur.  
  
 Aşağıdaki örnek, Visual Basic projelerinde bu görevi gerçekleştirmek gösterilmiştir nerede **Option Strict** kapalı Visual C# projeleri hedefleyen olup [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Bu projeleri, Visual Basic ve Visual C# Derleyicileri geç bağlama özelliklerini kullanabilirsiniz. Bu örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]  
  
 Aşağıdaki örnek, Visual Basic projelerinde bu görevi gerçekleştirmek gösterilmiştir nerede **Option Strict** açıktır. Bu projelerde geç bağlama özelliklere erişmek için yansıma kullanmanız gerekir. Bu örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla Word yerleşik iletişim kutularını kullanın](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Office çözümlerinde geç bağlama](../vsto/late-binding-in-office-solutions.md)   
 [Yansıma (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [Yansıma (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  