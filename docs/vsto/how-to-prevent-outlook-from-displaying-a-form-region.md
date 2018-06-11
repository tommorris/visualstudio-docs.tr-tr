---
title: 'Nasıl yapılır: Outlook form bölgesini görüntülemesini engelleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87a03e62c77730c7be2c9487c5e344d668ea62cc
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254794"
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>Nasıl yapılır: Outlook form bölgesini görüntülemesini engelleme
  Belirli bir öğe için bir form bölgesini görüntülemek için Microsoft Office Outlook istemediğiniz durumlar olabilir. Örneğin, bir kişi öğesi iş adresi içermiyorsa, iş konumunu görünmesini bir harita gösteren form bölgesini engelleyebilirsiniz.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Outlook form bölgesini görüntülemesini engellemek için  
  
1.  Değiştirmek istediğiniz form bölgesi için kod dosyasını açın.  
  
2.  Genişletme **Form bölgesi fabrikası** kod bölgesini.  
  
3.  Kodu ekleyin `FormRegionInitializing` ayarlar olay işleyicisi <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliği <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> sınıfının **doğru**.  
  
 Kişi öğesini bir adres içermiyorsa, bu örnekte, <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliği ayarlanmış **doğru**, ve form bölgesi görünmez.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Outlook form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook form bölgesi tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Nasıl yapılır: bir Outlook eklenti projesine form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [İzlenecek yol: Outlook form bölgesi tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [İzlenecek yol: Outlook'ta tasarlanan form bölgesini içeri aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  