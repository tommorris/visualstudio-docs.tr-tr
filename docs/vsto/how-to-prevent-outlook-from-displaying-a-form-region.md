---
title: "Nasıl yapılır: Outlook Form bölgesini görüntülemesini engelleme | Microsoft Docs"
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
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
ms.assetid: 82a25def-776a-476a-a72d-d0a48a827d3c
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fb181ba7bd408194bec52224496ebef7f343f5d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>Nasıl Yapılır: Outlook'un Form Bölgesini Görüntülemesini Engelleme
  Belirli bir öğe için bir form bölgesini görüntülemek için Microsoft Office Outlook istemediğiniz durumlar olabilir. Örneğin, bir kişi öğesi iş adresi içermiyorsa, iş konumunu görünmesini bir harita gösteren form bölgesini engelleyebilirsiniz.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Outlook form bölgesini görüntülemesini engellemek için  
  
1.  Değiştirmek istediğiniz form bölgesi için kod dosyasını açın.  
  
2.  Genişletme **Form bölgesi fabrikası** kod bölgesini.  
  
3.  Kodu ekleyin `FormRegionInitializing` ayarlar olay işleyicisi <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliği <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> sınıfının **doğru**.  
  
 Kişi öğesini bir adres içermiyorsa, bu örnekte, <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliği ayarlanmış **doğru**, ve form bölgesi görünmez.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [İzlenecek yol: Outlook'ta tasarlanan Form bölgesini içeri aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  